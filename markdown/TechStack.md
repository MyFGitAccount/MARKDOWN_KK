#  Project Stack & Cost Overview

##  Tech Stack: MERN

| Layer        | Technology                      | Notes                                 |
| ------------ | ------------------------------- | ------------------------------------- |
| **Database** | MongoDB (Atlas)                 | Cloud-hosted, scalable NoSQL database |
| **Backend**  | Express.js                      | Lightweight Node.js framework         |
| **Frontend** | React                           | Component-based UI library            |
| **Runtime**  | Node.js                         | Fast, event-driven JavaScript runtime |
| **Forum**    | Discourse (self-hosted or paid) | Robust community platform             |

---

##  Potential Cost Breakdown

| Category               | Option(s)                | Estimated Monthly Cost (USD)/(HKD)        | Notes(USD)                                                                                                                               |
| ---------------------- | ------------------------ | ----------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| **Computers**          | Three laptops            | **$848/$6592**                            | Lenovo IdeaPad 3 (282.85*3)                                                                                                              |
| **Server & Hosting**   | **DigitalOcean**         | **$12/$93**                               | Basic Droplet: 1 vCPU, 2 GB RAM, 50 GB SSD<br>→ Docker deployment adds **no extra cost**<br>Use `docker-compose.yml` for one-click setup |
|                        | **Hetzner**              | **$4/$31**                                | CX11 VPS: 1 vCPU, 2 GB RAM, 20 GB SSD<br>Cheapest Docker-compatible option                                                               |
| **Database**           | **MongoDB Atlas**        | **$0** (M0 free)<br>**$9+/$70+** (M2/M5)  | M0: 512 MB shared<br>M2 ($9/mo): 2 GB<br>M5 ($25/mo): 5 GB                                                                               |
|                        | **Supabase**             | **$0** (free)<br>**$25+/$194+** (Pro)     | Free: 500 MB DB<br>Pro ($25/mo): 8 GB                                                                                                    |
| **Forum**              | **Discourse**            | **$0** (self-hosted)<br>**$100** (hosted) | Official Docker image → `docker pull discourse/discourse`<br>Zero cost when self-hosted on your VPS                                      |
| **Email Verification** | **Gmail SMTP**           | **$0**                                    | ~500 emails/day limit<br>Works perfectly in Docker with environment variables                                                            |
|                        | **SendPulse**            | **$0**                                    | 12,000 emails/month free                                                                                                                 |
| **Domain Name**        | **Namecheap**            | **$1–$2/$8-$16**                          | `.com` ≈ $10–15/year (first year often $1)                                                                                               |
|                        | **Cloudflare Registrar** | **$1–$2/$8-$16**                          | `.com` ≈ $10/year + free DNS/security                                                                                                    |
| **Backup & Storage**   | **AWS S3**               | **$0.005/$0.04** <br>(10 GB)              | $0.005/GB/month                                                                                                                          |
|                        | **IDrive**               | **$0** (10 GB)                            | **cheapest option (free!)**                                                                                                              |
|                        |                          |                                           | **total: $853-987<br> (The first month)    <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: $5-145 (per month)**                          |

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
  B --> B7[Contact with supervisor]

  Root --> C[Member C - Integration, Testing & Admin Tools]
  C --> C1[Discourse Forum Integration]
  C --> C2[Email Verification System]
  C --> C3[Admin Dashboard Interface]
  C --> C4[Search & Filter Tools]
  C --> C5[Testing & Validation]
  C --> C6[Deployment & Documentation]
```
 
---

## WorkFlow
```mermaid
gantt
    title EFS Development Schedule (Sep 2025 – Apr 2026)
    dateFormat  YYYY-MM-DD
    axisFormat  %m/%Y
    tickInterval 1month
    todayMarker stroke-width:4px,stroke:#e74c3c,opacity:0.9

    section Phase 1: Planning & Setup (Oct–Nov)
    Project Planning & Research                 :done, plan1, 2025-10-01, 2025-10-15
    Learn MERN Stack + Discourse SSO            :done, learn1, after plan1, 15d
    Setup Dev Environment (VS Code, Docker)     :done, setup1, after learn1, 7d
    Initialize MongoDB Schema                   :done, db1, after setup1, 10d
    Configure Frontend & Backend Frameworks     :done, config1, after db1, 10d

    section Phase 2: Core System (Nov–Dec)
    Develop Login & Registration UI             :done, auth1, 2025-11-10, 18d
    Implement Course Page & Repository          :done, repo1, after auth1, 20d
    Create Admin Dashboard & Moderation         :done, admin1, after repo1, 18d

    section Examination Break
    Semester Exam Period – NO DEVELOPMENT       :crit, exam, 2025-12-15, 2026-01-12

    section Phase 3: Interactive Tools & Collaboration (Jan–Feb)
    Flashcards, Matching Games, Assessments     :active, tools1, 2026-01-13, 25d
    Articles Section + Markdown Editor          :active, articles1, after tools1, 12d
    Discourse SSO + Forum Integration           :active, forum1, after articles1, 18d
    Timetable Matching & Groupmate Finder       :active, match1, after forum1, 20d

    section Phase 4: Finalization & Deployment (Mar–Apr)
    Full Testing (Cypress + Load Testing)       :test1, 2026-03-10, 20d
    Performance Optimization                    :perf1, after test1, 10d
    Accessibility Audit (WCAG 2.1 AA)           :audit1, after perf1, 7d
    Deployment + Launch Event                   :milestone, launch, 2026-04-10, 1d
    Final Documentation & Handover              :handover1, after launch, 15d

    section Final Submission
    Project Submission to HKU SPACE             :crit, milestone, submit, 2026-04-26, 1d
```
---
