 STUDENT TRANSCRIPT DATABASE - Complete Project Design

## 1. DATABASE SCHEMA OVERVIEW

### Complete Table Structure with Sample Data

| **Table Name** | **Field Name** | **Data Type** | **Constraints** | **Description** | **Sample Data** |
|----------------|----------------|---------------|-----------------|-----------------|-----------------|
| **Students** | student_id | INTEGER | PRIMARY KEY AUTOINCREMENT | Unique system ID | 10001 |
| | hkid | TEXT | UNIQUE NOT NULL | Hong Kong ID Card | Y1234567 |
| | full_name | TEXT | NOT NULL | Student full name | CHAN Tai Man |
| | english_name | TEXT | | English preferred name | Tommy Chan |
| | date_of_birth | DATE | NOT NULL | Date of birth | 2003-05-15 |
| | gender | TEXT | CHECK('M','F','Other') | Gender | M |
| | email | TEXT | UNIQUE NOT NULL | University email | tmchan@student.hku.hk |
| | phone | TEXT | | Contact number | 91234567 |
| | address | TEXT | | Residential address | Flat A, 123 Nathan Rd, HK |
| | enrollment_date | DATE | NOT NULL | First enrollment date | 2022-09-01 |
| | status | TEXT | DEFAULT 'Active' | Active/Graduated/Suspended | Active |
| | nationality | TEXT | | Nationality | Chinese (HK) |
| | previous_institution | TEXT | | High school/previous uni | Queen's College |

| **Table Name** | **Field Name** | **Data Type** | **Constraints** | **Description** | **Sample Data** |
|----------------|----------------|---------------|-----------------|-----------------|-----------------|
| **Programs** | program_id | INTEGER | PRIMARY KEY AUTOINCREMENT | Unique program code | 101 |
| | program_code | TEXT | UNIQUE NOT NULL | Official program code | BBA-ACCT |
| | program_name | TEXT | NOT NULL | Full program name | Bachelor of Business Administration in Accounting |
| | degree_level | TEXT | NOT NULL | Bachelor/Master/PhD | Bachelor |
| | department | TEXT | NOT NULL | Offering department | School of Business |
| | faculty | TEXT | NOT NULL | Faculty name | Faculty of Business and Economics |
| | total_credits_required | INTEGER | NOT NULL | Credits to graduate | 120 |
| | duration_years | INTEGER | NOT NULL | Normal study period | 4 |
| | medium_of_instruction | TEXT | | English/Cantonese/Mandarin | English |
| | accreditation_body | TEXT | | Professional accreditation | HKICPA |
| | program_leader | TEXT | | Program director name | Prof. Wong Siu Ming |

| **Table Name** | **Field Name** | **Data Type** | **Constraints** | **Description** | **Sample Data** |
|----------------|----------------|---------------|-----------------|-----------------|-----------------|
| **Courses** | course_code | TEXT | PRIMARY KEY | Official course code | ACCT3101 |
| | course_title | TEXT | NOT NULL | Full course name | Intermediate Financial Accounting |
| | course_description | TEXT | | Detailed description | This course covers... |
| | credit_hours | DECIMAL(3,1) | NOT NULL | Credit value | 3.0 |
| | level | INTEGER | | Year 1/2/3/4 | 3 |
| | department | TEXT | | Offering department | Accounting |
| | instructor | TEXT | | Lecturer name | Dr. Lee Ka Ho |
| | semester | TEXT | | Fall/Spring/Summer | Fall |
| | academic_year | TEXT | | e.g., 2024-25 | 2024-25 |
| | max_capacity | INTEGER | | Class size limit | 80 |
| | current_enrollment | INTEGER | DEFAULT 0 | Enrolled students | 65 |
| | available_seats | INTEGER | | Calculated field | 15 |
| | status | TEXT | DEFAULT 'Active' | Active/Archived/Cancelled | Active |
| | syllabus_url | TEXT | | Link to syllabus | /syllabi/ACCT3101.pdf |

| **Table Name** | **Field Name** | **Data Type** | **Constraints** | **Description** | **Sample Data** |
|----------------|----------------|---------------|-----------------|-----------------|-----------------|
| **Prerequisites** | prerequisite_id | INTEGER | PRIMARY KEY AUTOINCREMENT | Auto ID | 1 |
| | course_code | TEXT | FOREIGN KEY | Advanced course | ACCT3101 |
| | required_course_code | TEXT | FOREIGN KEY | Prerequisite course | ACCT2101 |
| | minimum_grade | TEXT | | Minimum grade required | C+ |
| | is_corequisite | BOOLEAN | DEFAULT 0 | Can take together? | 0 |

| **Table Name** | **Field Name** | **Data Type** | **Constraints** | **Description** | **Sample Data** |
|----------------|----------------|---------------|-----------------|-----------------|-----------------|
| **Student_Programs** | student_program_id | INTEGER | PRIMARY KEY AUTOINCREMENT | Auto ID | 5001 |
| | student_id | INTEGER | FOREIGN KEY REFERENCES Students | Student | 10001 |
| | program_id | INTEGER | FOREIGN KEY REFERENCES Programs | Program | 101 |
| | admission_date | DATE | NOT NULL | Program start date | 2022-09-01 |
| | graduation_date | DATE | | Expected/actual graduation | 2026-06-30 |
| | status | TEXT | NOT NULL | Active/Completed/Dropped | Active |
| | current_year_of_study | INTEGER | | 1/2/3/4/5 | 3 |
| | academic_advisor | TEXT | | Staff assigned | Dr. Chan Mei Ling |
| | scholarship_holder | BOOLEAN | DEFAULT 0 | Scholarship status | 1 |
| | exchange_program | TEXT | | Outbound exchange details | N/A |

| **Table Name** | **Field Name** | **Data Type** | **Constraints** | **Description** | **Sample Data** |
|----------------|----------------|---------------|-----------------|-----------------|-----------------|
| **Enrollments** | enrollment_id | INTEGER | PRIMARY KEY AUTOINCREMENT | Unique ID | 50001 |
| | student_id | INTEGER | FOREIGN KEY REFERENCES Students | Student | 10001 |
| | course_code | TEXT | FOREIGN KEY REFERENCES Courses | Course | ACCT3101 |
| | program_id | INTEGER | FOREIGN KEY REFERENCES Programs | Program enrolled under | 101 |
| | enrollment_date | DATE | NOT NULL | Date registered | 2025-01-10 |
| | enrollment_status | TEXT | NOT NULL | Enrolled/Dropped/Withdrawn | Enrolled |
| | grade_letter | TEXT | | A+, A, A-, B+, etc. | B+ |
| | grade_points | DECIMAL(3,2) | | 4.0, 3.7, 3.3, etc. | 3.3 |
| | percentage_score | DECIMAL(5,2) | | 0-100 | 78.5 |
| | is_repeat | BOOLEAN | DEFAULT 0 | Previously failed? | 0 |
| | previous_grade | TEXT | | If repeating | NULL |
| | semester | TEXT | NOT NULL | Semester taken | Fall |
| | academic_year | TEXT | NOT NULL | Year taken | 2025-26 |
| | instructor | TEXT | | Course instructor | Dr. Lee Ka Ho |
| | remarks | TEXT | | Additional notes | Good performance |

| **Table Name** | **Field Name** | **Data Type** | **Constraints** | **Description** | **Sample Data** |
|----------------|----------------|---------------|-----------------|-----------------|-----------------|
| **Grade_Scale** | grade_scale_id | INTEGER | PRIMARY KEY AUTOINCREMENT | 1 |
| | grade_letter | TEXT | UNIQUE NOT NULL | A+ |
| | grade_points | DECIMAL(3,2) | NOT NULL | 4.3 (HK system) / 4.0 (US) | 4.3 |
| | minimum_percentage | INTEGER | | 85 |
| | maximum_percentage | INTEGER | | 100 |
| | description | TEXT | | Excellent |
| | is_passing | BOOLEAN | DEFAULT 1 | 1 |

| **Table Name** | **Field Name** | **Data Type** | **Constraints** | **Description** | **Sample Data** |
|----------------|----------------|---------------|-----------------|-----------------|-----------------|
| **Transcripts** | transcript_id | INTEGER | PRIMARY KEY AUTOINCREMENT | Auto ID | 1001 |
| | student_id | INTEGER | FOREIGN KEY REFERENCES Students | Student | 10001 |
| | generated_date | DATE | NOT NULL | Issue date | 2026-01-15 |
| | generated_by | TEXT | | Staff who generated | Registrar Office |
| | cumulative_gpa | DECIMAL(3,2) | | Overall GPA | 3.45 |
| | total_credits_attempted | INTEGER | | Sum of credits | 90 |
| | total_credits_earned | INTEGER | | Passed credits | 87 |
| | transcript_type | TEXT | | Official/unofficial | Official |
| | purpose | TEXT | | Job application, further study | Job application |
| | pdf_file_path | TEXT | | Storage location | /transcripts/2026/1001.pdf |
| | verification_code | TEXT | UNIQUE | For authentication | TR-2026-1001-ABCD |
| | is_sealed | BOOLEAN | DEFAULT 0 | Official seal | 1 |

| **Table Name** | **Field Name** | **Data Type** | **Constraints** | **Description** | **Sample Data** |
|----------------|----------------|---------------|-----------------|-----------------|-----------------|
| **Transcript_Items** | transcript_item_id | INTEGER | PRIMARY KEY AUTOINCREMENT | Auto ID | 500001 |
| | transcript_id | INTEGER | FOREIGN KEY REFERENCES Transcripts | Parent transcript | 1001 |
| | enrollment_id | INTEGER | FOREIGN KEY REFERENCES Enrollments | Enrollment record | 50001 |
| | course_code | TEXT | | Denormalized for efficiency | ACCT3101 |
| | course_title | TEXT | | Denormalized | Intermediate Financial Accounting |
| | credits | DECIMAL(3,1) | | Denormalized | 3.0 |
| | grade_letter | TEXT | | Grade at transcript time | B+ |
| | grade_points | DECIMAL(3,2) | | Grade points at transcript time | 3.3 |
| | semester | TEXT | | When taken | Fall |
| | academic_year | TEXT | | Year taken | 2025-26 |
| | sequence_order | INTEGER | | Display order | 1 |

| **Table Name** | **Field Name** | **Data Type** | **Constraints** | **Description** | **Sample Data** |
|----------------|----------------|---------------|-----------------|-----------------|-----------------|
| **Users** | user_id | INTEGER | PRIMARY KEY AUTOINCREMENT | System user | 100 |
| | username | TEXT | UNIQUE NOT NULL | Login ID | rchan |
| | password_hash | TEXT | NOT NULL | Encrypted | 5f4dcc3b5aa765d61d8327deb882cf99 |
| | role | TEXT | NOT NULL | Admin/Registrar/Instructor/Student | Registrar |
| | staff_id | TEXT | | If staff | S-2024-001 |
| | student_id | INTEGER | FOREIGN KEY | If student | 10001 |
| | last_login | TIMESTAMP | | Audit | 2026-01-15 09:30:00 |
| | account_status | TEXT | DEFAULT 'Active' | Active/Locked | Active |

| **Table Name** | **Field Name** | **Data Type** | **Constraints** | **Description** | **Sample Data** |
|----------------|----------------|---------------|-----------------|-----------------|-----------------|
| **Audit_Log** | log_id | INTEGER | PRIMARY KEY AUTOINCREMENT | Auto ID | 5000001 |
| | user_id | INTEGER | FOREIGN KEY REFERENCES Users | Who performed action | 100 |
| | action_type | TEXT | | INSERT/UPDATE/DELETE/VIEW | UPDATE |
| | table_name | TEXT | | Affected table | Enrollments |
| | record_id | INTEGER | | Primary key of record | 50001 |
| | old_value | TEXT | | JSON of old data | {"grade":null} |
| | new_value | TEXT | | JSON of new data | {"grade":"B+"} |
| | ip_address | TEXT | | User IP | 10.12.34.56 |
| | timestamp | TIMESTAMP | DEFAULT CURRENT_TIMESTAMP | When | 2026-01-15 14:23:45 |

---

## 2. USER REQUIREMENTS

### A. Functional Requirements

#### Student Requirements:
1. **View Transcript**: Generate and view unofficial transcript anytime
2. **Check GPA**: Calculate current semester GPA and cumulative GPA
3. **Course Registration**: View available courses and register
4. **Graduation Audit**: Check progress toward degree completion
5. **Grade Viewing**: Access individual course grades when released
6. **Academic History**: View complete enrollment history
7. **Personal Info**: Update contact information

#### Instructor Requirements:
1. **Grade Entry**: Input final grades for courses taught
2. **Roster Management**: View enrolled students list
3. **Grade Modification**: Change grades with approval workflow
4. **Course Management**: Submit course syllabi and materials
5. **Student Progress**: View academic standing of advisees

#### Registrar/Admin Requirements:
1. **Transcript Generation**: Produce official transcripts with verification
2. **Enrollment Management**: Override registration restrictions
3. **Academic Standing**: Identify at-risk students (GPA < 2.0)
4. **Graduation Processing**: Verify completion for graduation
5. **Course Creation**: Add/modify course catalog
6. **Program Management**: Define/update program requirements
7. **Grade Scale Maintenance**: Update grading policies
8. **Reporting**: Generate institutional reports (enrollment trends, grade distribution)
9. **Data Import**: Batch import student records and grades
10. **Audit Trail**: Review all grade changes and transcript requests

### B. Non-Functional Requirements

1. **Accuracy**: GPA calculations must be 100% accurate
2. **Security**: Student data must be protected; role-based access control
3. **Auditability**: All grade changes must be logged
4. **Performance**: Transcript generation < 5 seconds
5. **Scalability**: Support 20,000+ students, 1M+ enrollment records
6. **Availability**: System available 24/7 (except maintenance)
7. **Data Integrity**: No orphaned records; referential integrity
8. **Compliance**: Meet HK PDPO (Personal Data Privacy Ordinance)
9. **Backup**: Daily automated backups

---

## 3. DATABASE DESIGN DOCUMENT

### Entity-Relationship Model Description

```
Students (1) -----< (M) Student_Programs >----- (1) Programs
   |                                                |
   |                                                |
   +-------< (M) Enrollments >---------------------+
   |                 |
   |                 +----< (M) Transcript_Items
   |                 |
   +--------------< (M) Transcripts
                       |
                       +----< (M) Transcript_Items

Courses (1) -----< (M) Enrollments
   |
   +-----< (M) Prerequisites >----- (1) Courses (as required course)

Grade_Scale (1) -----< (M) Enrollments (via grade_letter reference)
```

### Business Rules

1. **Student Identity**: Each student has unique HKID and student email
2. **Program Enrollment**: Student must be enrolled in at least one program
3. **Course Registration**: Student can only register for courses if prerequisites met with minimum grade
4. **Grade Assignment**: Each enrollment must have NULL grade until finalized, then assigned valid grade letter from Grade_Scale
5. **GPA Calculation**: GPA = Σ(credit_hours × grade_points) / Σ(credit_hours) for courses with grades
6. **Graduation**: Student can graduate when:
   - Completed all required courses
   - Earned ≥ total_credits_required
   - Cumulative GPA ≥ minimum requirement (typically 2.0)
   - No outstanding academic obligations

7. **Transcript Integrity**: Once transcript is generated as "Official", the grade snapshot is preserved even if grades later changed
8. **Audit Requirement**: All grade changes require audit trail with reason code
9. **Academic Standing**: 
   - Good Standing: GPA ≥ 2.0
   - Academic Warning: GPA 1.7-1.99
   - Probation: GPA 1.5-1.69
   - Required to Withdraw: GPA < 1.5 for two consecutive semesters

### Data Dictionary Summary

| **Entity** | **Description** | **Volumetrics** | **Growth Rate** |
|------------|-----------------|-----------------|-----------------|
| Students | All enrolled persons | 15,000 | +3,000/year |
| Programs | Academic programs offered | 150 | +5/year |
| Courses | Course catalog | 2,500 | +100/year |
| Enrollments | Course registrations | 150,000/year | 10%/year |
| Transcripts | Generated official transcripts | 5,000/year | 5%/year |

---

## 4. IMPLEMENTATION NOTES

### Critical Queries to Implement

1. **Calculate Cumulative GPA**
```sql
SELECT s.student_id, s.full_name,
       SUM(e.credit_hours * g.grade_points) / SUM(e.credit_hours) AS cumulative_gpa,
       SUM(e.credit_hours) AS total_credits_attempted,
       SUM(CASE WHEN g.is_passing = 1 THEN e.credit_hours ELSE 0 END) AS credits_earned
FROM Students s
JOIN Enrollments e ON s.student_id = e.student_id
JOIN Grade_Scale g ON e.grade_letter = g.grade_letter
WHERE s.student_id = 10001
AND e.enrollment_status = 'Enrolled'
AND e.grade_letter IS NOT NULL;
```

2. **Check Graduation Eligibility**
```sql
-- Complex query checking program requirements vs completed courses
```

### Suggested Project Timeline

| **Week** | **Tasks** |
|----------|----------|
| 1-2 | Collect real forms from university registrar; identify exact data fields |
| 3-4 | Create ER diagram; define all tables and relationships |
| 5-6 | Implement SQLite database; create all tables with constraints |
| 7-8 | Populate with sample data (minimum 10 students, 20 courses, 50 enrollments) |
| 9-10 | Develop key queries; implement views for transcript generation |
| 11-12 | Create report formats; prepare presentation |
| 13 | Final testing and submission |

### Sample Input Form References

You should collect these forms from your university:
1. **Course Add/Drop Form** - shows what fields needed for enrollment
2. **Transcript Request Form** - shows information needed for transcript generation
3. **Graduation Application Form** - shows graduation requirements
4. **Grade Appeal Form** - shows audit trail requirements
5. **Student Registration Form** - shows personal information needed

---

## 5. DELIVERABLES CHECKLIST

| **Deliverable** | **Status** | **Notes** |
|-----------------|-----------|----------|
| ER Diagram | ✅ | Include cardinalities and constraints |
| Table Creation Scripts | ✅ | SQLite compatible |
| Sample Data Population | ✅ | 10+ students with realistic data |
| GPA Calculation Function | ✅ | Accurate with HK grading scale |
| Transcript Generation View | ✅ | Format similar to real transcript |
| Enrollment Validation Triggers | ✅ | Check prerequisites, capacity |
| Audit Log Triggers | ✅ | For grade modifications |
| Graduation Audit Query | ✅ | Check degree completion |
| User Interface/Forms | Optional | If required by instructor |
| Presentation Slides | ✅ | 20-30 minutes |
| Project Report | ✅ | 1500-2000 words |

