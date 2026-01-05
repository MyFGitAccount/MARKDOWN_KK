graph TB
    subgraph "Client Layer (Frontend)"
        CL[Client Browser]
        RE[React.js]
        AD[Ant Design UI]
        FR[FullCalendar]
    end
    
    subgraph "API Layer (Backend)"
        EXP[Express.js Server]
        API[REST API Routes]
        MW[Middleware]
        AUTH[Authentication]
        CORS[CORS Config]
    end
    
    subgraph "Data Layer"
        DB[MongoDB Database]
        GF[GridFS File Storage]
        subgraph "Collections"
            US[users]
            CA[courses]
            PA[pending_accounts]
            PC[pending_courses]
            GR[group_requests]
            QN[questionnaires]
            MT[materials]
        end
    end
    
    subgraph "External Services"
        GMAIL[Nodemailer Gmail]
        VERCEL[Vercel Hosting]
    end
    
    CL --> RE
    RE --> AD
    RE --> FR
    CL -->|HTTPS| EXP
    EXP --> API
    EXP --> MW
    MW --> AUTH
    MW --> CORS
    API --> DB
    DB --> GF
    API -->|SMTP| GMAIL
    EXP -->|Deploy| VERCEL

    API -->|SMTP| GMAIL
    EXP -->|Deploy| VERCEL
