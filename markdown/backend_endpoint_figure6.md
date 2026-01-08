# Figure 6: Backend API Endpoints Architecture

## API Endpoints Overview
The EFS Platform backend exposes a comprehensive REST API organized around key functional domains.  
Each endpoint implements specific business logic with proper authentication, validation, and error handling.
```
mermaid
graph TB
    %% ====================
    %% API Endpoint Categories
    %% ====================
    subgraph "API Gateway (Express Router)"
        APIBase["/api/*<br/>Base Path"]
    end

    subgraph "Authentication Endpoints"
        AuthRouter["/api/auth/*<br/>Authentication"]
        AuthRegister["POST /register"]
        AuthLogin["POST /login"]
        AuthCheck["GET /check"]

        AuthRouter --> AuthRegister
        AuthRouter --> AuthLogin
        AuthRouter --> AuthCheck
    end

    subgraph "Group Formation Endpoints"
        GroupRouter["/api/group/*<br/>Study Groups"]
        GroupList["GET /requests"]
        GroupCreate["POST /requests"]
        GroupInvite["POST /requests/:id/invite"]
        GroupDelete["DELETE /requests/:id"]

        GroupRouter --> GroupList
        GroupRouter --> GroupCreate
        GroupRouter --> GroupInvite
        GroupRouter --> GroupDelete
    end

    subgraph "Calendar Endpoints"
        CalendarRouter["/api/calendar/*<br/>Timetable"]
        CalendarCourses["GET /courses"]
        CalendarEvents["GET /events"]
        CalendarSave["POST /save"]
        CalendarMyTimetable["GET /mytimetable"]

        CalendarRouter --> CalendarCourses
        CalendarRouter --> CalendarEvents
        CalendarRouter --> CalendarSave
        CalendarRouter --> CalendarMyTimetable
    end

    subgraph "Questionnaire Endpoints"
        QuestionnaireRouter["/api/questionnaire/*<br/>Survey Exchange"]
        QuestionnaireList["GET /"]
        QuestionnairePost["POST /"]
        QuestionnaireFill["POST /:id/fill"]
        QuestionnaireMy["GET /my"]

        QuestionnaireRouter --> QuestionnaireList
        QuestionnaireRouter --> QuestionnairePost
        QuestionnaireRouter --> QuestionnaireFill
        QuestionnaireRouter --> QuestionnaireMy
    end

    subgraph "Materials Endpoints"
        MaterialsRouter["/api/materials/*<br/>Learning Resources"]
        MaterialsUpload["POST /course/:code"]
        MaterialsDownload["GET /download/:id"]
        MaterialsList["GET /course/:code"]

        MaterialsRouter --> MaterialsUpload
        MaterialsRouter --> MaterialsDownload
        MaterialsRouter --> MaterialsList
    end

    subgraph "Admin Endpoints"
        AdminRouter["/api/admin/*<br/>Administration"]
        AdminPendingAccounts["GET /pending/accounts"]
        AdminApproveAccount["POST /pending/accounts/:sid/approve"]
        AdminRejectAccount["POST /pending/accounts/:sid/reject"]
        AdminUsers["GET /users"]
        AdminStats["GET /stats"]

        AdminRouter --> AdminPendingAccounts
        AdminRouter --> AdminApproveAccount
        AdminRouter --> AdminRejectAccount
        AdminRouter --> AdminUsers
        AdminRouter --> AdminStats
    end

    subgraph "User Management Endpoints"
        ProfileRouter["/api/profile/*<br/>User Profiles"]
        ProfileMe["GET /me"]
        ProfileUpdate["PUT /update"]
        ProfileBySid["GET /:sid"]

        MeRouter["/api/me/*<br/>Current User"]
        MeCredits["GET /credits"]

        ProfileRouter --> ProfileMe
        ProfileRouter --> ProfileUpdate
        ProfileRouter --> ProfileBySid
        MeRouter --> MeCredits
    end

    %% ====================
    %% Database Collections
    %% ====================
    subgraph "MongoDB Collections"
        UsersCollection["users<br/>User accounts"]
        PendingAccountsCollection["pending_accounts<br/>Registration queue"]
        GroupRequestsCollection["group_requests<br/>Study group requests"]
        UserTimetablesCollection["user_timetables<br/>Personal schedules"]
        QuestionnairesCollection["questionnaires<br/>Survey management"]
        MaterialsCollection["materials<br/>File metadata"]
        CoursesCollection["courses<br/>Course catalog"]
        UploadsFilesCollection["uploads.files<br/>GridFS metadata"]
        UploadsChunksCollection["uploads.chunks<br/>GridFS binary data"]
    end

    %% ====================
    %% External Services
    %% ====================
    subgraph "External Services"
        EmailServiceNode["Email Service<br/>Nodemailer"]
        CryptoService["Crypto Module<br/>Token generation"]
        BCryptService["BCrypt<br/>Password hashing"]
        GridFSService["GridFS<br/>File storage"]
    end

    %% ====================
    %% Connections
    %% ====================
    APIBase --> AuthRouter
    APIBase --> GroupRouter
    APIBase --> CalendarRouter
    APIBase --> QuestionnaireRouter
    APIBase --> MaterialsRouter
    APIBase --> AdminRouter
    APIBase --> ProfileRouter
    APIBase --> MeRouter

    %% ====================
    %% Styling
    %% ====================
    classDef category fill:#e3f2fd,stroke:#1565c0,stroke-width:3px,color:#000000,font-size:16px
    classDef endpoint fill:#f3e5f5,stroke:#7b1fa2,stroke-width:3px,color:#000000,font-size:16px
    classDef flow fill:#e8f5e8,stroke:#2e7d32,stroke-width:3px,color:#000000,font-size:16px
    classDef database fill:#fff8e1,stroke:#ff8f00,stroke-width:3px,color:#000000,font-size:16px
    classDef service fill:#e0f2f1,stroke:#00695c,stroke-width:3px,color:#000000,font-size:16px

    %% Different colors for each API block
    class AuthRouter,AuthRegister,AuthLogin,AuthCheck fill:#ffe0e0,stroke:#b71c1c,color:#000000,font-size:16px
    class GroupRouter,GroupList,GroupCreate,GroupInvite,GroupDelete fill:#e0f7fa,stroke:#006064,color:#000000,font-size:16px
    class CalendarRouter,CalendarCourses,CalendarEvents,CalendarSave,CalendarMyTimetable fill:#f1f8e9,stroke:#33691e,color:#000000,font-size:16px
    class QuestionnaireRouter,QuestionnaireList,QuestionnairePost,QuestionnaireFill,QuestionnaireMy fill:#fff3e0,stroke:#e65100,color:#000000,font-size:16px
    class MaterialsRouter,MaterialsUpload,MaterialsDownload,MaterialsList fill:#ede7f6,stroke:#4527a0,color:#000000,font-size:16px
    class AdminRouter,AdminPendingAccounts,AdminApproveAccount,AdminRejectAccount,AdminUsers,AdminStats fill:#fce4ec,stroke:#880e4f,color:#000000,font-size:16px
    class ProfileRouter,ProfileMe,ProfileUpdate,ProfileBySid,MeRouter,MeCredits fill:#e8eaf6,stroke:#1a237e,color:#000000,font-size:16px
