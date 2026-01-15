# System Architecture Diagram

```mermaid
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
```
# User Registration & Authentication Flow

```mermaid
flowchart TD
    Start[User Registration] --> Upload[Upload Student Card Photo]
    Upload --> Form[Fill Registration Form]
    Form --> Submit[Submit to Backend]
    Submit --> Store[Store as Pending User]
    Store --> Notify[Notify Admin]
    Notify --> Approve{Admin Approval}
    Approve -->|Yes| Activate[Activate Account]
    Activate --> Login[User Can Login]
    Approve -->|No| Reject[Account Rejected]
    Reject --> NotifyUser[Notify User via Email]
    
    Login --> Auth[JWT Token Issued]
    Auth --> Access[Access Platform Features]
```

# Timetable Planner Workflow

```mermaid
flowchart LR
    A[PDF Timetable<br>MTT_2526S1_V2_20250911.pdf] --> B[Python Scripts<br>PyMuPDF]
    B --> C[Extracted Course Data<br>JSON Format]
    C --> D[MongoDB Course Collection]
    
    E[User] --> F[Search & Select Courses]
    F --> G[Drag & Drop Interface]
    G --> H[Real-time Conflict Detection]
    H --> I[Save Timetable]
    I --> J[Export as PNG/JSON]
    
    D --> F
```

# Group Formation System

```mermaid
flowchart TD
    A[User Creates Group Request] --> B[Adds Preferences: Major, GPA, etc.]
    B --> C[Request Stored in MongoDB]
    C --> D[Visible in Public List]
    
    E[Other User Browsing] --> F[Filter by Preferences]
    F --> G[Send Interest]
    G --> H[Automated Email Notification]
    H --> I[Poster Receives Contact Info]
    I --> J[Direct Communication]
```

# Questionnaire Credit System

```mermaid
flowchart TD
    Start[New User Registration] --> Credits[Receive 3 Credits]
    
    subgraph "Questionnaire Workflow"
        direction LR
        A[User Posts Questionnaire<br>Cost: 1 Credit] --> B[Listing Visible to Others]
        B --> C[Other Users Fill Questionnaire<br>Earn: 1 Credit Each]
        C --> D[Target: 30 Responses]
        D --> E[Questionnaire Completed]
    end
    
    Credits --> Check{Credits > 0?}
    Check -->|Yes| A
    Check -->|No| FillOthers[Must Fill Others' Questionnaires First]
    FillOthers --> C
```

# File Upload & Storage Flow

```mermaid
flowchart TD
    subgraph "Client Side"
        A[User Selects File] --> B[Client-side Validation<br>Size & Type Check]
        B --> C[Convert to Base64]
        C --> D[Send to API]
    end
    
    subgraph "Server Side"
        D --> E[Server-side Validation]
        E --> F[Role-based Access Check]
        F --> G{Admin Role?}
        G -->|Yes| H[Store in GridFS<br>MongoDB]
        G -->|No| I[Access Denied]
        H --> J[Update Metadata in Collection]
        J --> K[Success Response]
    end
    
    K --> L[File Available for Download]
```

# Admin Approval Workflow

```mermaid
flowchart TD
    A[New User Registration] --> B[Account Created as 'Pending']
    B --> C[Admin Dashboard Notification]
    C --> D[Admin Reviews Student Card Photo]
    D --> Decision{Approval Decision}
    
    Decision -->|Approve| E[Change Role to 'Student']
    E --> F[Send Welcome Email]
    F --> G[User Can Login]
    
    Decision -->|Reject| H[Delete Account]
    H --> I[Send Rejection Email]
```

# Component Hierarchy

```mermaid
graph TD
    A[App Component] --> B[Main Layout]
    B --> C[Header]
    B --> D[Sidebar]
    B --> E[Content Area]
    
    E --> F[Dashboard]
    E --> G[Calendar]
    E --> H[Group Formation]
    E --> I[Questionnaire]
    E --> J[Materials]
    E --> K[Profile]
    E --> L[Admin Panel]
    
    F --> M[Statistics Cards]
    F --> N[Quick Actions]
    F --> O[Recent Activities]
    
    G --> P[Course Search]
    G --> Q[Calendar View]
    G --> R[Export/Import]
```

# Technology Stack Visualization

```mermaid
flowchart TD
    subgraph TechStack["Technology Stack Comparison"]
        React["React\nLearning Curve: 0.8\nProduction Readiness: 0.7"]
        Express["Express.js\nLearning Curve: 0.6\nProduction Readiness: 0.8"]
        MongoDB["MongoDB\nLearning Curve: 0.5\nProduction Readiness: 0.9"]
        Node["Node.js\nLearning Curve: 0.7\nProduction Readiness: 0.8"]
        PyMuPDF["PyMuPDF\nLearning Curve: 0.4\nProduction Readiness: 0.6"]
        Vercel["Vercel\nLearning Curve: 0.9\nProduction Readiness: 0.9"]
        Gmail["Gmail SMTP\nLearning Curve: 1.0\nProduction Readiness: 0.5"]
    end
```

# Deployment Architecture

```mermaid
flowchart TD
    subgraph "Development"
        A[Local Development] --> B[GitHub Repository]
    end
    
    subgraph "CI/CD Pipeline"
        B --> C[Vercel Integration]
        C --> D[Automatic Build]
        D --> E[Deploy to Vercel]
    end
    
    subgraph "Production"
        E --> F[Frontend: Vercel Hosting]
        E --> G[Backend: Serverless Functions]
        G --> H[MongoDB Atlas Cloud]
        H --> I[GridFS File Storage]
        
        F --> J[Users Access Platform]
        J --> F
        J --> G
    end
```


