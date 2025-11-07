mermaid
```gantt
    title EFS Revised Schedule – 3 Features Only (Nov 2025 – Apr 2026)
    dateFormat  YYYY-MM-DD
    axisFormat  %m/%Y
    tickInterval 1month
    todayMarker stroke-width:5px,stroke:#e74c3c,opacity:0.9

    section Phase 1: Setup & Timetable (Nov–Dec)
    Re-scoping & Planning                        :done, plan1, 2025-11-01, 2025-11-07
    MERN Stack Setup                             :done, setup1, after plan1, 2d
    Secure Login + Photo Verification            :done, auth1, after setup1, 2d
    Admin Dashboard                              :done, admin1, after auth1, 2d
    Timetable Grid (Drag & Drop)                 :active, timetable1, after admin1, 10d
    Clash Detection                              :active, clash1, after timetable1, 10d
    Save/Export Timetable                        :active, export1, after clash1, 1d

    section Examination Break
    Semester Exam Period                         :crit, exam, 2025-12-15, 2026-01-12

    section Phase 2: Groupmate System (Jan)
    Contribution-Gated Matching                  :active, group1, 2026-01-13, 20d
    Sample Upload + Auto-Match                   :active, timer1, after group1, 10d
    Private Group Chat                           :active, chat1, after timer1, 7d

    section Phase 3: Questionnaire System (Jan–Feb)
    Token System                                 :active, token1, 2026-01-20, 10d
    Share Questionnaire                          :active, share1, after token1, 5d
    Response Board                               :active, board1, after share1, 5d

    section Phase 4: Polish & Launch (Feb–Apr)
    Full Testing                                 :active, test1, 2026-02-10, 10d
    Mobile Optimization                          :active, mobile1, after test1, 7d
    Performance + Accessibility                  :active, perf1, after mobile1, 7d
    Deployment + Launch                          :milestone, launch, 2026-04-10
    Final Documentation & Handover               :active, handover1, after launch, 15d

    section Final Submission
    Project Submission to HKU SPACE              :crit, submit, 2026-04-26
```
