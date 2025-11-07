```mermaid
gantt
    title EFS Revised Schedule – 3 Features Only (Nov 2025 – Apr 2026)
    dateFormat  YYYY-MM-DD
    axisFormat  %m/%Y
    tickInterval 1month
    todayMarker stroke-width:4px,stroke:#e74c3c,opacity:0.9

    section Phase 1: Core Setup & Login & Timetable Planner (Nov - Dec)
    Project Re-scoping & Planning               :done, plan1, 2025-11-01, 2025-11-07
    MERN Stack Setup                            :done, setup1, after plan1, 2d
    Secure Login + Photo Verification           :done, auth1, after setup1, 2d
    Admin Dashboard (Approval + Moderation)     :done, admin1, after auth1, 2d
    Drag & Drop Timetable Grid                  :active, timetable1, after admin1, 10d
    Course Block Database + Clash Detection     :active, clash1, after timetable1, 10d
    Save/Export Timetable (PNG/PDF)             :active, export1, after clash1, 1d

    section Examination Break
    Semester Exam Period                        :crit, exam, 2025-12-15, 2026-01-12

    section Phase 2: Groupmate formation system (Dec - Jan)
    Contribution-Gated Group System             :active, group1, 2026-01-12, 20d

    section Phase 3: Questionnaire System (Jan - Feb)
    Token System (Fill = Earn 3 Tokens)         :active, token1, 2026-01-12, 10d
    Share Questionnaire (Costs 3 Tokens)        :active, share1, after token1, 5d
    Course-Specific Questionnaire Board         :active, board1, after share1, 5d

    section Phase 4: Final Polish & Testing (Feb–Apr)
    Full Testing                                :active, test1, 2026-02-01, 5d
    Deployment + Launch Event                   :milestone, launch, after test1, 5d 
    Final Documentation & Handover              :active, handover1, after launch, 45d

    section Final Submission                    
    Project Submission to HKU SPACE             :crit, submit, 2026-04-26
