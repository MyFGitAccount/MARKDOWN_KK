#  Project Stack & Cost Overview

##  Tech Stack: MERN

| Layer        | Technology               | Notes                                  |
|--------------|---------------------------|----------------------------------------|
| **Database** | MongoDB (Atlas)           | Cloud-hosted, scalable NoSQL database  |
| **Backend**  | Express.js                | Lightweight Node.js framework          |
| **Frontend** | React                     | Component-based UI library             |
| **Runtime**  | Node.js                   | Fast, event-driven JavaScript runtime  |
| **Forum**    | Discourse (self-hosted or paid) | Robust community platform         |

---

##  Potential Cost Breakdown

| Category               | Option(s)                                      | Notes                                                                 |
|------------------------|------------------------------------------------|-----------------------------------------------------------------------|
| **Server & Hosting**   | DigitalOcean, AWS, Hetzner                     | VPS providers for backend and forum hosting                          |
| **Database**           | MongoDB Atlas                                  | Free tier: 512 MB; paid plans for scaling                            |
| **Forum**              | Discourse                                      | Free if self-hosted; paid if hosted by Discourse.org                 |
| **Email Verification** | Gmail SMTP, SendPulse                          | Gmail: ~500 emails/day; SendPulse: 12,000/month free tier            |
| **Domain Name**        | Namecheap, Cloudflare                          | Optional, depending on branding needs                                |
| **Backup & Storage**   | AWS S3, Backblaze, local storage               | For file uploads, student cards, and forum backups                   |

---

## Role Breakdown
```mermaid
graph TD
  Root[HKU SPACE Learning Platform Project]

  Root --> A[Member A - Backend & Infrastructure]
  A --> A1[Authentication System]
  A1 --> A1a[Login with Course Code Validation]
  A1 --> A1b[First-Time User Registration Flow]
  A --> A2[Database Schema Design]
  A --> A3[Admin Dashboard Backend]
  A --> A4[Points & Rating Logic]
  A --> A5[Timetable Matching & Groupmate Finder]
  A --> A6[API for Material Upload & Retrieval]

  Root --> B[Member B - Frontend & User Experience]
  B --> B1[Login & Registration UI]
  B --> B2[Course Page Interface]
  B2 --> B2a[Material Repository Viewer]
  B2 --> B2b[Interactive Tools - Flashcards, Matching Games]
  B --> B3[Articles & Forum UI]
  B --> B4[Rating Interface]
  B --> B5[Responsive Design & Accessibility]
  B --> B6[User Profile & Avatar System]

  Root --> C[Member C - Integration, Testing & Admin Tools]
  C --> C1[Discourse Forum Integration]
  C --> C2[Email Verification System]
  C --> C3[Admin Dashboard Interface]
  C --> C4[Search & Filter Tools]
  C --> C5[Testing & Validation]
  C --> C6[Deployment & Documentation]
 
--
## WorkFlow
```mermaid
graph TD
  Start[Setup Environment] --> Setup1[Initialize Database Schema]
  Setup1 --> Setup2[Configure Frontend and Backend Frameworks]
  Progress0 --> Progress1[Develop Login and Registration UI]
  Progress1 --> Progress2[Implement Course Page and Material Repository]
  Progress2 --> Progress3[Build Interactive Tools - Flashcards, Matching Games, Assessments]
  Progress3 --> Progress4[Integrate Points and Rating System]
  Progress4 --> Progress5[Create Admin Dashboard and Moderation Tools]
  Progress5 --> Progress6[Add Articles and Forum Sections]
  Progress6 --> Progress7[Develop Timetable Matching and Groupmate Finder]
  Progress7 --> Finalize[Testing, Optimization, and Deployment]
--
