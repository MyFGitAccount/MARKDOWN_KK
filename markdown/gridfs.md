# Figure 1: EFS Platform Architecture Diagram

## System Overview

The EFS Platform employs a modern serverless architecture with MongoDB GridFS for handling large files, overcoming the limitations of ephemeral cloud environments like Vercel.

```mermaid
graph TB
    %% ====================
    %% Frontend Layer
    %% ====================
    subgraph "Frontend Layer (React/Vite)"
        React["React Components<br/>User Interface"]
        
        subgraph "Frontend Routes"
            FR1["/register<br/>Registration Form"]
            FR2["/login<br/>Login Form"]
            FR3["/dashboard<br/>User Dashboard"]
            FR4["/courses<br/>Course Browser"]
            FR5["/calendar<br/>Timetable"]
            FR6["/group<br/>Group Formation"]
            FR7["/questionnaire<br/>Survey Exchange"]
            FR8["/materials<br/>Learning Resources"]
            FR9["/admin<br/>Admin Panel"]
        end
        
        React --> FR1
        React --> FR2
        React --> FR3
        React --> FR4
        React --> FR5
        React --> FR6
        React --> FR7
        React --> FR8
        React --> FR9
    end

    %% ====================
    %% API Gateway Layer
    %% ====================
    subgraph "API Gateway Layer (Express.js)"
        Express["Express Server<br/>API Router"]
        
        subgraph "API Endpoints"
            API1["POST /api/auth/register"]
            API2["POST /api/auth/login"]
            API3["GET /api/dashboard/summary"]
            API4["GET|POST /api/courses/*"]
            API5["GET|POST /api/calendar/*"]
            API6["GET|POST /api/group/*"]
            API7["GET|POST /api/questionnaire/*"]
            API8["GET|POST /api/materials/*"]
            API9["GET|POST /api/admin/*"]
            API10["GET /api/upload/*"]
        end
        
        Express --> API1
        Express --> API2
        Express --> API3
        Express --> API4
        Express --> API5
        Express --> API6
        Express --> API7
        Express --> API8
        Express --> API9
        Express --> API10
    end

    %% ====================
    %% Authentication Layer
    %% ====================
    subgraph "Authentication Layer"
        AuthMiddleware["Authentication Middleware"]
        TokenValidation["Token Validation<br/>(Bearer Token)"]
        RoleCheck["Role-based Access Control"]
        
        AuthMiddleware --> TokenValidation
        TokenValidation --> RoleCheck
    end

    %% ====================
    %% Core Business Logic
    %% ====================
    subgraph "Business Logic Layer"
        CreditSystem["Credit System Manager"]
        ApprovalWorkflow["Approval Workflow Engine"]
        FileProcessor["File Processor<br/>(Base64 ↔ Buffer)"]
        GridFSManager["GridFS Manager<br/>(Streaming)"]
        
        CreditSystem --> ApprovalWorkflow
        FileProcessor --> GridFSManager
    end

    %% ====================
    %% Database Layer - MongoDB
    %% ====================
    subgraph "Database Layer (MongoDB Atlas)"
        DB["MongoDB Database"]
        
        subgraph "Collections"
            Users["users<br/>Approved accounts"]
            PendingAcc["pending_accounts<br/>Awaiting approval"]
            Courses["courses<br/>Course catalog"]
            PendingCourses["pending_courses<br/>Course requests"]
            GroupReq["group_requests<br/>Study groups"]
            Questionnaires["questionnaires<br/>Surveys"]
            Materials["materials<br/>File metadata"]
            Timetables["user_timetables<br/>Schedules"]
        end
        
        subgraph "GridFS Buckets"
            UploadsFiles["uploads.files<br/>File metadata"]
            UploadsChunks["uploads.chunks<br/>Binary data chunks"]
            
            UploadsFiles -- "references" --> UploadsChunks
        end
        
        DB --> Users
        DB --> PendingAcc
        DB --> Courses
        DB --> PendingCourses
        DB --> GroupReq
        DB --> Questionnaires
        DB --> Materials
        DB --> Timetables
        DB --> UploadsFiles
    end

    %% ====================
    %% External Services
    %% ====================
    subgraph "External Services"
        EmailService["Email Service<br/>(Nodemailer)"]
        PDFProcessor["PDF Processing Service<br/>(Optional)"]
        
        subgraph "Email Types"
            E1["Approval/Rejection"]
            E2["Group Invitations"]
            E3["Admin Notifications"]
            E4["System Alerts"]
        end
        
        EmailService --> E1
        EmailService --> E2
        EmailService --> E3
        EmailService --> E4
    end

    %% ====================
    %% File Flow Examples
    %% ====================
    subgraph "File Upload Flow Example"
        Upload["1. User Upload"]
        Base64["2. Base64 Encoding"]
        Buffer["3. Buffer Conversion"]
        GridFSWrite["4. GridFS Write Stream"]
        Chunking["5. Automatic Chunking<br/>(255KB per chunk)"]
        
        Upload --> Base64
        Base64 --> Buffer
        Buffer --> GridFSWrite
        GridFSWrite --> Chunking
    end
    
    subgraph "File Download Flow Example"
        Request["1. File Request"]
        GridFSRead["2. GridFS Read Stream"]
        Stream["3. HTTP Streaming"]
        Client["4. Client Receives"]
        
        Request --> GridFSRead
        GridFSRead --> Stream
        Stream --> Client
    end

    %% ====================
    %% Connections
    %% ====================
    %% Frontend to API
    FR1 -- "HTTP POST with Base64<br/>student card photo" --> API1
    FR2 -- "HTTP POST credentials" --> API2
    FR3 -- "HTTP GET with Bearer token" --> API3
    FR4 -- "Course browsing/requests" --> API4
    FR5 -- "Timetable operations" --> API5
    FR6 -- "Group formation" --> API6
    FR7 -- "Questionnaire exchange" --> API7
    FR8 -- "Material upload/download" --> API8
    FR9 -- "Admin operations" --> API9
    
    %% API to Middleware
    API1 --> AuthMiddleware
    API2 --> AuthMiddleware
    API3 --> AuthMiddleware
    API9 --> AuthMiddleware
    
    %% Middleware to Business Logic
    AuthMiddleware -- "Validated request" --> CreditSystem
    AuthMiddleware -- "Admin role required" --> ApprovalWorkflow
    
    %% Business Logic to Database
    CreditSystem -- "Update credit balance" --> Users
    ApprovalWorkflow -- "Move from pending to users" --> PendingAcc
    ApprovalWorkflow -- "Approve/reject accounts" --> Users
    
    FileProcessor -- "Convert files for storage" --> GridFSManager
    GridFSManager -- "Stream to GridFS" --> UploadsFiles
    GridFSManager -- "Read from GridFS" --> UploadsFiles
    
    %% File-specific API connections
    API8 -- "Upload material<br/>(Admin only)" --> FileProcessor
    API10 -- "Stream files<br/>(No auth for public)" --> GridFSManager
    API1 -- "Upload student card" --> FileProcessor
    
    %% Database relationships
    Materials -- "Contains fileId references" --> UploadsFiles
    Users -- "photoFileId references" --> UploadsFiles
    
    %% External service triggers
    ApprovalWorkflow -- "Trigger email on approval" --> EmailService
    API6 -- "Send group invitation" --> EmailService
    API1 -- "Notify admin of new registration" --> EmailService
    
    %% Styling
    classDef frontend fill:#e1f5fe,stroke:#01579b,stroke-width:2px
    classDef api fill:#f3e5f5,stroke:#4a148c,stroke-width:2px
    classDef auth fill:#fff3e0,stroke:#e65100,stroke-width:2px
    classDef logic fill:#e8f5e8,stroke:#1b5e20,stroke-width:2px
    classDef database fill:#fff8e1,stroke:#ff6f00,stroke-width:2px
    classDef gridfs fill:#fce4ec,stroke:#880e4f,stroke-width:2px
    classDef external fill:#e0f2f1,stroke:#004d40,stroke-width:2px
    classDef flow fill:#f5f5f5,stroke:#616161,stroke-width:1px
    
    class React,FR1,FR2,FR3,FR4,FR5,FR6,FR7,FR8,FR9 frontend
    class Express,API1,API2,API3,API4,API5,API6,API7,API8,API9,API10 api
    class AuthMiddleware,TokenValidation,RoleCheck auth
    class CreditSystem,ApprovalWorkflow,FileProcessor,GridFSManager logic
    class DB,Users,PendingAcc,Courses,PendingCourses,GroupReq,Questionnaires,Materials,Timetables database
    class UploadsFiles,UploadsChunks gridfs
    class EmailService,PDFProcessor,E1,E2,E3,E4 external
    class Upload,Base64,Buffer,GridFSWrite,Chunking,Request,GridFSRead,Stream,Client flow
