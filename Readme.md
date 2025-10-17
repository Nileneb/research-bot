
# Laravel 12 Research Bot Database Schema

## Entity Relationship Diagram

```mermaid
erDiagram
    USERS {
        bigint id PK "autoincrement"
        varchar name
        varchar email "unique, not null"
        timestamp email_verified_at
        varchar password "not null"
        varchar remember_token
        timestamp created_at
        timestamp updated_at
        timestamp deleted_at "soft delete"
    }
    
    PERSONAL_ACCESS_TOKENS {
        bigint id PK "autoincrement"
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
        varchar status "default: open"
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
        int source_count "default: 0"
        text notes
        timestamp created_at
        timestamp updated_at
        timestamp deleted_at
    }
    
    CHAT_SESSIONS {
        bigint id PK "autoincrement"
        bigint user_id FK "owner"
        uuid problem_id FK "optional"
        varchar title
        json metadata
        timestamp created_at
        timestamp updated_at
        timestamp deleted_at
    }
    
    CHAT_MESSAGES {
        bigint id PK "autoincrement"
        bigint chat_session_id FK
        bigint user_id FK "null for system messages"
        enum role "user|assistant|system|tool"
        text content "not null"
        varchar tool_name
        json metadata
        timestamp created_at
        timestamp updated_at
    }
    
    MESSAGE_RESEARCH_CITATIONS {
        bigint id PK "autoincrement"
        bigint message_id FK
        uuid research_id FK
        varchar note
        timestamp created_at
    }
    
    CHAT_SESSION_RESEARCH_PREFS {
        bigint id PK "autoincrement"
        bigint chat_session_id FK
        uuid research_id FK
        int priority "default: 0"
        timestamp created_at
        timestamp updated_at
    }
    
    USERS ||--o{ PROBLEMS : "creates"
    PROBLEMS ||--o{ RESEARCHES : "has"
    USERS ||--o{ CHAT_SESSIONS : "owns"
    PROBLEMS ||--o{ CHAT_SESSIONS : "linked to"
    CHAT_SESSIONS ||--o{ CHAT_MESSAGES : "contains"
    USERS ||--o{ CHAT_MESSAGES : "authors"
    CHAT_MESSAGES ||--o{ MESSAGE_RESEARCH_CITATIONS : "cites"
    RESEARCHES ||--o{ MESSAGE_RESEARCH_CITATIONS : "cited in"
    CHAT_SESSIONS ||--o{ CHAT_SESSION_RESEARCH_PREFS : "prefers"
    RESEARCHES ||--o{ CHAT_SESSION_RESEARCH_PREFS : "preferred in"
```

## Note

Vector embeddings live externally (n8n). Only IDs and metadata are stored in this database.
