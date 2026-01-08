# Figure 6: Backend API Endpoints Architecture

## API Endpoints Overview

The EFS Platform backend exposes a comprehensive REST API organized around key functional domains. Each endpoint implements specific business logic with proper authentication, validation, and error handling.

```mermaid
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
    %% Endpoint Details & Flow
    %% ====================
    
    subgraph "Endpoint: POST /api/auth/register"
        Reg1["1. Request Validation<br/>Check required fields"]
        Reg2["2. Duplicate Check<br/>Verify unique SID/email"]
        Reg3["3. Password Hashing<br/>bcrypt with salt 12"]
        Reg4["4. Student Card Processing<br/>Base64 → Buffer → GridFS"]
        Reg5["5. Create Pending Account<br/>Store in pending_accounts"]
        Reg6["6. Admin Notification<br/>Email to administrator"]
        Reg7["7. Response<br/>{ok: true, message: 'Awaiting approval'}"]
        
        Reg1 --> Reg2
        Reg2 --> Reg3
        Reg3 --> Reg4
        Reg4 --> Reg5
        Reg5 --> Reg6
        Reg6 --> Reg7
    end
    
    subgraph "Endpoint: POST /api/auth/login"
        Login1["1. Credential Validation<br/>Check email/password"]
        Login2["2. User Lookup<br/>Find by email in users collection"]
        Login3["3. Password Verification<br/>bcrypt.compare()"]
        Login4["4. Token Generation<br/>crypto.randomBytes(16)"]
        Login5["5. Token Formatting<br/>'SID-randomToken'"]
        Login6["6. Update User<br/>Set new token in database"]
        Login7["7. Response<br/>{ok: true, data: {user, token}}"]
        
        Login1 --> Login2
        Login2 --> Login3
        Login3 --> Login4
        Login4 --> Login5
        Login5 --> Login6
        Login6 --> Login7
    end
    
    subgraph "Endpoint: POST /api/group/requests"
        GroupReq1["1. Authentication<br/>Bearer token validation"]
        GroupReq2["2. Validation<br/>Major field required"]
        GroupReq3["3. Duplicate Check<br/>Only one active request per user"]
        GroupReq4["4. Create Request<br/>Store in group_requests collection"]
        GroupReq5["5. Response<br/>{ok: true, data: request}"]
        
        GroupReq1 --> GroupReq2
        GroupReq2 --> GroupReq3
        GroupReq3 --> GroupReq4
        GroupReq4 --> GroupReq5
    end
    
    subgraph "Endpoint: POST /api/calendar/save"
        CalendarSave1["1. Authentication<br/>Bearer token validation"]
        CalendarSave2["2. Validation<br/>SID required"]
        CalendarSave3["3. Upsert Operation<br/>Create or update user_timetable"]
        CalendarSave4["4. Data Structure<br/>Store courses array with timestamps"]
        CalendarSave5["5. Response<br/>{ok: true, message: 'Timetable saved'}"]
        
        CalendarSave1 --> CalendarSave2
        CalendarSave2 --> CalendarSave3
        CalendarSave3 --> CalendarSave4
        CalendarSave4 --> CalendarSave5
    end
    
    subgraph "Endpoint: POST /api/questionnaire/post"
        QPost1["1. Authentication<br/>Bearer token validation"]
        QPost2["2. Validation<br/>Description and link required"]
        QPost3["3. Credit Check<br/>Verify user has ≥ 3 credits"]
        QPost4["4. Duplicate Check<br/>Only one active questionnaire per user"]
        QPost5["5. Credit Deduction<br/>Subtract 3 credits from user"]
        QPost6["6. Create Questionnaire<br/>Store in questionnaires collection"]
        QPost7["7. Response<br/>{ok: true, data: questionnaire, message: '3 credits deducted'}"]
        
        QPost1 --> QPost2
        QPost2 --> QPost3
        QPost3 --> QPost4
        QPost4 --> QPost5
        QPost5 --> QPost6
        QPost6 --> QPost7
    end
    
    subgraph "Endpoint: POST /api/materials/upload"
        MatUpload1["1. Admin Authentication<br/>Bearer token + admin role"]
        MatUpload2["2. Validation<br/>File data and filename required"]
        MatUpload3["3. Course Verification<br/>Check course exists"]
        MatUpload4["4. File Processing<br/>Base64 → Buffer conversion"]
        MatUpload5["5. GridFS Storage<br/>Upload to uploads bucket"]
        MatUpload6["6. Metadata Creation<br/>Store in materials collection"]
        MatUpload7["7. Course Update<br/>Add material reference to course"]
        MatUpload8["8. Response<br/>{ok: true, data: material, message: 'Upload successful'}"]
        
        MatUpload1 --> MatUpload2
        MatUpload2 --> MatUpload3
        MatUpload3 --> MatUpload4
        MatUpload4 --> MatUpload5
        MatUpload5 --> MatUpload6
        MatUpload6 --> MatUpload7
        MatUpload7 --> MatUpload8
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
    %% Main API structure
    APIBase --> AuthRouter
    APIBase --> GroupRouter
    APIBase --> CalendarRouter
    APIBase --> QuestionnaireRouter
    APIBase --> MaterialsRouter
    APIBase --> AdminRouter
    APIBase --> ProfileRouter
    APIBase --> MeRouter
    
    %% Registration flow connections
    AuthRegister -.-> Reg1
    Reg4 -.-> GridFSService
    Reg5 -.-> PendingAccountsCollection
    Reg6 -.-> EmailServiceNode
    
    %% Login flow connections
    AuthLogin -.-> Login1
    Login2 -.-> UsersCollection
    Login4 -.-> CryptoService
    Login3 -.-> BCryptService
    
    %% Group request connections
    GroupCreate -.-> GroupReq1
    GroupReq4 -.-> GroupRequestsCollection
    
    %% Calendar save connections
    CalendarSave -.-> CalendarSave1
    CalendarSave3 -.-> UserTimetablesCollection
    
    %% Questionnaire connections
    QuestionnairePost -.-> QPost1
    QPost3 -.-> UsersCollection
    QPost5 -.-> UsersCollection
    QPost6 -.-> QuestionnairesCollection
    
    %% Materials upload connections
    MaterialsUpload -.-> MatUpload1
    MatUpload3 -.-> CoursesCollection
    MatUpload5 -.-> GridFSService
    MatUpload6 -.-> MaterialsCollection
    MatUpload7 -.-> CoursesCollection
    
    %% Styling
    classDef category fill:#e3f2fd,stroke:#1565c0,stroke-width:2px
    classDef endpoint fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px
    classDef flow fill:#e8f5e8,stroke:#2e7d32,stroke-width:2px
    classDef database fill:#fff8e1,stroke:#ff8f00,stroke-width:2px
    classDef service fill:#e0f2f1,stroke:#00695c,stroke-width:2px
    
    class AuthRouter,GroupRouter,CalendarRouter,QuestionnaireRouter,MaterialsRouter,AdminRouter,ProfileRouter,MeRouter category
    class AuthRegister,AuthLogin,AuthCheck,GroupList,GroupCreate,GroupInvite,GroupDelete,CalendarCourses,CalendarEvents,CalendarSave,CalendarMyTimetable,QuestionnaireList,QuestionnairePost,QuestionnaireFill,QuestionnaireMy,MaterialsUpload,MaterialsDownload,MaterialsList,AdminPendingAccounts,AdminApproveAccount,AdminRejectAccount,AdminUsers,AdminStats,ProfileMe,ProfileUpdate,ProfileBySid,MeCredits endpoint
    class Reg1,Reg2,Reg3,Reg4,Reg5,Reg6,Reg7,Login1,Login2,Login3,Login4,Login5,Login6,Login7,GroupReq1,GroupReq2,GroupReq3,GroupReq4,GroupReq5,CalendarSave1,CalendarSave2,CalendarSave3,CalendarSave4,CalendarSave5,QPost1,QPost2,QPost3,QPost4,QPost5,QPost6,QPost7,MatUpload1,MatUpload2,MatUpload3,MatUpload4,MatUpload5,MatUpload6,MatUpload7,MatUpload8 flow
    class UsersCollection,PendingAccountsCollection,GroupRequestsCollection,UserTimetablesCollection,QuestionnairesCollection,MaterialsCollection,CoursesCollection,UploadsFilesCollection,UploadsChunksCollection database
    class EmailServiceNode,CryptoService,BCryptService,GridFSService service
