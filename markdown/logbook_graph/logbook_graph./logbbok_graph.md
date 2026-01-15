graph TB
    subgraph "Client Layer"
        A[React Frontend] --> B[Browser]
        A --> C[Local Storage]
    end
    
    subgraph "Server Layer"
        D[Node.js/Express.js]
        E[RESTful APIs]
        F[MongoDB Atlas]
        G[GridFS Storage]
        
        D --> E
        E --> F
        E --> G
    end
    
    subgraph "External Services"
        H[Gmail SMTP]
        I[PDF Timetable]
        J[Python Scripts]
    end
    
    B --> E
    F --> B
    E --> H
    I --> J
    J --> F
