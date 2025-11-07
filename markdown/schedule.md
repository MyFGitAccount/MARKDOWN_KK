```mermaid
gantt
    title EFS Revised Schedule – 3 Features Only (Nov 2025 – Apr 2026)
    dateFormat  YYYY-MM-DD
    axisFormat  %m/%Y
    tickInterval 1month
    todayMarker stroke-width:1px,stroke:#e74c3c,opacity:0.9,font-size:small


    section Phase 1: Setup (Nov–Dec)
    Re-scoping & Planning                     :done, plan1, 2025-11-01, 2025-11-07
    MERN Stack Setup                          :done, setup1, after plan1, 2d
    Secure Login + Photo Verification         :done, auth1, after setup1, 2d
    Admin Dashboard                           :done, admin1, after auth1, 2d
    Timetable Grid (Drag & Drop)              :active, timetable1, after admin1, 10d
    Clash Detection                           :active, clash1, after timetable1, 10d
    Save/Export Timetable                     :active, export1, after clash1, 1d

    section Examination Break
    Semester Exam Period – NO DEVELOPMENT     :crit, exam, 2025-12-15, 2026-01-12

    section Phase 2: Find Groupmate System (Jan 2026)
    Contribution-Gated Matching               :active, group1, 2026-01-13, 20d
    Sample Upload + Auto-Match                :active, timer1, after group1, 10d
    Private Group Chat                        :active, chat1, after timer1, 7d

    section Phase 3: Questionnaire System (Jan–Feb 2026)
    Token System                              :token1, 2026-01-20, 10d
    Share Questionnaire                       :share1, after token1, 5d
    Response Board                            :board1, after share1, 5d

    section Phase 4: Polish & Launch (Feb–Apr 2026)
    Full Testing (Cypress + Load)             :test1, 2026-02-10, 10d
    Mobile Optimization                       :mobile1, after test1, 7d
    Performance + Accessibility (WCAG 2.1 AA) :perf1, after mobile1, 7d
    Deployment + Launch Event                 :milestone, launch, 2026-04-10, 1d
    Final Documentation & Handover            :handover1, after launch, 15d

    section Final Submission
    Project Submission to HKU SPACE           :crit, milestone, submit, 2026-04-26, 1d
``mermaid
gantt
    title EFS Revised Schedule – 3 Features Only (Nov 2025 – Apr 2026)
    dateFormat  YYYY-MM-DD
    axisFormat  %m/%Y
    tickInterval 1month
    todayMarker stroke-width:1px,stroke:#e74c3c,opacity:0.9,font-size:small

    section Phase 1: Setup & Timetable Planner (Nov–Dec 2025)
    Re-scoping & Planning                     :done, plan1, 2025-11-01, 2025-11-07
    MERN Stack Setup                          :done, setup1, after plan1, 2d
    Secure Login + Photo Verification         :done, auth1, after setup1, 2d
    Admin Dashboard                           :done, admin1, after auth1, 2d
    Timetable Grid (Drag & Drop)              :active, timetable1, after admin1, 10d
    Clash Detection                           :active, clash1, after timetable1, 10d
    Save/Export Timetable                     :active, export1, after clash1, 1d

    section Examination Break
    Semester Exam Period – NO DEVELOPMENT     :crit, exam, 2025-12-15, 2026-01-12

    section Phase 2: Find Groupmate System (Jan 2026)
    Contribution-Gated Matching               :active, group1, 2026-01-13, 20d
    Sample Upload + Auto-Match                :active, timer1, after group1, 10d
    Private Group Chat                        :active, chat1, after timer1, 7d

    section Phase 3: Questionnaire System (Jan–Feb 2026)
    Token System                              :token1, 2026-01-20, 10d
    Share Questionnaire                       :share1, after token1, 5d
    Response Board                            :board1, after share1, 5d

    section Phase 4: Polish & Launch (Feb–Apr 2026)
    Full Testing (Cypress + Load)             :test1, 2026-02-10, 10d
    Mobile Optimization                       :mobile1, after test1, 7d
    Performance + Accessibility (WCAG 2.1 AA) :perf1, after mobile1, 7d
    Deployment + Launch Event                 :milestone, launch, 2026-04-10, 1d
    Final Documentation & Handover            :handover1, after launch, 15d

    section Final Submission
    Project Submission to HKU SPACE           :crit, milestone, submit, 2026-04-26, 1d