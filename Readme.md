

# Laravel 12-ready Core Schema for Research/Chat App

> **Note:** The following schema is not standard Markdown, but a DSL for describing the database structure. For better readability and rendering on GitHub, the schema is visualized as a diagram below.

Vector embeddings are stored externally (n8n). Only IDs and metadata are stored in the database.

```mermaid
erDiagram
  USERS {
    bigint id PK "auto increment"
    varchar name
    varchar email "unique, not null"
    timestamp email_verified_at
    varchar password "not null"
    varchar remember_token
    timestamp created_at
    timestamp updated_at
    timestamp deleted_at
  }
  PERSONAL_ACCESS_TOKENS {
    bigint id PK "auto increment"
    varchar tokenable_type "not null"
    bigint tokenable_id "not null"
    varchar name "not null"
    varchar token "unique, not null"
    text abilities
    timestamp last_used_at
    timestamp expires_at
    timestamp created_at
    timestamp updated_at
  }
  PASSWORD_RESET_TOKENS {
    varchar email PK
    varchar token "not null"
    timestamp created_at
  }
  PROBLEMS {
    uuid id PK
    bigint user_id FK
    varchar title "not null"
    text description
    varchar status "not null, default: open"
    timestamp created_at
    timestamp updated_at
    timestamp deleted_at
  }
  RESEARCHES {
    uuid id PK
    uuid problem_id FK
    varchar vector_store_kind "not null, default: n8n"
    varchar vector_store_ref "not null"
    varchar vector_version
    int source_count "not null, default: 0"
    text notes
    timestamp created_at
    timestamp updated_at
    timestamp deleted_at
  }
  CHAT_SESSIONS {
    bigint id PK "auto increment"
    bigint user_id FK
    uuid problem_id FK
    varchar title
    json metadata
    timestamp created_at
    timestamp updated_at
    timestamp deleted_at
  }
  CHAT_MESSAGES {
    bigint id PK "auto increment"
    bigint chat_session_id FK
    bigint user_id FK
    varchar role "not null"
    text content "not null"
    varchar tool_name
    json metadata
    timestamp created_at
    timestamp updated_at
  }
  MESSAGE_RESEARCH_CITATIONS {
    bigint id PK "auto increment"
    bigint message_id FK
    uuid research_id FK
    varchar note
    timestamp created_at
  }
  CHAT_SESSION_RESEARCH_PREFS {
    bigint id PK "auto increment"
    bigint chat_session_id FK
    uuid research_id FK
    int priority "not null, default: 0"
    timestamp created_at
    timestamp updated_at
  }

  USERS ||--o{ PROBLEMS : "user_id"
  PROBLEMS ||--o{ RESEARCHES : "problem_id"
  USERS ||--o{ CHAT_SESSIONS : "user_id"
  PROBLEMS ||--o{ CHAT_SESSIONS : "problem_id"
  CHAT_SESSIONS ||--o{ CHAT_MESSAGES : "chat_session_id"
  USERS ||--o{ CHAT_MESSAGES : "user_id"
  CHAT_MESSAGES ||--o{ MESSAGE_RESEARCH_CITATIONS : "message_id"
  RESEARCHES ||--o{ MESSAGE_RESEARCH_CITATIONS : "research_id"
  CHAT_SESSIONS ||--o{ CHAT_SESSION_RESEARCH_PREFS : "chat_session_id"
  RESEARCHES ||--o{ CHAT_SESSION_RESEARCH_PREFS : "research_id"
```

//// ---------------------------
//// Enums
//// ---------------------------
Enum message_role {
  user
  assistant
  system
  tool
}

//// ---------------------------
//// Core Auth / Users
//// ---------------------------
Table users {
  id                bigint [pk, increment] // Laravel default
  name              varchar(255)
  email             varchar(255) [not null, unique]
  email_verified_at timestamp [null]
  password          varchar(255) [not null]
  remember_token    varchar(100) [null]
  created_at        timestamp
  updated_at        timestamp
  deleted_at        timestamp [null] // soft delete
}

//// Laravel Sanctum (API tokens)
Table personal_access_tokens {
  id             bigint [pk, increment]
  tokenable_type varchar(255) [not null]
  tokenable_id   bigint [not null]
  name           varchar(255) [not null]
  token          varchar(64)  [not null, unique] // hashed token
  abilities      text [null]
  last_used_at   timestamp [null]
  expires_at     timestamp [null]
  created_at     timestamp
  updated_at     timestamp

  Indexes {
    (tokenable_type, tokenable_id)
  }
}

//// Password reset tokens (Laravel 10/12)
Table password_reset_tokens {
  email      varchar(255) [pk]
  token      varchar(255) [not null]
  created_at timestamp [null]
}

//// ---------------------------
//// Problem & Research (metadata only)
//// ---------------------------
Table problems {
  id          uuid [pk]                       // Business/domain ID (ULID/UUID ok; using UUID here)
  user_id     bigint [not null, ref: > users.id]
  title       varchar(255) [not null]
  description text [null]
  status      varchar(50) [not null, default: 'open'] // open|in_progress|done
  created_at  timestamp
  updated_at  timestamp
  deleted_at  timestamp [null]
  Indexes {
    (user_id)
    (status)
  }
}

Table researches {
  id                   uuid [pk]                         // Business/domain ID for research
  problem_id           uuid [not null, ref: > problems.id]
  vector_store_kind    varchar(50)  [not null, default: 'n8n'] // e.g., 'n8n'
  vector_store_ref     varchar(255) [not null]                 // external identifier (index/collection/id)
  vector_version       varchar(50)  [null]                     // optional version/tag
  source_count         int          [not null, default: 0]
  notes                text         [null]                     // optional notes/summary
  created_at           timestamp
  updated_at           timestamp
  deleted_at           timestamp [null]
  Indexes {
    (problem_id)
    (vector_store_kind, vector_store_ref) [unique]
  }
}

//// ---------------------------
//// Chat Sessions & Messages (chat history)
//// ---------------------------
Table chat_sessions {
  id          bigint [pk, increment]
  user_id     bigint [not null, ref: > users.id] // owner/creator
  problem_id  uuid   [null, ref: > problems.id]  // optional link to a problem
  title       varchar(255) [null]
  metadata    json        [null]                 // free-form small metadata
  created_at  timestamp
  updated_at  timestamp
  deleted_at  timestamp [null]
  Indexes {
    (user_id)
    (problem_id)
  }
}

Table chat_messages {
  id               bigint [pk, increment]
  chat_session_id  bigint [not null, ref: > chat_sessions.id]
  user_id          bigint [null, ref: > users.id]      // null for assistant/system/tool messages
  role             message_role [not null]             // user|assistant|system|tool
  content          text [not null]                     // main message content
  tool_name        varchar(100) [null]                 // filled if role=tool
  metadata         json [null]                         // small per-message metadata (tokens, latency, etc.)
  created_at       timestamp
  updated_at       timestamp
  Indexes {
    (chat_session_id, created_at)
    (user_id)
    (role)
  }
}

//// Messages referencing research items used/cited for the response
Table message_research_citations {
  id          bigint [pk, increment]
  message_id  bigint [not null, ref: > chat_messages.id]
  research_id uuid   [not null, ref: > researches.id]
  note        varchar(255) [null]   // optional: which chunk/section, etc.
  created_at  timestamp
  Indexes {
    (message_id)
    (research_id)
    (message_id, research_id) [unique]
  }
}

//// ---------------------------
//// Optional: tie a chat session to a preferred research set (shortcut)
//// ---------------------------
Table chat_session_research_prefs {
  id              bigint [pk, increment]
  chat_session_id bigint [not null, ref: > chat_sessions.id]
  research_id     uuid   [not null, ref: > researches.id]
  priority        int    [not null, default: 0] // lower = higher priority
  created_at      timestamp
  updated_at      timestamp
  Indexes {
    (chat_session_id)
    (research_id)
    (chat_session_id, research_id) [unique]
    (chat_session_id, priority)
  }
}

//// ---------------------------
//// Foreign Key Graph (explicit Refs for clarity)
//// ---------------------------
Ref: problems.user_id > users.id
Ref: researches.problem_id > problems.id
Ref: chat_sessions.user_id > users.id
Ref: chat_sessions.problem_id > problems.id
Ref: chat_messages.chat_session_id > chat_sessions.id
Ref: chat_messages.user_id > users.id
Ref: message_research_citations.message_id > chat_messages.id
Ref: message_research_citations.research_id > researches.id
Ref: chat_session_research_prefs.chat_session_id > chat_sessions.id
Ref: chat_session_research_prefs.research_id > researches.id
