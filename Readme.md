
# Laravel 12 Research Bot Database Schema
##Project Structure
### Research Analysis Software Architecture
```mermaid
flowchart TD
    A[Client] --> B[Laravel Service]
    B --> C[Agent Pico]
    B --> D[Agent Research]
    B --> E[Database  SQL DB]
    C --> F[Vector DB]
    D --> G[MCP - Paper-Search]
    subgraph UseCase[Use Case: Research]
        A
        B
        C
        D
        E
        F
        G
    end
```
##Sequence Diagram
```mermaid
sequenceDiagram
    autonumber
    participant Client
    participant Laravel as Laravel Service
    participant Pico as Agent Pico
    participant VDB as Vektor DB
    participant Research as Agent Research
    participant MCP as MCP (Paper-Search)
    participant SQL as SQL DB

    Client->>Laravel: Submit research query
    Note over Laravel: Validate, auth, route

    par Lightweight enrichment
        Laravel->>Pico: Pre-filter / embed request
        Pico->>VDB: Upsert/Retrieve embeddings
        VDB-->>Pico: Vectors / candidates
        Pico-->>Laravel: Filtered context
    and Core paper search
        Laravel->>Research: Research task with context
        Research->>MCP: Query papers/APIs
        MCP-->>Research: Results (papers, metadata)
        Research-->>Laravel: Ranked findings
    end

    Laravel->>SQL: Persist chat, query, metadata, links
    SQL-->>Laravel: IDs / status

    Laravel-->>Client: Consolidated response (results + refs)
```

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
    varchar role "user|assistant|system|tool"
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



# Research-Bot — 24-Month Roadmap (Flowchart)

```mermaid
flowchart TD
    Start([Start])
    Core[Product Core]
    AI[AI / Genetics / 3D]
    Game[Gamification]
    Agents[Research Agents]
    Evidence[Evidence Automation]
    Platform[Platform & Monetarization]
    Compliance[Compliance & Infra]
    Integration[Integrations]
    Growth[Growth / Community]
    Milestones[Big Milestones]
    End([End])

    Start --> Core
    Core --> AI
    AI --> Game
    Game --> Agents
    Agents --> Evidence
    Evidence --> Platform
    Platform --> Compliance
    Compliance --> Integration
    Integration --> Growth
    Growth --> Milestones
    Milestones --> End

    Core -->|"Public Beta (v0.9)"| AI
    AI -->|"Pilot Genomics View"| Game
    Game -->|"Season-0 Launch"| Agents
    Agents -->|"Agent Pack v1"| Evidence
    Evidence -->|"Evidence Suite v1"| Platform
    Platform -->|"Pro/Enterprise Release"| Compliance
    Compliance -->|"Compliance Gate v1"| Integration
    Integration -->|"Partner-Pilot Journal"| Growth
    Growth -->|"Community Summit"| Milestones
    Milestones -->|"v1.0 GA, Break-even"| End
```