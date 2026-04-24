# EFS Platform Oral Presentation Slides

## CCIT4080 – Project on Knowledge Product Development
### CL15 | Group 07

**Group Members:**
- Xavier Wong (20296532)
- Kwok Ho Yin (20293303)
- Young Ho Tim (20293048)

**Supervisor:** Mr. Lau Chung Yin (Tim)

---

## SLIDE 1: TITLE SLIDE

**Image Placeholder:** [EFS Logo - Simple icon showing calendar connected to people and survey form]

**Text:**

CCIT4080 – Project on Knowledge Product Development
Class: CL15 | Group: 07

# Educational Facilitation System (EFS)

**Making Student Life Easier at HKU SPACE**

**Presented by:**
- Xavier Wong (20296532)
- Kwok Ho Yin (20293303)
- Young Ho Tim (20293048)

**Supervisor:** Mr. Lau Chung Yin (Tim)

---

## SLIDE 2: AGENDA

**Image Placeholder:** [Roadmap icon with 6 stops]

**Text:**

# Today's Roadmap

| Stop | Topic | Presenter |
|------|-------|-----------|
| 1 | The Three Problems | Xavier |
| 2 | Our Solution Overview | Xavier |
| 3 | How We Built It | Xavier |
| 4 | Live Demonstration | Kwok |
| 5 | Testing & User Feedback | Tim |
| 6 | Lessons Learned & Q&A | All |

**Total: ~40 minutes**

---

## SLIDE 3: OPENING

**Image Placeholder:** [Cartoon of student surrounded by messy PDF windows]

**Text:**

# A Common Experience at HKU SPACE

**Every semester, students face three recurring challenges:**

1. Planning course schedules using PDF timetables
2. Finding study partners for group projects
3. Collecting survey responses for courses like EAP II

**Today we present a platform that addresses all three.**

---

## SLIDE 4: PROBLEM 1 - COURSE SCHEDULING

**Image Placeholder:** [Screenshot of a messy timetable PDF with multiple columns and rows]

**Text:**

# Problem 1: Course Scheduling is Manual and Difficult

**What students currently do:**

- Download multiple PDF timetable files from the college portal
- Open each PDF separately for different days or departments
- Read through rows of course codes, times, and room numbers
- Compare courses across documents to find available slots
- Check for time conflicts by scanning manually
- Track prerequisites and course dependencies separately
- Repeat the entire process when course selections change during add/drop period

**Why this is a problem:**

- No visual overview of the weekly schedule
- No automatic detection of overlapping courses
- No easy way to experiment with different course combinations
- The add/drop period is limited to a few days, adding pressure
- Students must rely on manual checking, which is prone to human error

---

## SLIDE 5: WHY EXISTING TOOLS ARE INSUFFICIENT

**Image Placeholder:** [Four icons: Moodle logo, Google Calendar logo, PDF icon, spreadsheet icon]

**Text:**

# Existing Tools Each Have Limitations

| Tool | What It Does | What's Missing |
|------|--------------|----------------|
| Moodle Calendar | Shows course events | No drag-and-drop planning, no conflict detection, not designed for schedule building |
| Google Calendar | Visual scheduling interface | No connection to HKU SPACE course data, requires manual entry of every course |
| PDF Files | Display timetable as document | Static format, no interaction, no automation |
| Spreadsheet | Manual schedule tracking | Requires full manual data entry, error-prone, no conflict detection |

**The gap:** A tool that combines institutional course data with a visual, interactive scheduling interface.

---

## SLIDE 6: PROBLEM 2 - STUDY GROUP FORMATION

**Image Placeholder:** [Screenshot of WhatsApp group chat with study group requests]

**Text:**

# Problem 2: Finding Study Partners Is Unstructured

**What students currently do:**

- Post messages in WhatsApp or Telegram class groups asking for study partners
- Receive replies from people they may not know
- Exchange contact information publicly in the group chat
- Manually coordinate meeting times and availability
- Have no way to know if potential partners have similar academic backgrounds
- Risk forming groups where participation is unequal
- Cannot filter or search for partners with specific skills or majors

**Why this is a problem:**

- No structure or organization to the formation process
- Personal contact information is exposed publicly
- No way to assess compatibility before committing
- Groups formed through informal channels often have mismatched ability levels
- Some group members may contribute less than others, affecting learning outcomes
- Students with smaller social networks have fewer opportunities to find partners

---

## SLIDE 7: PROBLEM 3 - QUESTIONNAIRE RESPONSES

**Image Placeholder:** [Illustration showing many students sending survey links to a small group of recipients]

**Text:**

# Problem 3: Collecting Survey Responses Is Competitive

**What students currently do:**

- Create surveys using Google Forms or similar tools for courses like EAP II
- Share survey links repeatedly in class group chats and personal messages
- Ask friends and classmates to fill out their surveys
- Hope that enough people will respond to meet course requirements
- Compete with dozens of other students who need responses from the same pool of people
- Send follow-up reminders when response targets are not met

**Why this is a problem:**

- Many students need responses from the same limited group of people
- Recipients receive multiple requests from different students, leading to request fatigue
- Students with larger friend networks have an advantage over those with smaller networks
- Significant time is spent chasing responses rather than analyzing data
- Course requirements may be difficult to complete fairly across all students

---

## SLIDE 8: SUMMARY OF THE THREE PROBLEMS

**Image Placeholder:** [Three icons arranged horizontally: PDF document, people icon, survey form]

**Text:**

# Three Problems. One Missing Solution.

| Problem | Current State |
|---------|----------------|
| Course Scheduling | Manual PDF checking, no visual overview, no conflict detection |
| Study Group Formation | Unstructured WhatsApp posts, no filtering, public contact exposure |
| Survey Response Collection | Competition for limited respondents, request fatigue, unfair advantage based on network size |

**Our observation:** No single platform at HKU SPACE addresses all three problems together, yet these are recurring challenges that affect most students.

**Our goal:** Build one integrated platform that solves all three.

---

## SLIDE 9: WHAT IS EFS?

**Image Placeholder:** [Four module icons arranged in a circle with central dashboard]

**Text:**

# EFS: Educational Facilitation System

**A web-based platform that addresses all three problems through four integrated modules.**

| Module | Problem It Solves |
|--------|-------------------|
| Timetable Planner | First problem - course scheduling |
| Group Formation | Second problem - finding study partners |
| Questionnaire Exchange | Third problem - survey response collection |
| Materials Repository | Additional feature - centralizing learning resources |

**One login. One dashboard. Four solutions.**

---

## SLIDE 10: MODULE 1 - TIMETABLE PLANNER

**Image Placeholder:** [Screenshot of visual calendar with colored course blocks]

**Text:**

# Timetable Planner: From PDFs to Visual Calendar

**What this module does:**

- Takes the existing HKU SPACE course data and displays it visually
- Allows students to search for courses by code or title
- Provides a weekly calendar view from Monday to Saturday, 8 AM to 9 PM
- Lets students drag and drop courses directly onto the calendar
- Automatically checks for scheduling conflicts when courses are added
- Colors each course consistently based on its code for easy identification
- Allows students to save their timetable to their account
- Exports the timetable as an image file for printing or sharing

**How it solves Problem 1:** Students no longer need to manually check PDF files. The system does the conflict detection automatically.

---

## SLIDE 11: HOW CONFLICT DETECTION WORKS

**Image Placeholder:** [Diagram showing two overlapping course blocks with red border]

**Text:**

# Automatic Conflict Detection

**When a student adds a course to their timetable, the system:**

1. Retrieves all existing courses already in the student's timetable
2. Compares the day of the new course (Monday? Tuesday?) with each existing course
3. Compares the time range of the new course (start time and end time) with each existing course on the same day
4. If the new course's time range overlaps with an existing course on the same day, the system flags a conflict
5. The conflicting course block turns red on the calendar
6. The system prevents the student from saving the overlapping schedule

**Example scenario:**
- Existing course: Tuesday, 2:30 PM to 5:30 PM
- Proposed new course: Tuesday, 4:00 PM to 6:00 PM
- Result: Conflict detected (the two courses share 1.5 hours of overlap)

**The student can then choose a different class time or remove the conflicting course.**

---

## SLIDE 12: MODULE 2 - GROUP FORMATION

**Image Placeholder:** [Screenshot of group formation request list with filter options]

**Text:**

# Group Formation: Structured Study Partner Matching

**What this module does:**

- Allows students to create study group requests with their major, description, and preferences
- Provides optional fields for GPA, DSE score, and phone number (student chooses what to share)
- Shows all active requests in a searchable and filterable list
- Allows students to filter requests by major or keyword
- Enables students to send private invitations to request creators
- Sends email notifications when someone expresses interest
- Keeps email addresses private (not shown in public list)
- Allows students to delete their request once they have found a group

**How it solves Problem 2:** Students can find partners based on actual compatibility criteria, not just whoever sees their WhatsApp message. Contact information stays private.

---

## SLIDE 13: THE INVITATION FLOW

**Image Placeholder:** [Flow diagram with four steps: Create → Browse → Invite → Connect]

**Text:**

# How the Matching Process Works

**Step 1: Student A creates a request**
- Fills in major, description, desired groupmates
- Optionally includes GPA, DSE score, or phone number
- Request appears in the public list

**Step 2: Student B browses available requests**
- Searches by major or keyword
- Reads descriptions from different students
- Identifies Student A as a potential good match

**Step 3: Student B sends an invitation**
- Clicks "Send Invite" button
- Types a personalized message
- System sends email to Student A

**Step 4: Student A reviews and decides**
- Reads the invitation and Student B's information
- Decides whether to respond
- If interested, they coordinate directly
- If not, the request remains active for others

**Key feature:** Student A's email address is never shown to Student B. The system handles the communication.

---

## SLIDE 14: MODULE 3 - QUESTIONNAIRE EXCHANGE

**Image Placeholder:** [Credit flow diagram showing: Start → Post (-1) → Fill (+1) → Repeat]

**Text:**

# Questionnaire Exchange: A Credit-Based System

**What this module does:**

- Gives every new user an initial balance of credits
- Allows students to post their survey links for others to fill
- Costs credits to post a survey
- Awards credits to students who fill other people's surveys
- Tracks how many responses each survey has received
- Marks surveys as completed when they reach their target
- Prevents students from filling the same survey twice

**How it solves Problem 3:** Instead of competing for respondents, students have an incentive to help each other. Filling surveys earns credits, which can be used to post one's own survey.

---

## SLIDE 15: HOW THE CREDIT ECONOMY WORKS

**Image Placeholder:** [Diagram showing: Help others → Earn credits → Post your survey → Get helped]

**Text:**

# The Credit Cycle

**Starting point:** Every new student receives an initial credit balance.

**To post a survey:** The student spends credits. The survey becomes visible to other students.

**To fill a survey:** The student opens the survey link, completes it, then returns to the platform to claim credit. The system verifies that the student has not already filled that survey before awarding credit.

**To earn more credits:** The student fills other people's surveys. Each filled survey adds to their credit balance.

**Result:** Students who help others earn the ability to be helped in return.

**When a survey reaches its target number of responses:** It is marked as completed and removed from the active list.

---

## SLIDE 16: MODULE 4 - MATERIALS REPOSITORY

**Image Placeholder:** [Screenshot of materials list organized by course code]

**Text:**

# Materials Repository: Centralized Learning Resources

**What this module does:**

- Organizes course materials by course code
- Allows students to browse materials for their enrolled courses
- Provides search functionality by course or material name
- Tracks download counts for each material
- Restricts uploads to administrators (quality control)
- Supports multiple file formats: PDF, images, Word documents, PowerPoint files

**What this module addresses (bonus feature):**

- Course materials are currently scattered across different platforms
- Some materials are on Moodle, some on WhatsApp, some on email attachments
- Students waste time searching for resources
- Centralizing materials saves time and provides a single source of truth

---

## SLIDE 17: THE DASHBOARD

**Image Placeholder:** [Screenshot of user dashboard showing credits, modules, and information]

**Text:**

# One Dashboard. Everything in One Place.

**What students see when they log in:**

- Welcome message with their student ID
- Current credit balance (for questionnaire exchange)
- Quick action buttons to access all four modules
- Statistics summary showing their courses, groups, surveys, and materials
- Recent activity log

**Why this matters:**

- Students no longer need to navigate between multiple different tools
- All information is visible from a single screen
- The dashboard provides a starting point for all activities

---

## SLIDE 18: USER ROLES

**Image Placeholder:** [Three user icons: Student, Admin, Pending]

**Text:**

# Three Types of Users

| Role | Permissions |
|------|-------------|
| **Student** | View timetable, create group requests, post and fill questionnaires, download materials, edit own profile |
| **Admin** | All student permissions, plus approve new account registrations, approve course requests, upload materials, view all users, delete users |
| **Pending** | Account created but awaiting admin approval (cannot log in until approved) |

**Why pending accounts exist:** New registrations require verification using student ID photos to ensure only legitimate HKU SPACE students can join.

---

## SLIDE 19: LIVE DEMONSTRATION

**Video Placeholder:** [Screen recording showing the following features in action]

**Text:**

# Watch EFS in Action

**The following will be demonstrated:**

1. **Account registration** - Creating a new student account
2. **Admin approval** - Approving a pending registration
3. **Login and dashboard** - Accessing the main interface
4. **Timetable planner** - Searching for courses, dragging onto calendar, conflict detection, exporting
5. **Group formation** - Creating a request, browsing requests, sending an invitation
6. **Questionnaire exchange** - Checking credit balance, posting a survey, filling a survey, credit changes
7. **Materials repository** - Browsing materials by course, downloading a file
8. **Profile management** - Editing profile information

**Demonstration duration:** 8-10 minutes

---

## SLIDE 20: DEMO PART 1 - ACCOUNT CREATION

**Video Placeholder:** [Screen recording showing registration form and student ID photo upload]

**Text:**

# Account Creation Process

**What the user does:**

- Navigates to the registration page
- Enters student ID, email address, and password
- Uploads a photo of their student ID card (for verification)
- Submits the registration form

**What happens after submission:**

- The account is created with "pending" status
- The account appears in the admin panel
- The student cannot log in until approved

**Why student ID verification is required:** Prevents people outside HKU SPACE from creating accounts.

---

## SLIDE 21: DEMO PART 2 - ADMIN APPROVAL

**Video Placeholder:** [Screen recording showing admin dashboard with pending accounts and approval action]

**Text:**

# Admin Approval Process

**What the administrator sees:**

- List of pending accounts with student IDs and email addresses
- Thumbnail preview of uploaded student ID photos
- Approve and Reject buttons for each account

**What the administrator does:**

- Clicks on the student ID photo to view it full size
- Verifies that the photo matches the student ID information
- Clicks "Approve" if the verification passes
- Clicks "Reject" with a reason if the verification fails

**What happens after approval:**

- The student receives an email notification
- The student can now log in to the platform
- The account status changes from "pending" to "active"

---

## SLIDE 22: DEMO PART 3 - TIMETABLE PLANNER

**Video Placeholder:** [Screen recording showing course search, drag-and-drop, and conflict detection]

**Text:**

# Timetable Planner Demonstration

**This demonstration shows:**

- Searching for a course by typing its code (e.g., "CCIT4080")
- Viewing the search results showing available class times and rooms
- Dragging a course from the search results onto the calendar
- Seeing the course appear as a colored block at the correct day and time
- Searching for a second course that overlaps with the first
- Dragging the second course onto the calendar
- Watching the conflict detection trigger (red border appears)
- Saving the timetable to the account
- Exporting the timetable as a PNG image

**The demonstration shows both successful adds and conflict scenarios.**

---

## SLIDE 23: DEMO PART 4 - GROUP FORMATION

**Video Placeholder:** [Screen recording showing request creation, browsing, and invitation sending]

**Text:**

# Group Formation Demonstration

**This demonstration shows:**

- Clicking "Create Request" to open the request form
- Filling in major (e.g., "Engineering")
- Writing a description of what kind of study partners the student wants
- Adding optional information (GPA, DSE score, phone number)
- Submitting the request
- Viewing the new request in the public list
- Using filters to search for requests by major
- Clicking "Send Invite" on another student's request
- Typing a personalized message
- Confirming the invitation is sent

**The demonstration shows the full cycle from creation to invitation.**

---

## SLIDE 24: DEMO PART 5 - QUESTIONNAIRE EXCHANGE

**Video Placeholder:** [Screen recording showing credit balance, posting survey, filling survey]

**Text:**

# Questionnaire Exchange Demonstration

**This demonstration shows:**

- The current credit balance displayed at the top of the page (starting at 3)
- Clicking "Create Questionnaire" to open the posting form
- Entering a description of the survey
- Pasting the Google Forms link
- Setting the target number of responses (30 for EAP II)
- Submitting the questionnaire (credit balance decreases by 1)
- Viewing the new questionnaire in the "Available" list
- Clicking "Open Link" to view an available survey
- Marking the survey as filled (credit balance increases by 1)
- Checking that the same survey cannot be filled twice

**The demonstration shows both posting and filling workflows.**

---

## SLIDE 25: DEMO PART 6 - MATERIALS REPOSITORY

**Video Placeholder:** [Screen recording showing materials browsing and downloading]

**Text:**

# Materials Repository Demonstration

**This demonstration shows:**

- Navigating to the materials section
- Viewing materials organized by course code
- Searching for a specific course code
- Clicking on a material to view its details (file name, upload date, size, download count)
- Clicking the download button
- The file downloading to the computer

**Note:** Uploading materials is restricted to administrators only. This demonstration focuses on the student experience of browsing and downloading.

---

## SLIDE 26: DEMO PART 7 - PROFILE MANAGEMENT

**Video Placeholder:** [Screen recording showing profile page and editing]

**Text:**

# Profile Management Demonstration

**This demonstration shows:**

- Navigating to the profile page
- Viewing current profile information (student ID, email, major, etc.)
- Clicking "Edit Profile" to enter edit mode
- Updating the phone number
- Changing the major field
- Adding GPA information (optional field)
- Adding skills as tags
- Writing an "about me" description
- Saving the changes
- Viewing the updated profile

**The demonstration shows that all changes persist after saving and reappear when the user logs back in.

---

## SLIDE 27: HOW WE BUILT IT - THREE TIERS

**Image Placeholder:** [Three-tier diagram: Client (laptop) → Server (cloud) → Database (cylinder)]

**Text:**

# The Three Layers of EFS

**Every web application has three layers:**

| Layer | Name | What it does |
|-------|------|--------------|
| Top | Client (Frontend) | What the user sees and clicks in the browser |
| Middle | Server (Backend) | Processes requests, runs business logic |
| Bottom | Database | Stores all data permanently |

**Analogy for understanding:**
- Client = Restaurant dining room (where customers sit)
- Server = Kitchen (where food is prepared)
- Database = Refrigerator (where ingredients are stored)

**EFS uses this standard three-tier architecture.**

---

## SLIDE 28: THE TECHNOLOGY STACK

**Image Placeholder:** [Four connected icons: MongoDB leaf, Express.js, React logo, Node.js logo]

**Text:**

# The MERN Stack

**MERN stands for four technologies that work together:**

| Letter | Technology | Role |
|--------|------------|------|
| M | MongoDB | Database tier - stores user accounts, courses, surveys, group requests |
| E | Express.js | Server framework - organizes how the server responds to different requests |
| R | React | Client library - builds the user interface in the browser |
| N | Node.js | Runtime - executes JavaScript code on the server |

**Why we chose these technologies:**

- All four use JavaScript, so the same language works across all three tiers
- The MERN stack is well-documented with many learning resources
- MongoDB's document model fits educational data well (courses and users have different structures)
- React is good for interactive features like drag-and-drop calendars

---

## SLIDE 29: HOW A REQUEST TRAVELS

**Image Placeholder:** [Flow diagram: Browser → Server → Database → Server → Browser]

**Text:**

# What Happens When You Click a Button

**Example: Student adds a course to their timetable**

1. **Browser** sends a request to the server asking to add the course
2. **Server** receives the request and checks the student's authentication token
3. **Server** validates that the course exists in the database
4. **Server** runs the conflict detection algorithm against existing courses
5. **Server** sends a write request to the database to save the new course
6. **Database** confirms the write operation completed
7. **Server** sends a success response back to the browser
8. **Browser** updates the screen to show the new course

**Total time per request:** Typically between 150 and 250 milliseconds

---

## SLIDE 30: AUTHENTICATION AND SECURITY

**Image Placeholder:** [Lock icon with three security elements: Password hash, Token, Role check]

**Text:**

# How We Protect User Data

**Password storage:**
- Passwords are not stored as plain text in the database
- When a user creates a password, the system converts it into a scrambled format called a hash
- The hash cannot be reversed to get the original password
- When the user logs in, the system hashes the entered password and compares it to the stored hash

**Session management:**
- When a user logs in successfully, the system issues a digital token
- The token proves the user's identity for future requests
- Tokens expire after 24 hours, requiring re-authentication

**Access control:**
- Each request checks the user's role (student or admin)
- Admin-only endpoints return an error if a non-admin user tries to access them

**Data in transit:**
- All communication between browser and server uses HTTPS encryption
- This prevents anyone from intercepting and reading the data

---

## SLIDE 31: DEPLOYMENT AND HOSTING

**Image Placeholder:** [Vercel logo and MongoDB Atlas logo]

**Text:**

# Where EFS Runs

**Frontend and Server: Vercel**

- EFS is deployed on Vercel, a cloud hosting platform
- Vercel uses a "serverless" model, meaning the code only runs when someone visits the site
- The platform automatically scales to handle more users without additional configuration
- Deployment is automatic when code is pushed to the GitHub repository

**Database: MongoDB Atlas**

- The database is hosted on MongoDB Atlas, a cloud database service
- The free tier provides enough storage and connection capacity for testing and demonstration
- The database is accessible only from authorized connections

**Result:** EFS is available 24/7 from anywhere with an internet connection, without requiring any installation.

---

## SLIDE 32: DATA EXTRACTION FROM PDFs

**Image Placeholder:** [Screenshot of PDF timetable next to JSON data output]

**Text:**

# Getting Course Data into the System

**Challenge:** HKU SPACE distributes course timetables as PDF files. PDFs are designed for printing, not for computers to read automatically.

**Solution:** Python scripts using a library called PyMuPDF

**The extraction process:**

1. The script opens the PDF file and reads its contents
2. It identifies text blocks and their positions on each page (X and Y coordinates)
3. It groups text blocks that belong together (e.g., course code + title + time + room)
4. It extracts the data into a structured format (JSON)
5. A separate script merges data from multiple PDF files and removes duplicate entries
6. The final JSON data is inserted into MongoDB

**Special handling for combined classes:**
- Some courses appear as "01+02" in the PDF, indicating two classes merged together
- The script detects the plus sign and creates separate entries for each class number
- Each separate entry includes a reference to the original combined class for display purposes

---

## SLIDE 33: TESTING THE PLATFORM

**Image Placeholder:** [Three icons: Manual testing, Load testing, Security testing]

**Text:**

# How We Tested EFS

**Manual feature testing:**
- Each member tested every feature multiple times
- Test cases included normal usage, edge cases, and error conditions
- Different web browsers (Chrome, Firefox, Safari) were used to check compatibility
- Screen sizes from desktop to mobile were tested for layout issues

**Load testing:**
- The platform was tested with simulated multiple users accessing it at the same time
- This simulated conditions during peak periods like add/drop week
- Response times and error rates were measured

**Security testing:**
- Attempted to access protected endpoints without authentication tokens (expected: denied)
- Attempted to access admin endpoints with student accounts (expected: denied)
- Attempted to submit invalid or malformed data to API endpoints (expected: proper error messages)

---

## SLIDE 34: USER FEEDBACK SUMMARY

**Image Placeholder:** [Bar chart showing feature ratings with neutral labeling]

**Text:**

# What Users Told Us About EFS

**Method:** Anonymous survey distributed to HKU SPACE students after they had the opportunity to use the platform.

**Sample:** Students from different years and majors who volunteered to test the platform.

**Feedback collected on:**

- The overall concept of an integrated platform for HKU SPACE
- The usefulness of each of the four modules (Timetable Planner, Group Formation, Questionnaire Exchange, Materials Repository)
- The dashboard and user interface
- The credit system for questionnaire exchange
- Privacy controls and profile management
- Feature requests and suggestions for improvement

**Key themes from open-ended responses:**
- The timetable planner's visual interface and conflict detection were noted as helpful compared to manual PDF checking
- The ability to control what information is shared publicly was mentioned positively
- The questionnaire credit system was seen as a fair way to balance supply and demand
- Requests for additional features included deadline reminders and more materials

---

## SLIDE 35: PERFORMANCE TEST RESULTS

**Image Placeholder:** [Metric table with green indicators]

**Text:**

# System Performance Measurements

| Test | Result |
|------|--------|
| Average API response time | 219 milliseconds |
| Response time under concurrent users | Maintained under 300 milliseconds |
| Error rate during load testing | Zero errors recorded |
| Page load time (initial visit) | Approximately 1.5 seconds |
| Page load time (subsequent visits) | Approximately 0.8 seconds (cached) |

**Lighthouse audit scores (Google's web quality tool):**

| Category | Score |
|----------|-------|
| Performance | 76 out of 100 |
| Accessibility | 96 out of 100 |
| Best Practices | 96 out of 100 |
| SEO | 90 out of 100 |

**The accessibility score indicates the platform can be used by students with disabilities who rely on screen readers or keyboard navigation.**

---

## SLIDE 36: CHALLENGES WE FACED

**Image Placeholder:** [Five challenge icons with brief solutions]

**Text:**

# Technical Challenges and Solutions

**Challenge 1: Serverless deployment incompatibility**
- Traditional server code expects to run continuously
- Vercel uses serverless functions that start and stop per request
- **Solution:** Restructured the code to export handler functions instead of starting a server

**Challenge 2: File upload storage**
- Traditional file upload libraries write to the local disk
- Vercel's filesystem is temporary and resets frequently
- **Solution:** Used GridFS to store files directly in MongoDB

**Challenge 3: Database connection limits**
- The free MongoDB tier limits concurrent connections
- Each serverless function call could create a new connection
- **Solution:** Implemented connection pooling to reuse connections across requests

**Challenge 4: PDF parsing inconsistency**
- Timetable PDFs have different formatting across semesters
- Some tables span multiple pages, some have merged cells
- **Solution:** Used coordinate-based text extraction rather than table structure detection

**Challenge 5: Email deliverability**
- Invitation emails from new senders often go to spam folders
- **Solution:** Configured proper SMTP settings and used Gmail's App Password feature

---

## SLIDE 37: LESSONS LEARNED

**Image Placeholder:** [Lightbulb icon with bullet points]

**Text:**

# What We Learned

**Technical lessons:**

- Test deployment configuration early in the development process, not at the end
- Database connection limits require planning even with cloud services
- PDF parsing is fragile and may need maintenance when source documents change
- Environment variables should be managed centrally, not scattered across configuration files

**Process lessons:**

- Building small working features first and then adding more works better than trying to build everything at once
- Writing documentation during development saves time during integration
- Getting feedback from potential users early helps identify which features are most needed

**Team lessons:**

- Clear division of responsibilities helps, but regular communication is essential
- Daily brief check-ins help keep everyone aligned, even during busy exam periods
- Using version control with feature branches prevents code conflicts

---

## SLIDE 38: WHAT WE BUILT - SUMMARY

**Image Placeholder:** [Four module screenshots in a grid]

**Text:**

# Summary of Deliverables

**The EFS platform includes:**

1. **Timetable Planner** - Visual calendar with drag-and-drop course scheduling, automatic conflict detection, and PNG export
2. **Group Formation** - Structured study partner requests, search and filter functionality, private email invitations
3. **Questionnaire Exchange** - Credit-based system for posting and filling surveys, response tracking, completion status
4. **Materials Repository** - Centralized course materials organized by course code, download tracking
5. **User Dashboard** - Central view showing credit balance, quick actions, and activity summary
6. **Admin Panel** - Account approval, course request approval, user management, platform statistics
7. **Authentication System** - Registration, login, role-based access control, password hashing

**All modules are fully integrated with a single user account.**

---

## SLIDE 39: FUTURE WORK

**Image Placeholder:** [Roadmap with short-term and long-term items]

**Text:**

# Planned Future Enhancements

**Short-term (next iteration):**

- Password reset functionality (currently not implemented)
- Deadline reminder system connected to the timetable
- More granular privacy controls for profile information
- Expanded file format previews in materials repository

**Long-term (future development):**

- Native mobile applications for iOS and Android
- Integration with HKU SPACE official systems if APIs become available
- Automated study group recommendations based on course enrollment
- Analytics dashboard for instructors to see platform usage patterns
- Real-time notifications (currently the system uses periodic checks)

**The priority for immediate next steps is based on user feedback collected during testing.**

---

## SLIDE 40: TEAM CONTRIBUTIONS

**Image Placeholder:** [Three team member names with brief role descriptions]

**Text:**

# Who Built What

| Team Member | Primary Role | Key Contributions |
|-------------|--------------|-------------------|
| Xavier Wong | Backend Development | Server architecture, API endpoints, MongoDB schema, GridFS file storage, authentication system, Vercel deployment configuration |
| Kwok Ho Yin | Frontend Development | React user interface, calendar component with drag-and-drop, group formation UI, dashboard layout, profile management screens, CSS styling |
| Young Ho Tim | Data Processing & Testing | PDF parsing scripts using PyMuPDF, data transformation pipelines, database seeding, integration testing, documentation, logbook maintenance |

**Collaborative work across all members:** System design decisions, testing, user feedback collection, project logbook, final report writing.

---

## SLIDE 41: TRY EFS YOURSELF

**Image Placeholder:** [Screenshot of the live website with URL displayed]

**Text:**

# Live Demo Available

**URL:** `https://platform-efs2.vercel.app`

**To try the platform:**
1. Open the URL in any modern web browser (Chrome, Firefox, Safari, Edge)
2. Click "Register" to create a test account
3. Upload a student ID photo (any image file is acceptable for demonstration)
4. Wait for admin approval (or ask the presenters to approve immediately)
5. Log in and explore all four modules

**No installation required.** The platform runs entirely in the browser.

**The source code repository is available upon request for examiners.**

---

## SLIDE 42: ACKNOWLEDGMENTS

**Image Placeholder:** [Thank you graphic]

**Text:**

# Acknowledgments

**We would like to thank:**

- **Mr. Lau Chung Yin (Tim)** - For supervising this project and providing guidance throughout both semesters

- **HKU SPACE Community College** - For providing the opportunity to work on this project and access to resources

- **The students who participated in testing** - For their time and feedback

- **The open source community** - For creating and maintaining the libraries and tools we used: MongoDB, Express.js, React, Node.js, PyMuPDF, Nodemailer, and many others

---

## SLIDE 43: QUESTIONS AND DISCUSSION

**Image Placeholder:** [Q&A graphic with question marks]

**Text:**

# Questions?

**We welcome questions about:**

- How specific features work
- Technical implementation details
- Design decisions and alternatives considered
- Testing methodology
- Future development plans
- Any other aspect of the project

**Direct technical questions to:**
- Xavier Wong - Backend, database, deployment
- Kwok Ho Yin - Frontend, UI, calendar
- Young Ho Tim - Data processing, PDF parsing, testing

---

## SLIDE 44: BACKUP - SYSTEM ARCHITECTURE DIAGRAM

**Image Placeholder:** [Detailed three-tier architecture diagram with arrows showing data flow]

**Text:**

# Appendix: Complete System Architecture

**This diagram is available for reference during Q&A if there are technical questions about how the components connect.**

**The diagram shows:**
- Client tier: React application running in the browser
- Application tier: Express.js API endpoints deployed on Vercel
- Database tier: MongoDB Atlas collections and GridFS buckets
- External services: Gmail SMTP for email notifications

**The arrows indicate the flow of data between components when a user interacts with the platform.**

---

## SLIDE 45: BACKUP - API ENDPOINTS LIST

**Image Placeholder:** [Table of API endpoints with methods and descriptions]

**Text:**

# Appendix: API Endpoint Reference

**Available during Q&A for technical questions.**

| Module | Endpoint | Method | Purpose |
|--------|----------|--------|---------|
| Auth | /api/auth/register | POST | Create new pending account |
| Auth | /api/auth/login | POST | Authenticate and receive token |
| Auth | /api/auth/check | GET | Verify token validity |
| Courses | /api/courses | GET | List all courses |
| Courses | /api/courses/:code | GET | Get course details |
| Calendar | /api/calendar/events | GET | Get timetable events |
| Calendar | /api/calendar/save | POST | Save user timetable |
| Group | /api/group/requests | GET | List group requests |
| Group | /api/group/requests | POST | Create group request |
| Group | /api/group/requests/:id/invite | POST | Send invitation |
| Questionnaire | /api/questionnaire | GET | List questionnaires |
| Questionnaire | /api/questionnaire | POST | Create questionnaire |
| Questionnaire | /api/questionnaire/:id/fill | POST | Mark questionnaire as filled |
| Materials | /api/materials/all | GET | List all materials |
| Materials | /api/materials/download/:id | GET | Download material file |
| Profile | /api/profile/me | GET | Get current user profile |
| Profile | /api/profile/update | PUT | Update profile |
| Admin | /api/admin/pending/accounts | GET | List pending accounts |
| Admin | /api/admin/pending/accounts/:sid/approve | POST | Approve account |
| Admin | /api/admin/stats | GET | Get platform statistics |

---

## SLIDE 46: BACKUP - DATABASE COLLECTIONS

**Image Placeholder:** [List of collections with descriptions]

**Text:**

# Appendix: Database Schema

**Available during Q&A for technical questions.**

| Collection | Purpose | Key Fields |
|------------|---------|------------|
| users | Student and admin accounts | sid, email, passwordHash, role, credits, token, timetable |
| courses | Course session data | code, name, weekday, startTime, endTime, room, classNo |
| pending_accounts | Accounts awaiting approval | sid, email, passwordHash, photoFileId |
| pending_courses | Course requests awaiting approval | code, title, requestedBy |
| group_requests | Study group posts | sid, major, description, email, status |
| questionnaires | Survey exchange listings | creatorSid, description, link, targetResponses, filledBy, currentResponses |
| materials | Course resource metadata | id, name, fileId, courseCode, downloads, uploadedBy |
| uploads.files | GridFS file metadata | filename, uploadDate, length, metadata |
| uploads.chunks | GridFS file binary chunks | files_id, n, data |

**Relationships between collections are maintained through reference fields (e.g., courseCode in materials references code in courses).**

---

## SLIDE 47: THANK YOU

**Image Placeholder:** [Closing graphic]

**Text:**

# Thank You for Your Attention

**EFS Platform - Educational Facilitation System**

**Group 7**
- Xavier Wong (20296532)
- Kwok Ho Yin (20293303)
- Young Ho Tim (20293048)

**Supervisor:** Mr. Lau Chung Yin (Tim)

**Questions?**

---
