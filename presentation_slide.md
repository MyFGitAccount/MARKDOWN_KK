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
| 3 | How We Built It (Simple Explanation) | Xavier |
| 4 | Live Demonstration | Kwok |
| 5 | Testing & User Feedback | Tim |
| 6 | Lessons Learned & Q&A | All |

**Total: ~40 minutes**

---

## SLIDE 3: OPENING HOOK

**Image Placeholder:** [Cartoon of student surrounded by messy PDF windows, looking confused]

**Text:**

# "I have five PDFs open... and I still don't know if my courses overlap."

**– A real quote from a HKU SPACE student during add/drop week**

**Today we're solving this problem – and two others – with one simple platform.**

---

## SLIDE 4: THREE CORE PROBLEMS

**Image Placeholder:** [Three icons: PDF document, People with question mark, Survey form with downward arrow]

**Text:**

# Three Problems. One Solution.

| # | Problem | Key Stat |
|---|---------|----------|
| 1 | **Inefficient course scheduling** | 79% say PDF checking is time-consuming |
| 2 | **Fragmented study group formation** | 58% struggle to find study partners |
| 3 | **Questionnaire demand crisis** | 58% have difficulty getting responses |

**The data:** Survey of 24 HKU SPACE students

---

## SLIDE 5: PROBLEM 1 - THE PDF NIGHTMARE

**Image Placeholder:** [Screenshot of messy timetable PDF with confusing layout]

**Text:**

# Problem 1: Timetable Planning is Broken

**Current process:**
1. Download 5+ PDF files
2. Open each separately
3. Manually track course times
4. Check for conflicts by eye
5. Repeat when schedule changes

**What students told us:**
> *"I spent 4 hours on my timetable and still got a conflict."*

> *"Add/drop week is the most stressful time of the semester."*

**70% of students have made scheduling errors**

---

## SLIDE 6: WHY EXISTING TOOLS FAIL

**Image Placeholder:** [Four logos with X marks: Moodle, Google Calendar, PDF, Excel]

**Text:**

# No Existing Tool Solves This

| Tool | What's Missing |
|------|----------------|
| Moodle Calendar | No drag-and-drop, no conflict detection |
| Google Calendar | Not connected to HKU SPACE course data |
| PDF files | Static, no interaction, manual only |
| Excel/Paper | Manual entry, error-prone |

**The Gap:** Institutional course data + visual scheduling + automatic conflict detection = None exist

---

## SLIDE 7: PROBLEM 2 - STUDY GROUP CHAOS

**Image Placeholder:** [WhatsApp screenshot showing group formation request with multiple replies]

**Text:**

# Problem 2: Finding Study Partners is Random

**Current method:** Post on WhatsApp/Telegram and hope

**Problems with this approach:**
- No way to know someone's major or skill level
- No filter for compatibility
- Free-riding is common (people don't contribute)
- Contact information exposed publicly

> *"I've joined groups where one person does all the work."*

**81% of students would use a structured matching system**

---

## SLIDE 8: WHAT RESEARCH TELLS US

**Image Placeholder:** [Simple diagram showing matching criteria: Skills + Availability + Goals]

**Text:**

# Research-Backed Design

**Massah (2018):** Free-riding is a persistent challenge in group work. Structured formation reduces unequal participation.

**Srba & Bielikova (2014):** Dynamic group formation based on student profiles significantly improves collaboration outcomes.

**Our conclusion:** Need profile-based matching with privacy controls.

**Key insight:** Students need compatibility across multiple dimensions – skills, availability, goals.

---

## SLIDE 9: PROBLEM 3 - SURVEY FATIGUE

**Image Placeholder:** [Graph showing declining response rates as requests increase]

**Text:**

# Problem 3: Too Many Surveys, Too Few Respondents

**The math for EAP II:**
- 40 students × 30 responses each = 1,200 responses needed
- Available respondents: ~200-300 students
- **Demand is 4-6x higher than supply**

**Response rates decline with each request:**
| Requests | Expected Response Rate |
|----------|----------------------|
| 0-5 | 85% |
| 6-10 | 65% |
| 11-15 | 42% |
| 16-20 | 23% |

*Source: De Koning et al., 2021*

---

## SLIDE 10: THE SYSTEM GAP

**Image Placeholder:** [Five disconnected tools: Moodle, WhatsApp, Google Forms, PDF, LinkedIn with X marks]

**Text:**

# No Single Platform Does It All

| Need | Current Tool | Problem |
|------|--------------|---------|
| Timetable | Moodle + PDFs | Basic only, no visuals |
| Group formation | WhatsApp | No structure, no filtering |
| Surveys | Google Forms | No respondent finding |
| Materials | Scattered | No central location |

**Students patch together 5+ different tools.**

**Our goal:** One platform that does everything.

---

## SLIDE 11: WHAT IS EFS?

**Image Placeholder:** [Four module icons arranged in a circle with central dashboard]

**Text:**

# Meet EFS: Your Academic Command Center

**Four modules. One login. Zero switching.**

| Module | Solves |
|--------|--------|
| Timetable Planner | PDF nightmare |
| Group Formation | Finding study partners |
| Questionnaire Exchange | Survey fatigue |
| Materials Repository | Scattered resources |

**Built specifically for HKU SPACE students with real course data.**

---

## SLIDE 12: MODULE 1 - TIMETABLE PLANNER

**Image Placeholder:** [Screenshot of visual calendar with colored course blocks]

**Text:**

# Timetable Planner: From PDFs to Visual Calendar

**What you can do:**
- Search for courses by code or title
- Drag and drop onto calendar
- See conflicts instantly (red = overlap)
- Color-coded courses (same course = same color)
- Export as PNG image
- Save to your account

**Time saved:** From 4-6 hours to under 10 minutes

---

## SLIDE 13: HOW CONFLICT DETECTION WORKS

**Image Placeholder:** [Two overlapping course blocks with red border, showing before/after]

**Text:**

# Automatic Conflict Detection

**What happens when you try to add a course:**

1. System checks every course already in your timetable
2. Compares day (Monday? Tuesday?)
3. Compares times (14:30-17:30 vs 16:00-18:00)
4. If overlap detected → RED border + cannot save

**No more guessing. No more manual checking.**

**Example:** Existing course 14:30-17:30 + new course 16:00-18:00 = CONFLICT

---

## SLIDE 14: MODULE 2 - GROUP FORMATION

**Image Placeholder:** [Screenshot of group formation request list with filter options]

**Text:**

# Group Formation: Find Compatible Study Partners

**How it works:**
1. Create request with major, description, preferences
2. Optional: share GPA, DSE score, phone
3. Browse other students' requests
4. Filter by major or keyword
5. Send private invitation via email

**Privacy first:** Email addresses never shown publicly

---

## SLIDE 15: THE INVITATION FLOW

**Image Placeholder:** [Flow diagram: Student A creates request → Student B finds it → System sends email → Student A decides]

**Text:**

# How Matching Works

**Step 1:** Student A creates a request (major, description, preferences)

**Step 2:** Student B browses and finds a good match

**Step 3:** Student B clicks "Send Invite" + types message

**Step 4:** System sends email to Student A (email address stays private)

**Step 5:** Student A reviews and decides whether to respond

**Both parties opt in. No spam. No unwanted contact.**

---

## SLIDE 16: MODULE 3 - QUESTIONNAIRE EXCHANGE

**Image Placeholder:** [Credit flow diagram showing: 3 credits start → Post (-1) → Fill (+1) → Repeat]

**Text:**

# Questionnaire Exchange: A Fair Credit System

**The economy of responses:**

| Action | Credits |
|--------|---------|
| New user starts with | 3 credits |
| Post your own survey | Costs 1 credit |
| Fill someone's survey | Earns 1 credit |
| Reach 30 responses | Survey completes |

**Fair exchange:** Help others, earn credits, spend credits to get help.

---

## SLIDE 17: WHY THE CREDIT SYSTEM WORKS

**Image Placeholder:** [Simple equation showing: Help 3 people → Get 3 credits → Post your survey]

**Text:**

# Solving Supply and Demand

**Without credits:** Everyone posts, few respond → Nobody wins

**With credits:** 
- To post, you must have earned credits (or use your starting 3)
- To earn credits, you must help others
- Result: Balanced supply and demand

**What users said:**
> *"The credit system makes it fair. Everyone has to contribute."*

**79% of users agreed the credit system is fair.**

---

## SLIDE 18: MODULE 4 - MATERIALS REPOSITORY

**Image Placeholder:** [Screenshot of materials list organized by course code]

**Text:**

# Materials Repository: Everything in One Place

**Features:**
- Organized by course code
- Search by course or material name
- Download count tracking (see what's popular)
- Only admins upload (quality control)

**Supported formats:** PDF, images, Word, PowerPoint

**User feedback:** 92% said organized materials are useful

**Top requests:** Lecture notes (88%), Past exam papers (79%)

---

## SLIDE 19: THE DASHBOARD - YOUR CENTRAL HUB

**Image Placeholder:** [Screenshot of user dashboard showing credits, quick actions, statistics]

**Text:**

# One Dashboard. Everything You Need.

**What you see when you log in:**
- Welcome message and student ID
- Credit balance (starts at 3)
- Quick action buttons to all modules
- Statistics (courses, groups, surveys, materials)
- Recent activity feed

**88% of users found the dashboard helpful**

---

## SLIDE 20: USER ROLES & PERMISSIONS

**Image Placeholder:** [Three user icons: Student, Admin, Pending with different access levels]

**Text:**

# Three Types of Users

| Role | What They Can Do |
|------|------------------|
| **Student** | Timetable, groups, surveys, materials, profile |
| **Admin** | All student permissions + approve accounts, approve courses, upload materials, manage users |
| **Pending** | Registered, waiting for approval (cannot log in yet) |

**New registrations require admin approval to prevent spam.**

---

## SLIDE 21: LIVE DEMONSTRATION

**Video Placeholder:** [Screen recording of the following:]

**Text:**

# Watch EFS in Action

**Live demonstration of:**

1. Account registration
2. Admin approval
3. Login to dashboard
4. Timetable planner (search, drag-drop, conflict detection, export)
5. Group formation (create request, browse, send invitation)
6. Questionnaire exchange (post survey, fill survey, credit changes)
7. Materials repository (browse, download)

**Duration:** 8-10 minutes

---

## SLIDE 22: DEMO PART 1 - ACCOUNT CREATION

**Video Placeholder:** [Screen recording showing registration form and student ID upload]

**Text:**

# Step 1: Create an Account

**What the user does:**
1. Enters student ID, email, password
2. Uploads student ID card photo (verification)
3. Clicks submit

**What happens next:**
- Account goes to "pending" status
- Admin receives notification
- User waits for approval email

**Why this step?** Prevents non-HKU SPACE students from joining.

---

## SLIDE 23: DEMO PART 2 - ADMIN APPROVAL

**Video Placeholder:** [Screen recording showing admin dashboard with pending accounts]

**Text:**

# Step 2: Admin Approves Account

**What the admin sees:**
- List of pending accounts
- Student ID and email
- Uploaded student ID photo (click to enlarge)
- Approve or Reject buttons

**What the user receives:**
- Approval email with login instructions
- OR rejection email with reason

**Typical approval time:** Within 24 hours

---

## SLIDE 24: DEMO PART 3 - TIMETABLE PLANNER

**Video Placeholder:** [Screen recording showing course search, drag-and-drop, conflict detection]

**Text:**

# Step 3: Build Your Timetable

**Demonstration of:**
- Searching for courses by code (e.g., "CCIT4080")
- Viewing available classes with times and rooms
- Dragging courses onto the calendar
- Seeing conflict detection (red = overlap)
- Exporting timetable as PNG

**Real-time feedback:** Every action updates instantly.

---

## SLIDE 25: DEMO PART 4 - GROUP FORMATION

**Video Placeholder:** [Screen recording showing creating request, browsing, sending invitation]

**Text:**

# Step 4: Find Study Partners

**Demonstration of:**
- Creating a request with major and description
- Browsing existing requests
- Filtering by major or keyword
- Sending a private invitation
- Email notification being sent

**Privacy preserved:** Email addresses never exposed publicly.

---

## SLIDE 26: DEMO PART 5 - QUESTIONNAIRE EXCHANGE

**Video Placeholder:** [Screen recording showing credit balance, posting survey, filling survey]

**Text:**

# Step 5: Exchange Surveys

**Demonstration of:**
- Checking credit balance (starts at 3)
- Posting a survey (costs 1 credit)
- Browsing available surveys
- Filling someone's survey (earns 1 credit)
- Progress tracking (X/30 responses)

**Live credit updates:** Balance changes instantly after each action.

---

## SLIDE 27: DEMO PART 6 - MATERIALS & PROFILE

**Video Placeholder:** [Screen recording showing materials repository and profile editing]

**Text:**

# Step 6: Access Materials & Manage Profile

**Materials Repository:**
- Browse by course code
- Download files
- View download counts

**Profile Management:**
- Edit email, phone, major
- Add GPA, DSE score (optional)
- Update skills and bio
- Profile photo from student ID upload

**96% of users said privacy controls are important**

---

## SLIDE 28: HOW WE BUILT IT - SIMPLE EXPLANATION

**Image Placeholder:** [Three-tier diagram: User with laptop (Client) → Cloud (Server) → Database cylinder]

**Text:**

# How We Built EFS (Plain English)

**Three layers:**

| Layer | Name | What it does |
|-------|------|--------------|
| Top | Client (Frontend) | What you see and click |
| Middle | Server (Backend) | The brain that processes requests |
| Bottom | Database | Where information is stored |

**Analogy:** Restaurant dining room (client) → Kitchen (server) → Refrigerator (database)

---

## SLIDE 29: THE TECHNOLOGY STACK (MERN)

**Image Placeholder:** [Four connected icons: MongoDB leaf, Express.js, React logo, Node.js logo]

**Text:**

# The MERN Stack Explained

| Letter | Technology | What it does | Plain English |
|--------|------------|--------------|---------------|
| M | MongoDB | Database | Digital filing cabinet |
| E | Express.js | Backend framework | Traffic controller |
| R | React | Frontend library | Screen builder |
| N | Node.js | Runtime | Engine that runs the server |

**Cool fact:** Everything is JavaScript – same language from screen to server to database.

---

## SLIDE 30: HOW DATA MOVES (A REQUEST'S JOURNEY)

**Image Placeholder:** [Flow diagram: Browser → Server → Database → Server → Browser]

**Text:**

# What Happens When You Click a Button

**Example: Adding a course to timetable**

1. **Browser:** "Hey server, add CCIT4080 to my timetable"
2. **Server:** "Let me check if you're logged in..."
3. **Server:** "Let me check if that course exists..."
4. **Server:** "Let me check for conflicts..."
5. **Database:** "I saved it. Here's confirmation."
6. **Server:** "Success! Your timetable is updated."
7. **Browser:** Shows the new course on calendar

**Total time:** Usually under 200 milliseconds (faster than a blink)

---

## SLIDE 31: HOW WE KEEP DATA SAFE

**Image Placeholder:** [Lock icon with three checkmarks: Passwords, Tokens, Roles]

**Text:**

# Security in Plain English

| Feature | What it does | Why it matters |
|---------|--------------|----------------|
| Password hashing | Turns password into secret code | Even if database stolen, passwords stay secret |
| JWT tokens | Digital ID card that expires | Proves you're really you, expires after 24 hours |
| Role-based access | Student vs Admin permissions | Students can't access admin functions |
| HTTPS encryption | Scrambles data in transit | Nobody can spy on what you send |

**Result:** Zero security breaches during testing.

---

## SLIDE 32: THE BIGGEST TECHNICAL CHALLENGE (PDF PARSING)

**Image Placeholder:** [Screenshot of messy PDF next to clean structured JSON data]

**Text:**

# Challenge: Extracting Data from PDFs

**The problem:** HKU SPACE timetables are PDFs designed for printing, not computers.

**Our solution:** Python script using PyMuPDF library
- Reads PDF as coordinates (text at X,Y position)
- Groups text that belongs together
- Outputs clean JSON data
- Seeds the database automatically

**Why this was hard:** PDF formats change. Combined classes like "01+02" need special handling.

---

## SLIDE 33: TESTING - HOW WE KNOW IT WORKS

**Image Placeholder:** [Three icons: Checkmark, Speedometer, Lock]

**Text:**

# Three Types of Testing

| Test Type | What We Did | Result |
|-----------|-------------|--------|
| Manual testing | Tried every feature ourselves | All features work |
| Load testing | Simulated 200 users at once | Response time: 219ms |
| Security testing | Tried to break in | No unauthorized access |

**Also tested on:** Chrome, Firefox, Safari (all work)

**Lighthouse score:** 96/100 for accessibility (great for students with disabilities)

---

## SLIDE 34: WHO TESTED OUR PLATFORM

**Image Placeholder:** [Pie charts showing demographics]

**Text:**

# Our Test Users: 24 HKU SPACE Students

**Demographics:**
- 83% were Year 2 students (experienced with college systems)
- 71% were Engineering majors
- 71% use online platforms daily

**This group represented our target users well.**

**They tested every feature and gave anonymous feedback.**

---

## SLIDE 35: WHAT USERS TOLD US - OVERALL

**Image Placeholder:** [Bar chart showing percentages]

**Text:**

# Overall Feedback: Very Positive

| Question | Positive Response |
|----------|-------------------|
| Platform is useful | 92% |
| Would use this platform | 88% |
| Rating: Excellent or Good | 88% |

**Nobody rated it Fair or Poor.**

> *"Finally, a platform specialized for HKU SPACE students."*

> *"This should be official. Why doesn't HKU SPACE already have something like this?"*

---

## SLIDE 36: WHAT USERS SAID ABOUT EACH FEATURE

**Image Placeholder:** [Horizontal bar chart with percentages]

**Text:**

# Feature-by-Feature Satisfaction

| Feature | % Agree/Strongly Agree |
|---------|------------------------|
| Timetable saves time vs PDFs | 92% |
| Materials repository is useful | 92% |
| Dashboard is helpful | 88% |
| Group formation helps find partners | 83% |
| Credit system is fair | 79% |

**Every feature scored above 75%.**

---

## SLIDE 37: DIRECT QUOTES FROM USERS

**Image Placeholder:** [Speech bubbles with quotes]

**Text:**

# What Students Actually Said

> *"Much faster and more efficient than checking PDFs manually."*

> *"The credit system makes it fair. Everyone has to contribute."*

> *"I love that I can see my whole week at a glance."*

> *"Finally, a platform that understands HKU SPACE students."*

> *"Being able to control what information is visible is very important to me."*

**96% said privacy controls are important.**

---

## SLIDE 38: MOST VALUABLE FEATURE (According to Users)

**Image Placeholder:** [Pie chart showing feature rankings]

**Text:**

# Which Feature Do Students Value Most?

| Rank | Feature | % saying "Most Valuable" |
|------|---------|-------------------------|
| 1 | Questionnaire Exchange | 25% |
| 2 | Timetable Planner | 21% |
| 3 | Group Formation | 17% |
| 4 | Materials Repository | 17% |
| 5 | Dashboard | 12% |

**Questionnaire Exchange #1 confirms survey fatigue is real.**

---

## SLIDE 39: WHAT NEEDS IMPROVEMENT (Honest Feedback)

**Image Placeholder:** [Bar chart showing improvement requests]

**Text:**

# What Users Want Us to Improve

| Feature | % saying "Needs Improvement" |
|---------|------------------------------|
| Materials Repository | 21% (want MORE materials) |
| Dashboard | 17% (want deadline reminders) |
| Group Formation | 13% (want better filtering) |
| Timetable Planner | 8% (mostly happy with it) |

**We're addressing these in future updates.**

**Top request:** Deadline reminders on dashboard.

---

## SLIDE 40: PERFORMANCE TEST RESULTS

**Image Placeholder:** [Metric table with green checkmarks]

**Text:**

# How Fast and Reliable Is It?

| Metric | Our Result | Industry Standard |
|--------|------------|-------------------|
| Average response time | 219ms | Under 500ms = Good ✓ |
| Peak users handled | 200 concurrent | More than expected |
| Errors under load | 0% | Perfect ✓ |
| Uptime | 99.9% | Reliable ✓ |

**Lighthouse scores:**
- Performance: 76/100 (Good)
- Accessibility: 96/100 (Excellent)
- Best Practices: 96/100 (Excellent)

---

## SLIDE 41: CHALLENGES WE OVERCAME

**Image Placeholder:** [Five challenge icons with checkmarks]

**Text:**

# Five Major Challenges (And How We Solved Them)

| Challenge | Solution |
|-----------|----------|
| Vercel serverless doesn't support traditional servers | Restructured code to use serverless functions |
| File uploads need permanent storage | Used GridFS (stores files in database) |
| Free database only allows 20 connections | Connection pooling (reuse connections) |
| PDF formats are inconsistent | Python script with coordinate-based extraction |
| Email invitations going to spam | Proper Gmail SMTP configuration |

**Every challenge has a solution.**

---

## SLIDE 42: LESSONS WE LEARNED

**Image Placeholder:** [Lightbulb icon with bullet points]

**Text:**

# What We'll Do Differently Next Time

**Technical lessons:**
- Test deployment EARLY (not at the end)
- Connection pooling is critical with free tiers
- PDF parsing is fragile – need monitoring

**Process lessons:**
- Build small, test, iterate (agile works)
- Write documentation as you go
- Get user feedback early and often

**Team lessons:**
- Clear roles help, but communication is essential
- Daily check-ins kept us aligned
- Start simple, then add features

**First working version:** Only login and a basic calendar. Everything else came later.

---

## SLIDE 43: WHAT WE ACCOMPLISHED

**Image Placeholder:** [Nine checkboxes with checkmarks]

**Text:**

# Requirements: 9 for 9

**Functional Requirements (6/6):**
- ✓ Display institutional timetable
- ✓ Drag-and-drop scheduling
- ✓ Document upload
- ✓ Academic profiles
- ✓ Questionnaire platform
- ✓ Credit incentives

**Non-Functional Requirements (3/3):**
- ✓ Intuitive UI (92% user satisfaction)
- ✓ Security & privacy (fully verified)
- ✓ Responsiveness (<219ms under load)

**We delivered what we promised.**

---

## SLIDE 44: PROJECT STATISTICS

**Image Placeholder:** [Four large numbers with icons]

**Text:**

# By The Numbers

**5,000+** lines of code

**25+** API endpoints

**8** database collections

**24** survey respondents

**5 months** of development

**3** team members with no prior full-stack experience

**We're proud of what we built.**

---

## SLIDE 45: WHAT'S NEXT (Future Work)

**Image Placeholder:** [Roadmap with short-term and long-term items]

**Text:**

# The Road Ahead

**Short-term (3-6 months):**
- Password reset functionality
- Deadline reminders on dashboard
- More granular privacy controls (96% user demand)

**Long-term (6-12 months):**
- Native mobile apps (iOS and Android)
- AI-powered study group recommendations
- Integration with HKU SPACE official systems

**First priority:** Privacy controls (what 96% of users asked for)

---

## SLIDE 46: TEAM CONTRIBUTIONS

**Image Placeholder:** [Three team member names with role descriptions]

**Text:**

# Who Did What

| Member | Role | Key Contributions |
|--------|------|-------------------|
| Xavier Wong | Backend Lead | Server, database, API, authentication, deployment |
| Kwok Ho Yin | Frontend Lead | User interface, calendar, drag-and-drop, forms |
| Young Ho Tim | Data Lead | PDF parsing, data pipeline, testing, documentation |

**Everything was collaborative.** We all contributed to documentation, testing, and the project logbook.

---

## SLIDE 47: TRY IT YOURSELF

**Image Placeholder:** [Screenshot of the live website with URL]

**Text:**

# Live Demo Available

**URL:** `https://platform-efs2.vercel.app`

**Can't show live demo?** We have screen recordings of every feature.

**To try it yourself:**
1. Create an account
2. Wait for admin approval (or ask us to approve)
3. Log in and explore

**Repository available upon request for examiners.**

---

## SLIDE 48: ACKNOWLEDGMENTS

**Image Placeholder:** [Thank you graphic with logos]

**Text:**

# Thank You

**We want to thank:**

- **Mr. Lau Chung Yin (Tim)** – Our supervisor for guidance and feedback
- **HKU SPACE Community College** – For the opportunity and resources
- **The 24 students** – Who gave us honest feedback
- **Open source community** – For MERN stack, PyMuPDF, and all the libraries

**Without these, EFS wouldn't exist.**

---

## SLIDE 49: QUESTIONS?

**Image Placeholder:** [Q&A graphic with question marks]

**Text:**

# Questions?

**We'd love to answer:**

- Technical implementation details
- User testing methodology
- Future plans
- Anything else!

**Direct questions to:**
- Xavier – Backend, database, deployment
- Kwok – Frontend, UI, calendar
- Tim – Data, PDF parsing, testing

---

## SLIDE 50: BACKUP - ARCHITECTURE DETAILS

**Image Placeholder:** [Detailed three-tier architecture diagram]

**Text:**

# Appendix: Complete Architecture (For Reference)

**Available if you have technical questions:**

- Complete API documentation (25+ endpoints)
- Database schema diagrams
- PDF parsing script details
- Security implementation details

**Ask us during Q&A.**
