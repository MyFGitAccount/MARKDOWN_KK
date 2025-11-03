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

### Role Breakdown
```mermaid
graph TD
  A[Project Lead] --> A1[System Architecture]
  A --> A2[Backend Development]
  A --> A3[Database Design]
  A --> A4[Admin Dashboard]

  B[Frontend Developer] --> B1[Login & Registration UI]
  B --> B2[Course Page Interface]
  B --> B3[Interactive Tools (Flashcards, Games)]
  B --> B4[Responsive Design & Accessibility]

  C[Platform Integrator & QA] --> C1[Discourse Forum Integration]
  C --> C2[Timetable Matching & Groupmate Finder]
  C --> C3[Testing & Validation]
  C --> C4[Deployment & Documentation]
 
