## Frontend Components Reference

### Table 1: Key Frontend Components and Their Functions

| Component | File | Primary Function | Key Features |
|-----------|------|------------------|--------------|
| **App** | `App.jsx` | Root application component, routing, auth state | Authentication management, routing configuration, layout wrapper |
| **MainLayout** | `MainLayout.jsx` | Main application layout wrapper | Navigation menu, header, footer, responsive layout |
| **Login** | `Login.jsx` | User authentication interface | Login/register toggle, form validation, error handling |
| **AccountCreate** | `AccountCreate.jsx` | New user registration | Student card upload, form validation, approval submission |
| **Dashboard** | `Dashboard.jsx` | Main dashboard overview | Statistics display, quick actions, admin notifications |
| **Calendar** | `Calendar.jsx` | Timetable management | Interactive calendar, course scheduling, export functionality |
| **CourseViewer** | `CourseViewer.jsx` | Course information display | Course details, timetable, materials listing |
| **CourseEditor** | `CourseEditor.jsx` | Course management (Admin) | Course editing, timetable management, materials upload |
| **GroupFormation** | `GroupFormation.jsx` | Study group coordination | Request creation, invitation system, contact management |
| **Questionnaire** | `Questionnaire.jsx` | Survey exchange system | Credit-based posting, response tracking, progress display |
| **Materials** | `Materials.jsx` | Learning resources management | File upload/download, search functionality, course filtering |
| **Profile** | `Profile.jsx` | User profile management | Profile editing, skills management, credit display |
| **AdminPanel** | `AdminPanel.jsx` | Administrative interface | Account approval, user management, platform statistics |
| **API Utilities** | `api.js` | API communication layer | Centralized API calls, error handling, token management |

## Backend Endpoints Reference

### Table 2: Key Backend Endpoints and Their Purposes

| Endpoint | Method | Purpose | Authentication | Request/Response |
|----------|--------|---------|----------------|------------------|
| **Authentication** | | | | |
| `/api/auth/register` | POST | Register new user | None | `{sid, email, password, photoData}` → `{ok, message}` |
| `/api/auth/login` | POST | User login | None | `{email, password}` → `{ok, data: {user, token}}` |
| `/api/auth/check` | GET | Validate authentication token | Bearer Token | Headers → `{ok, data: user}` |
| **Admin** | | | | |
| `/api/admin/pending/accounts` | GET | Get pending account requests | Admin | → `{ok, data: [accounts]}` |
| `/api/admin/pending/accounts/:sid/approve` | POST | Approve account | Admin | → `{ok, message, data}` |
| `/api/admin/pending/accounts/:sid/reject` | POST | Reject account | Admin | `{reason}` → `{ok, message}` |
| `/api/admin/users` | GET | Get all users | Admin | → `{ok, data: [users]}` |
| `/api/admin/stats` | GET | Get platform statistics | Admin | → `{ok, data: stats}` |
| **Courses** | | | | |
| `/api/courses` | GET | Get all courses | Optional | → `{ok, data: {code: title}}` |
| `/api/courses/:code` | GET | Get specific course | Optional | → `{ok, data: course}` |
| `/api/courses/request` | POST | Request new course | User | `{code, title}` → `{ok, message}` |
| **Group Formation** | | | | |
| `/api/group/requests` | GET | Get all group requests | Optional | → `{ok, data: [requests]}` |
| `/api/group/requests` | POST | Create group request | User | Request data → `{ok, data, message}` |
| `/api/group/requests/:id/invite` | POST | Send invitation | User | `{message}` → `{ok, message}` |
| **Questionnaire** | | | | |
| `/api/questionnaire` | GET | Get all questionnaires | Optional | → `{ok, data: [questionnaires]}` |
| `/api/questionnaire` | POST | Create questionnaire | User | `{description, link, targetResponses}` → `{ok, data, message}` |
| `/api/questionnaire/:id/fill` | POST | Fill questionnaire | User | → `{ok, message}` |
| **Materials** | | | | |
| `/api/materials/course/:code` | POST | Upload material | Admin | `{fileData, fileName, name, description}` → `{ok, data, message}` |
| `/api/materials/download/:id` | GET | Download material | Optional | → File stream |
| **Profile** | | | | |
| `/api/profile/me` | GET | Get current profile | User | → `{ok, data: user}` |
| `/api/profile/update` | PUT | Update profile | User | Profile data → `{ok, message}` |
| `/api/profile/:sid` | GET | Get user by SID | Optional | → `{ok, data: user}` |
| **Calendar** | | | | |
| `/api/calendar/events` | GET | Get calendar events | Optional | → `{ok, data: [events]}` |
| `/api/calendar/save` | POST | Save timetable | User | `{courses}` → `{ok, message}` |
| **Upload** | | | | |
| `/api/upload/profile-photo/:fileId` | GET | Get profile photo | Optional | → Image file |
| **System** | | | | |
| `/api/health` | GET | Health check | None | → `{ok, message, timestamp}` |
| `/api/test-db` | GET | Test database connection | None | → `{ok, message}` |

---



