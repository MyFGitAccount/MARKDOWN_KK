```mermaid
gantt
    title EFS Development Schedule (Sep 2025 – Apr 2026)
    dateFormat  YYYY-MM-DD
    axisFormat  %m/%Y
    tickInterval 1month
    todayMarker off

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
    Deployment + Launch Event                   :milestone, launch, 2026-04-10
    Final Documentation & Handover              :handover1, after launch, 15d

    section Final Submission
    Project Submission to HKU SPACE             :crit, milestone, submit, 2026-04-26