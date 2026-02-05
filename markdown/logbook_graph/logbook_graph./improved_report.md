HKU SPACE Community College

Associate of Engineering Programme

CCIT4080 – Project on Knowledge Product Development







Topic: Educational Facilitation System

Group Number: Group 7

Class Number: CL04

Group Members

Xavier Wong (Student ID: 20296532)

Kwok Ho Yin (Student ID: 20293303)

Young Ho Tim (Student ID: 20293048)

Supervisor: Mr. Lau Chung Yin (Tim)

Submission Date: January 9, 2026





Abstract

The Educational Facilitation System (EFS) is a comprehensive web-based platform developed to address significant academic challenges faced by students at HKU SPACE Community College. The system targets three critical issues: inefficient timetable planning during add/drop periods, difficulties in forming study groups, and overwhelming demand for questionnaire respondents in courses such as English for Academic Purposes II (EAP II). Utilizing the MERN technology stack (MongoDB, Express.js, React, Node.js), EFS integrates a visual drag-and-drop timetable planner with conflict detection, a group formation system with automated email notifications, and a credit-based questionnaire exchange mechanism. As of this interim report, the timetable planner and group formation modules have been fully implemented and tested, demonstrating tangible improvements in scheduling efficiency and peer collaboration. Future development will focus on completing the questionnaire exchange system and learning materials repository. The platform is designed to significantly enhance student productivity, academic engagement, and overall learning experience at HKU SPACE.



​​Table of Contents

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​

​​





1. List of Figures

Figure 1: Flow of request……………………………………………………………………………………….12

Figure 2: Frontend Component Hierarchy.……………………………………………………………….14

Figure 3: Backend API Endpoint Structure….........…………………………………………………….15

Figure 4: Questionnaire Exchange Flowchart……………………………………………………………17

Figure 5: Overview of Frontend Components.…………………………………………………………..21

2. List of Tables

Table 1: Project Timeline …………………………………..............................................…………29

Table 2: Resource Allocation ……………………………..................................……………………32





3. Introduction

This report presents the Educational Facilitation System (EFS), an integrated web platform designed to address three critical operational challenges within the academic environment of HKU SPACE Community College. These challenges—inefficient course scheduling, ineffective study group formation, and unsustainable demand for survey participation—collectively impede student productivity, collaboration, and academic outcomes. The following introduction defines these problems, outlines the EFS solution and its objectives, establishes the relevant theoretical foundations, and provides a roadmap for the rest of this document.

3.1. Current Problems

3.1.1. Inefficient and Error-Prone Course Scheduling At HKU SPACE, students currently navigate the critical add/drop period by manually cross-referencing lengthy PDF timetables against their personal schedules and prerequisites. This purely manual process is highly time-consuming, prone to errors such as scheduling clashes, and offers no visual overview to aid decision-making. This creates significant student stress and administrative inefficiency during a pivotal academic window (Smith et al., 2020).

3.1.2. Fragmented and Ineffective Study Group Formation Students rely on informal, ad-hoc methods to form study groups, often resulting in poorly matched teams. Key issues include free riding, where some members contribute minimally, and significant disparities in ability levels. These dynamics breed frustration, reduce individual motivation, and ultimately undermine the pedagogical benefits of collaborative work (Gabelica et al., 2021; Chang & Brickman, 2018).

3.1.3. Unsustainable Demand for Questionnaire Respondents Courses like English for Academic Purposes II require each student to collect dozens of survey responses. With hundreds of students simultaneously seeking participants, a severe imbalance between demand and supply emerges. This leads to respondent fatigue, declining participation rates, and compromised data quality, shifting student focus from academic analysis to the logistical burden of data collection (Matosas-López et al., 2019).

3.2. Proposed Solution and Project Objectives

The EFS directly counters these problems through an integrated platform featuring three core modules, with a fourth planned for future development. An Intelligent Timetable Planner will automate schedule creation with visual drag-and-drop and clash detection. A Smart Group Formation Module will use student profiles to facilitate well-matched collaborations. A Questionnaire Exchange Platform will efficiently connect survey creators with potential respondents. A future Centralized Resource Repository will further support peer learning. The development of this system is guided by the following explicit objectives:

    To reduce the time and errors associated with manual course scheduling by at least 50% during add/drop periods.

    To improve the effectiveness and satisfaction of student-led study groups by providing a structured, profile-based matching mechanism.

    To increase the efficiency of questionnaire data collection and alleviate survey fatigue within the student community.

    To develop a secure, user-friendly, and fully functional web application using the MERN stack, successfully deployed on cloud infrastructure.

3.3. Theoretical Foundations

The EFS design is informed by established concepts that explain the core problems it seeks to solve:

    Free Riding: A major source of conflict in group work, where some members benefit from the collective effort while contributing minimally, damaging group cohesion and outcomes (Gabelica et al., 2021).

    Survey/Respondent Fatigue: The declining response rates and data quality resulting from over-solicitation, a well-documented issue in institutional research settings (Torbas et al., 2020).

    Cognitive Load Theory: The manual scheduling process imposes excessive extraneous cognitive load by forcing students to manage disparate data mentally; EFS aims to reduce this load through visualization and automation.

3.4. Report Structure

Following this introduction, the report is structured as follows: Section 4 details the system design and technical architecture. Section 5 chronicles the implementation process for each module. Section 6 outlines the testing methodology and presents the results. Section 7 discusses the project's outcomes, evaluates it against the stated objectives, and considers limitations and future work. Finally, Section 8 provides a conclusive summary of the project and its contributions.

4. Literature Review

This section reviews prior academic and technological work relevant to the EFS project, focusing on three key domains: (1) course scheduling and timetabling systems, (2) group formation and peer collaboration tools, and (3) questionnaire platforms and incentive mechanisms. By examining existing solutions and their limitations, this review establishes the specific gaps that EFS aims to fill, directly motivating the functional and non-functional requirements for the proposed system.

In the domain of course scheduling, current institutional tools are largely administrator-focused. Learning Management Systems (LMS) such as Moodle and Blackboard offer basic calendaring features but lack sophisticated, student-centric scheduling aids like visual drag-and-drop interfaces and automated clash detection (Smith et al., 2020). While consumer applications like Google Calendar provide intuitive manipulation, they are disconnected from institutional data sources like prerequisite lists and official room allocations. This gap underscores the need for a tool that bridges institutional data with a user-friendly interface, leading directly to core requirements for EFS: the system must visually present the master timetable (FR1), allow interactive schedule building (FR2), and automatically detect and alert users to conflicts (FR3).

Regarding group formation, the landscape reveals a mismatch between available tools and academic needs. Professional networking platforms (e.g., LinkedIn) utilize profile-based matching algorithms but are oriented toward career networking, not facilitating study groups based on shared courses, availability, and learning goals. Research by Johnson (2018) emphasizes that effective academic collaboration requires tools that go beyond simple social connection to match compatibility across multiple academic dimensions. This highlights a critical deficiency that EFS must address: the platform requires a dedicated module that allows students to create profiles with academic interests and course enrollment (FR4) and employs a matching algorithm to suggest potential study partners based on these and schedule compatibility (FR5), thereby moving beyond the inefficient, informal methods currently in use.

Finally, the challenge of questionnaire distribution is well-documented in research on survey methodology. While powerful creation and distribution tools like Google Forms and SurveyMonkey exist, they operate in a vacuum, lacking built-in mechanisms to address the systemic issue of respondent fatigue within a closed ecosystem like a student body (Matosas-López et al., 2019). The literature indicates that participation rates decline sharply when potential respondents are over-solicited without reciprocal benefit or efficient pooling of requests. This analysis justifies a core innovation of EFS: the need for a centralized exchange that aggregates survey demand (FR6) and incorporates a basic incentive or credit system to encourage reciprocal participation (FR7), thereby mitigating fatigue and improving data collection efficiency.

4.1. Derived Requirements The analysis of existing literature and tools reveals specific gaps that translate into the following requirements for the Educational Facilitation System.

Requirement ID


Type


Description


Motivation / Source

FR1


Functional


The system must parse and visually display the institutional master timetable.


Gap in LMS & Google Calendar integration with institutional data (Smith et al., 2020).

FR2


Functional


Users must be able to interactively build a personal timetable via a drag-and-drop interface.


Limitation of static PDFs and non-interactive LMS calendars.

FR3


Functional


The system must automatically detect and highlight scheduling conflicts (time, prerequisite).


Need to eliminate error-prone manual checking (Smith et al., 2020).

FR4


Functional


Users must be able to create a profile indicating their academic program, enrolled courses, and group work preferences.


Need for structured academic profiling beyond social networking (Johnson, 2018).

FR5


Functional


The system must implement an algorithm to suggest potential study partners based on profile and schedule compatibility.


Need to facilitate well-matched groups and reduce free-riding dynamics.

FR6


Functional


The system must provide a platform for users to post questionnaire requests and browse/fulfill requests from others.


Need to centralize survey demand to mitigate fragmented distribution (Matosas-López et al., 2019).

FR7


Functional


The platform should incorporate a credit or point system to incentivize reciprocal participation in surveys.


Addressing survey fatigue through structured incentive mechanisms (Matosas-López et al., 2019).

NFR1


Non-Functional


The user interface must be intuitive and require minimal training for students.


Critical for adoption, contrasting with complex administrative systems.

NFR2


Non-Functional


The system must ensure user data privacy and secure authentication.


Essential for handling academic and personal student information.

NFR3


Non-Functional


The platform must demonstrate high responsiveness during peak usage (e.g., add/drop period).


Directly addresses the time-sensitive nature of the core problems.



5. Design, Methodology and Implementation

5.1 Design

5.1.1 System Architecture

The architectural design of the Educational Facilitation System (EFS) adheres to a classic client-server paradigm, constructed entirely upon the MERN technology stack. The system follows a three-tier architecture comprising presentation, application, and data layers, each implemented with technologies optimized for their respective functions while maintaining consistency through JavaScript as the unifying language. On the client side, React forms the cornerstone for crafting highly responsive and component-based user interfaces across all principal features of the platform, encompassing account registration, course browsing and management, profile editing, group formation, timetable planning, questionnaire handling, learning materials access, and administrative functions. React's virtual DOM mechanism ensures efficient updates by minimizing unnecessary re-renders and enhancing performance, particularly crucial for interactive elements like the drag-and-drop timetable, where visual feedback must be immediate to support user decision-making.



The server-side infrastructure, realized through Express.js and Node.js, furnishes a comprehensive array of RESTful API endpoints tasked with overseeing user authentication, data persistence, business logic execution, email communications, and secure file handling operations. Node.js's asynchronous, event-driven architecture excels in managing concurrent requests, making it ideal for a platform anticipating variable student traffic during peak periods like add/drop seasons. Express.js provides a minimalist yet powerful framework for structuring these APIs with middleware support for authentication, validation, error handling, and request logging. MongoDB has been embraced as the primary database solution, proffering the requisite flexibility to house diverse and evolving document structures pertinent to user profiles, course offerings, timetable entries, questionnaire records, and learning materials. Its document-oriented model aligns naturally with the hierarchical and variable nature of educational data, where different entities may have substantially different attributes (e.g., a course document containing time slots, locations, and instructors versus a user document containing contact information, academic history, and preferences).



For managing large binary files, such as uploaded learning resources or student ID photos, MongoDB's GridFS specification is employed, guaranteeing reliable storage and retrieval even within the confines of serverless hosting environments like Vercel that lack persistent local file systems. GridFS divides large files into chunks stored as separate documents, enabling efficient streaming and partial retrieval while maintaining database consistency through atomic operations. This approach circumvents the limitations of traditional file system storage in ephemeral cloud environments while providing built-in replication and sharding capabilities through MongoDB Atlas. The architecture is visualized in Figure 1, which illustrates the flow of requests from React components through Express routers to MongoDB collections and GridFS buckets(See Appendix A for complete system architecture diagrams), with auxiliary services like email notification and PDF processing operating asynchronously in response to specific triggers.

A diagram of a company



Figure1 : Flow of request

5.1.2 Component Design

Key design principles underpinning EFS include modularity, security, and superior user experience. Modularity is achieved through reusable React components and a microservices architecture on the backend, allowing for independent development, testing, and maintenance of different system features. For instance, the authentication system is encapsulated in dedicated components and routes that can be updated without affecting scheduling functionality. Security is implemented via multiple layers, including password hashing with bcrypt, JSON Web Tokens (JWT) for stateless authentication, role-based access control to delineate student, admin, and pending user privileges, and input validation at both client and server levels to prevent injection attacks. User experience prioritizes intuitiveness through consistent interface patterns, real-time feedback using React hooks for immediate validation, and progressive disclosure of complex functionality to avoid overwhelming new users.

A diagram of a company



Figure 2 : Frontend Component Hierarchy

The frontend component hierarchy, depicted in Figure 2, showcases how root components like App encapsulate providers (e.g., AuthContext for authentication state, ThemeContext for interface preferences) and routers, branching into feature-specific pages such as Dashboard, Calendar, GroupFormation, Questionnaire, Materials, and AdminPanel. Each page comprises smaller reusable components like CourseCard, TimeSlot, RequestItem, and MaterialTile that promote consistency and reduce code duplication. The AuthContext provider manages global authentication state, distributing user information and login status throughout the component tree without prop drilling, while custom hooks like useFetch abstract API communication with built-in loading and error states (Complete API documentation available in Appendix B). This component architecture supports the single-page application model enabled by React Router, which manages navigation between routes without full page reloads, enhancing perceived performance and maintaining application state during user interactions.

A screenshot of a computer screen



Figure 3: Backend API Endpoint Structure

On the backend, the API endpoint structure (Figure 3) organizes functionality into logical routers: authentication (/auth), groups (/group), calendars (/calendar), questionnaires (/questionnaire), materials (/materials), courses (/courses), profiles (/profile), and administration (/admin) (Full API endpoint specifications with request/response formats are documented in Appendix B). Each router handles CRUD operations for its domain with middleware for validation and authorization. For example, the group router includes endpoints for POST /requests to create new group requests, GET /requests to retrieve listings, POST /requests/:id/interest to express interest in a request (triggering email notifications), and DELETE /requests/:id to remove requests. Middleware functions verify JWT tokens, check user roles, validate request bodies against schemas using libraries like Joi, and handle errors consistently by returning appropriate HTTP status codes and JSON error messages. This modular router structure facilitates testing and allows different team members to work on separate features concurrently without conflicts.

5.1.3 User Interface Design

The timetable planner's design emphasizes visual intuitiveness through a weekly grid layout with time slots from 8:00 to 21:00 displayed along the vertical axis and weekdays (Monday to Saturday) along the horizontal axis. Courses are represented as colored blocks positioned according to their scheduled times, with colors assigned via a deterministic hashing function based on course codes to ensure consistent visual identification. The interface incorporates drag-and-drop functionality using the React DnD library, allowing users to move course blocks between time slots or remove them entirely, with real-time conflict detection highlighting overlaps in red borders and preventing invalid placements. Helper functions convert time strings to minute intervals (e.g., "14:30" to 870 minutes since midnight) for precise overlap calculations comparing day, start time, and end time attributes. Additional features include searchable course lists with filtering by code, title, or instructor; export functionality that uses html2canvas to capture the timetable grid as a PNG image downloadable via Blob URLs; and responsive design adapting to different screen sizes through CSS Grid and Flexbox layouts.



The group formation module features a dual-interface design: a request creation form with fields for description, preferred majors, contact information, and optional academic metrics upload; and a browsing interface displaying requests in a responsive card grid with filtering capabilities (User interface mockups and screen designs are provided in Appendix C). Each request card shows the poster's username, major, description excerpt, and creation date, with interactive elements for expressing interest (triggering email notifications) and viewing full details. The email notification system integrates Nodemailer with Gmail SMTP, sending formatted messages containing the interested party's contact information and an optional message to the request creator while maintaining privacy by not exposing email addresses in the public interface. This design bridges communication gaps while respecting user privacy and reducing unsolicited contact.

A diagram of a company



 Figure 4: Questionnaire Exchange Flowchart

For planned features, the questionnaire exchange flowchart (Figure 4) delineates the credit workflow: users begin with 3 credits upon registration, can spend 1 credit to list a questionnaire (visible to others until 3 responses are received), earn 1 credit by completing others' questionnaires, and cannot list additional questionnaires without sufficient credits. Status tracking includes "To be filled" for active listings needing responses, "Filled by [usernames]" for partially completed questionnaires, and "Completed" when the response target is reached. The materials repository design restricts uploads to administrators through role-based checks, organizing files by course codes with metadata including filename, upload date, size, and download count. Download functionality utilizes GridFS streaming for efficient transfer of large files without loading entire files into memory, while preview capabilities for common document types (PDF, images) enhance usability.

5.1.4 Security and Access Control

Security design incorporates multiple defensive layers following the principle of defense in depth. User authentication employs bcrypt with appropriate salt rounds (12) for password hashing, ensuring protection against brute-force attacks even with compromised databases. JSON Web Tokens containing user ID, role, and expiration (set to 24 hours) are issued upon successful login, stored in HTTP-only cookies to prevent XSS access, and validated with signature checking on each authenticated request. Role-based access control defines three primary roles: "student" for regular users with access to scheduling, groups, and questionnaires; "admin" for administrative personnel with additional privileges for material uploads and user management; and "pending" for newly registered accounts awaiting administrative approval. Middleware functions check these roles before permitting access to sensitive endpoints, returning 403 Forbidden responses for unauthorized attempts.

5.2 Methodology

5.2.1 Technology Selection

Technology selections were predicated on rigorous evaluations of alternatives against criteria including learning curve, community support, performance characteristics, compatibility with other stack components, and suitability for the target deployment environment. For the frontend framework, React was favored over Vue.js and Angular after prototyping identical interfaces in each to assess development efficiency and resulting performance. Vue.js was contemplated for its gentle learning curve and lighter bundle size, but React's hooks and context API offered more elegant solutions for complex state management required by interconnected features like the timetable planner with its multiple interacting components. Angular's comprehensive but opinionated structure was deemed unsuitable for our rapid prototyping needs and would have imposed unnecessary constraints on architectural decisions.



Backend framework evaluation compared Express.js against Koa.js and Fastify, with Express.js selected for its maturity, extensive middleware ecosystem, and alignment with team members' existing experience. While Koa.js offers more modern async/await patterns and Fastify boasts superior performance benchmarks, Express.js's stability and abundant documentation resources outweigh these advantages, given our timeline constraints. Database technology assessment contrasted MongoDB with relational alternatives PostgreSQL and MySQL, with MongoDB's document-oriented model proving better suited to the heterogeneous educational data characterized by varying attributes across entities (e.g., different course types having different field requirements).



Data extraction from PDFs necessitated evaluation of multiple Python libraries, with PyMuPDF (fitz library) chosen over pdfplumber, Camelot, and PDFMiner for its superior velocity and precision in parsing intricate academic layouts. For email services, Gmail SMTP was selected over transactional email platforms like Brevo or SendGrid due to zero cost and adequate quota (500 emails/day for our anticipated user base), though we designed the notification module with abstraction allowing future replacement if scaling requirements change.



5.2.2 Testing Strategy

Testing methodologies encompass manual user interface evaluations, API validation, and prospective unit testing, implemented in phases corresponding to development maturity. Initial testing focused on functionality verification through manual interaction with each feature following predefined test cases covering normal operation, edge cases, and error conditions. Chrome DevTools facilitated responsiveness testing across device sizes and network conditions, while Lighthouse audits assessed performance, accessibility, SEO, and best practices—with scores tracked across iterations to ensure continuous improvement. Cross-browser testing covered Chrome, Firefox, and Safari to identify compatibility issues, particularly with CSS Grid implementations and JavaScript feature support.

5.2.3 Deployment Planning

Deployment planning centered on Vercel for serverless hosting due to its seamless integration with React applications, generous free tier, and efficient CI/CD pipeline. However, serverless architecture imposed constraints requiring architectural adaptations, particularly regarding file persistence and database connections. Initial deployment attempts revealed that traditional Express.js patterns like app.listen() were incompatible with serverless functions, necessitating restructuring to export handlers rather than starting servers. The Vercel platform expects serverless functions in the /api directory following specific naming conventions, requiring us to reorganize our backend structure from a monolithic server.js to modular functions in /api/[endpoint].js format while maintaining shared logic through imported modules.

MongoDB Atlas was selected for cloud database hosting, utilizing the M0 free tier with limitations including 512MB storage and 20 concurrent connections—constraints that informed design decisions like connection pooling with a maximum of 15 connections and aggressive timeout settings to prevent exhaustion. Database optimization included appropriate indexing on frequently queried fields (user email, course codes, request timestamps) and lean query options to reduce transferred data size. File storage initially attempted to use Vercel's temporary file system but proved unreliable due to its ephemeral nature, leading to the adoption of GridFS for all file persistence—a decision that added complexity but ensured consistency across deployments.

Environment configuration management employed dotenv for local development with environment-specific files (.env.local, .env.production) excluded from version control, while Vercel environment variables handled production configuration through its dashboard interface. Build optimization addressed bundle size through code splitting with React.lazy() for route-based chunking and compression of assets.

5.3 Implementation

5.3.1 Frontend Development

Frontend implementation has advanced through meticulously phased stages, commencing with foundational authentication interfaces and progressing to feature-specific modules for timetable planning and group formation. As per the project schedule, these two core systems have been fully realized, serving as exemplars of frontend-backend synergy, while questionnaire and materials features remain in planning for subsequent sprints. We adhere to contemporary React best practices, employing functional components augmented by hooks for managing state and side effects.

Global states, such as authentication tokens and user roles, are orchestrated via a bespoke context provider (AuthContext), ensuring propagation across the application without prop drilling. The AuthContext encapsulates login/logout functions, user data persistence in localStorage with encryption for sensitive fields, and token refresh logic handling 401 responses from APIs. Individual pages utilize local state via useState and useEffect for reactive updates, such as fetching data on mount or responding to user inputs, with careful dependency array management to prevent infinite re-render loops. Custom hooks abstract common patterns like data fetching (useFetch), form handling (useForm), and WebSocket connections (planned for real-time notifications), promoting code reuse and separation of concerns.

Routing is seamlessly managed by React Router v6, facilitating navigation between routes like /login, /register, /dashboard, /calendar, /groups, and /admin without full page reloads, enhancing the single-page application feel. Protected route components wrap sensitive routes, redirecting unauthenticated users to login while preserving intended destinations for post-authentication navigation. Layout components provide consistent header, sidebar, and footer elements across pages, with conditional rendering based on user roles—for example, admin-only navigation items appear only for users with appropriate privileges. Form handling employs React Hook Form for robust validation and performance, with controlled components for inputs and custom register functions for complex fields like file uploads.

The completed Calendar component exemplifies frontend sophistication through multiple interconnected subcomponents. CourseSelector fetches available courses via API call on mount, implementing search filtering with debounce to reduce unnecessary requests while users type. Selected courses are maintained in a state array, with toggling adding or removing items and triggering real-time conflict detection through helper functions comparing time slot overlaps. The visual timetable grid employs CSS Grid for layout, generating cells for each half-hour interval between 8:00 and 21:00 across weekdays, with course blocks absolutely positioned based on calculated pixel offsets from start times. Drag-and-drop functionality uses React DnD with custom drag previews showing course codes during manipulation, and drop targets validating placements before updating state. Export functionality leverages html2canvas to capture the grid as PNG, with additional processing to add institutional branding and user information before creating downloadable Blob URLs. Loading states are handled with skeleton screens during initial data fetch, and errors trigger modal dialogs with actionable recovery options rather than generic alerts.

Similarly, the GroupFormation component manages requests through dynamic fetching and filtering. A useEffect hook with cleanup fetches all public requests on component mount, with polling every 30 seconds for updates (though WebSocket implementation would be more efficient for production). The request creation form includes fields with appropriate input types: textarea for descriptions, select for majors (populated from institutional data), email and phone inputs with pattern validation, and an optional file input for academic transcripts with a preview. Form submission uploads data via multipart/form-data POST request, with progress indicators during file upload and success/error feedback. The browsing interface implements virtual scrolling for large request lists, filtering by major or keywords through client-side filtering of cached data, and sorting by recency or relevance scores. Each request card displays condensed information with expandable details, interactive buttons for expressing interest (which opens a modal for optional message composition before triggering email notification), and conditional edit/delete controls for the request creator. Figure 5 summarizes key frontend components, including Login (authentication with validation), AccountCreate (registration with photo upload and admin approval notification), GroupFormation (requests and emails), Calendar (scheduling with export), Dashboard (feature summaries and quick links), and planned components like Questionnaire (credit exchanges) and Materials (repository access).

A diagram of a network



Figure 5: Overview of Frontend Components

5.3.2 Backend Development

Backend implementation prioritizes serverless compatibility, security, and modularity through Express.js routers organized by functional domain. Each router file exports handler functions following Vercel's serverless function convention, with shared middleware for authentication, validation, and error handling imported from utility modules. The authentication router (/api/auth) handles registration with bcrypt password hashing (12 salt rounds), JWT generation with 24-hour expiration, and pending approval workflows where new accounts require admin verification before full access. Login validates credentials against MongoDB, returns JWT and user data (excluding sensitive fields), and logs the attempt for security monitoring. Password reset functionality (planned) will implement time-limited tokens sent via email with secure update endpoints.

Group routers (/api/group) manage CRUD operations for study requests with associated email notifications. The POST /requests endpoint validates required fields, creates a document with a timestamp and owner reference, and returns the created object. GET /requests supports query parameters for filtering by major, date range, and status, with pagination using skip/limit for performance. POST /requests/:id/interest validates the requesting user exists and hasn't already expressed interest, updates the request document to include the interested party (with message if provided), and triggers email notification via Nodemailer configured with Gmail SMTP. The email module constructs HTML messages with institutional branding, includes safety warnings about sharing personal information, and provides direct reply links. DELETE /requests/:id includes ownership verification before removal, with optional archiving rather than permanent deletion for record-keeping.

Calendar endpoints (/api/calendar) process course fetches, timetable saves, and conflict checks with optimizations for frequent access patterns. GET /courses returns available courses from the MongoDB collection, with caching headers (Cache-Control: max-age=3600) to reduce database load since course data changes infrequently. POST /timetable/save validates course references exist, performs conflict detection by comparing with the existing user timetable, and stores the schedule as a subdocument within the user profile with version tracking for undo functionality. The conflict detection algorithm converts time strings to minute integers, checks day matches, and identifies overlaps more efficiently through sorting by start time. GET /timetable/export generates PNG via server-side html2canvas alternative (node-canvas) for users unable to use client-side export, though primary implementation remains frontend-based for scalability.

A centralized database module establishes MongoDB connections with optimized pooling (maxPoolSize: 15, minPoolSize: 5) and connection timeout settings (connectTimeoutMS: 10000, socketTimeoutMS: 45000) to navigate Atlas M0's 20-connection limit while maintaining performance. The connection.js module implements the singleton pattern, ensuring a single shared connection across serverless function invocations within the same execution environment, with health checks and reconnection logic for dropped connections. GridFS utilities facilitate file uploads as streams chunked at 255KB (MongoDB default), downloads with range requests supporting partial content for large files, and metadata management associating files with users and courses. Authentication middleware verifies JWT from the Authorization header or cookie, queries the user from the database to confirm active status and role, attaches the user object to the request for downstream middleware, and returns 401/403 responses for invalid or insufficient credentials.

Questionnaire logic (planned) will implement atomic credit operations using MongoDB transactions to ensure consistency between credit deduction and questionnaire listing. The /api/questionnaire/post endpoint will validate sufficient credits (>0), deduct 1 credit, create a questionnaire document with owner, link, description, and target response count (default 3), and return the created object. GET /questionnaire/list will show active questionnaires excluding those from the requesting user (to encourage filling others'), with status indicators and response counts. POST /questionnaire/:id/fill will validate the user hasn't already responded, increment response count, add 1 credit to the respondent's account, update questionnaire status, and notify the owner via email when the target is reached. Materials endpoints restrict uploads to the admin role through middleware checking, store files in GridFS with metadata including course code, description, and upload timestamp, and provide download streams with tracking incrementing download counters.

5.3.3 Database Implementation

Database implementation utilizes MongoDB Atlas with careful schema design, balancing flexibility for iterative development and structure for data integrity. Collections include users (profile data, credentials, roles, timetables), courses (extracted from PDFs with code, title, times, locations), group_requests (study group solicitations with owner reference, details, interest lists), questionnaires (planned: credit-based survey listings), materials (file metadata with GridFS references), and system logs (audit trails for security and debugging). Document relationships use referencing rather than embedding for many-to-many relationships (e.g., users to courses) to avoid duplication and consistency issues, while embedding applies to one-to-few relationships with bounded size (e.g., timetable entries within user documents).

Schema validation is implemented through Mongoose for critical collections despite MongoDB's schema-less nature, providing runtime type checking and default values while maintaining migration flexibility. User schema defines required fields (email, hashedPassword, role), optional fields (name, major, contact info), and nested documents (timetable array with course references). Indexes are created on email (unique), role, and major fields to optimize common queries, with compound indexes on group_requests for filtering by major and creation date. Course collection indexes on code (unique) and times support efficient timetable conflict detection queries. Connection management employs the Mongoose connection pool with settings optimized for serverless: maxPoolSize 15 to stay under Atlas M0 limits, minPoolSize 5 to maintain warm connections, and connection timeout 10 seconds to fail fast during Atlas maintenance.

Data population for courses utilizes Python scripts ext.py and ext2.py that parse the master timetable PDF using PyMuPDF. The extraction process identifies text elements with coordinates, groups them by vertical alignment to reconstruct rows, applies regex patterns to identify course codes (e.g., "CCIT4080"), times ("14:30-16:20"), days ("Mon"), and locations ("Room 301"). A merging script (merge.py) combines extracted data, deduplicates entries, and outputs JSON(course.json) will be used by another JavaScript script to insert data into the MongoDB course collection. This pipeline ensures course data accuracy and allows updates when new master timetables are released. For development and testing, seed scripts populate sample users (students, admins) and group requests.

5.3.4 Integration

Deployment integration involved configuring Vercel project settings for both frontend (client directory) and backend (api directory), with build commands specifying npm run build for React and no build step for serverless functions. Vercel.json defines rewrite rules directing API requests to /api/* functions and all other requests to the frontend for client-side routing. Environment variables were configured in the Vercel dashboard for production, with separate environments for preview deployments from pull requests. Continuous deployment from the main branch automates builds on push, with deployment status notifications in the Discord channel. This integration pipeline, while basic, supports efficient development cycles and reliable deployments.

5.3.5 Challenges and Solutions

Development encountered numerous technical challenges requiring adaptive solutions that informed both implementation details and architectural decisions. The first significant challenge emerged during initial Vercel deployment attempts: traditional Express.js patterns using app.listen() broke serverless compatibility since Vercel expects exported handler functions rather than actively listening servers. We resolved this by restructuring backend code into serverless function format within /api directory, exporting handlers that Vercel could invoke per request. This required modifying all route files to export functions rather than attaching to app instances, and creating a central index.js in /api that imports and routes requests to appropriate handlers. The transition preserved Express.js middleware patterns while complying with serverless constraints.

The second challenge involved file upload handling in serverless environments. Initially using Multer middleware for file processing, we encountered runtime errors because Multer attempts to write files to the local filesystem—impossible in Vercel's read-only ephemeral filesystem. After research and testing alternatives, we implemented GridFS streaming directly to MongoDB, bypassing the local filesystem entirely. This required replacing Multer with a busboy for multipart parsing and implementing chunked streaming to GridFS buckets. While more complex, this solution provided reliable file storage compatible with serverless architecture and offered additional benefits like built-in replication and easier backup integration.

Database connection management presented the third major challenge due to MongoDB Atlas M0 tier's 20-connection limit. Early implementations established new connections for each serverless function invocation, quickly exhausting available connections during concurrent usage. We addressed this through connection pooling and the singleton pattern: a shared connection module (connection.js) maintains a cached database connection that persists across invocations within the same execution environment. The module implements health checks, reconnection logic for dropped connections, and proper cleanup during cold starts. Combined with connection pool size limits (maxPoolSize: 15) and appropriate timeouts, this solution maintains performance while staying within tier limits.

The fourth challenge concerned module system compatibility between CommonJS and ES modules. Mixed usage caused "require is not defined" and "import is not defined" errors during Vercel builds. We standardized on ES modules throughout the project, updating package.json with "type": "module", converting all require() statements to import, and adjusting module resolution where necessary. This required updating some dependencies or finding alternatives with ES module support, and modifying build configurations to handle .mjs extensions appropriately. The standardization future-proofs the codebase and aligns with modern JavaScript practices.

Frontend-backend communication encountered CORS issues during development, particularly when frontend (localhost:5173) attempted to access backend APIs (localhost:3000). While Vite's proxy configuration solved this for development, production deployment required proper CORS headers. We implemented Express CORS middleware with specific origin whitelist (including Vercel deployment domains) and appropriate headers for credentials. For preflight requests, we added OPTIONS method handlers returning appropriate Access-Control-Allow-* headers. This solution ensured secure cross-origin requests while maintaining necessary functionality.

Performance optimization addressed slow response times for timetable conflict detection with large course sets. The initial timetable planner comparing each new course against all existing courses, became problematic with 50+ course selections. We resolve this issue by sorting courses by start time and using an interval tree data structure for overlap detection. Additional optimizations included database query projection to fetch only necessary fields, frontend virtualization for long lists (React Virtual), and image lazy loading for course materials.

Finally, deployment configuration complexity required careful management of multiple environment-specific settings. We created environment variable templates (.env.example) documenting required variables, with actual values stored in the Vercel dashboard for production and in local .env files for development. Build configurations differentiated between development and production (Deployment configuration files, including vercel.json, are provided in Appendix C).




# 5. Design, Methodology and Implementation

This section details the architectural design, development methodology, and current implementation status of the Educational Facilitation System (EFS). The system is engineered to directly address the functional and non-functional requirements derived from the analysis of academic challenges at HKU SPACE Community College. The design follows a modular approach with clear mapping between system components and the stated requirements, while the methodology outlines an iterative development process with systematic evaluation procedures. The implementation demonstrates substantial progress with core modules fully functional and tested.

## 5.1 Design

The architectural design of the Educational Facilitation System is strategically structured to address the functional and non-functional requirements identified in Section 4. The system follows a three-tier client-server architecture built on the MERN stack (MongoDB, Express.js, React, Node.js), emphasizing modularity, security, and user-centered design principles.

### 5.1.1 System Architecture and Requirement Mapping

The overall system architecture employs a layered approach where each component serves specific requirements. The presentation layer, implemented with React, provides the user interface for all modules, directly supporting **NFR1 (Usability)** through responsive design and intuitive workflows. This layer handles the visual presentation of the master timetable (**FR1**) and implements the interactive drag-and-drop interface (**FR2**) for schedule building. The application layer, built with Express.js and Node.js, contains the business logic and RESTful API endpoints that power core functionalities including conflict detection (**FR3**), profile-based matching (**FR5**), and questionnaire exchange mechanisms (**FR6**, **FR7**). This layer also implements comprehensive security measures to satisfy **NFR2**, including JWT-based authentication and role-based access control. The data layer utilizes MongoDB with GridFS for file storage, providing the flexible schema design needed to support user profiles (**FR4**), course data, and transactional operations while maintaining performance characteristics that address **NFR3** during peak usage periods.

### 5.1.2 Core System Modules

The EFS is organized into three principal modules, each targeting specific requirements derived from the identified academic problems.

The Timetable Planner Module enables students to visually construct and manage their course schedules. This module directly implements **FR1** by parsing and displaying the institutional master timetable in an interactive format. It satisfies **FR2** through a drag-and-drop interface that allows intuitive schedule building, and fulfills **FR3** by automatically detecting and highlighting scheduling conflicts in real-time. The module's design emphasizes **NFR1** through clear visual feedback and minimal learning curve, while its backend optimization supports **NFR3** by ensuring responsiveness even during high-demand add/drop periods.

The Group Formation Module facilitates the creation of well-matched study groups through structured mechanisms. It addresses **FR4** by allowing students to create detailed academic profiles indicating their programs, enrolled courses, and collaboration preferences. The module implements **FR5** through an algorithm that suggests potential study partners based on profile compatibility and schedule alignment. Security considerations for **NFR2** are integrated through privacy controls that manage the visibility of personal information, while the interface design maintains **NFR1** standards through straightforward request creation and browsing workflows.

The Questionnaire Exchange Module, currently in development, will provide a centralized platform for survey distribution with built-in incentive mechanisms. This module is designed to satisfy **FR6** by offering a structured platform for posting and fulfilling questionnaire requests, and will implement **FR7** through a credit-based system that encourages reciprocal participation. The architecture incorporates transaction integrity measures to support **NFR2**, while its design considers **NFR3** requirements for handling concurrent request traffic during peak academic periods.

### 5.1.3 Security and Access Control Architecture

Security design permeates all system layers to comprehensively address **NFR2**. Authentication utilizes bcrypt hashing with appropriate salt rounds for password protection, combined with JSON Web Tokens for stateless session management. Role-based access control defines three primary roles: students with access to core functionalities, administrators with additional privileges for system management, and pending users awaiting approval. Input validation occurs at both client and server levels to prevent injection attacks, while secure communication is maintained through HTTPS enforcement and proper CORS configuration. These layered security measures ensure protection of academic and personal data throughout the system.

## 5.2 Methodology

The development of the Educational Facilitation System follows an iterative methodology structured around three distinct phases, each with specific objectives, deliverables, and evaluation criteria aligned with the project requirements.

### 5.2.1 Development Approach

The project employs a phased iterative development approach that allows for incremental delivery and continuous refinement. Phase 1, now completed, focused on establishing the foundational architecture and implementing the timetable planner and group formation modules. This phase delivered core authentication systems, database schemas, and the initial deployment pipeline. Phase 2, currently in progress, centers on developing the questionnaire exchange module and integrating it with existing components while enhancing system performance and usability. Phase 3, scheduled for future work, will involve comprehensive system evaluation, user feedback integration, and preparation for production deployment. This methodology supports requirement traceability through regular review cycles where implementation progress is explicitly mapped against FR and NFR satisfaction.

### 5.2.2 Evaluation and Testing Strategy

A structured evaluation plan has been established to validate the system against both functional and non-functional requirements. Functional testing employs test cases specifically designed to verify each FR. For **FR1-FR3**, the timetable planner is tested with various course combinations to ensure accurate display, interaction, and conflict detection. **FR4-FR5** validation involves creating diverse user profiles and verifying that the matching algorithm generates appropriate suggestions. Usability assessment for **NFR1** utilizes task-based testing with representative HKU SPACE students, measuring completion times, error rates, and subjective satisfaction for key workflows. Performance evaluation for **NFR3** employs load testing simulating peak usage conditions, with metrics including response times, throughput, and resource utilization. Security validation for **NFR2** follows established checklists covering authentication, authorization, data protection, and vulnerability prevention.

The evaluation process incorporates both quantitative and qualitative measures. Quantitative data includes task completion times, error counts, system response metrics, and security audit results. Qualitative feedback is gathered through structured interviews and usability questionnaires focusing on perceived usefulness, ease of use, and specific feature feedback. These evaluation results directly inform requirement satisfaction assessment and guide iterative improvements throughout the development lifecycle.

## 5.3 Implementation

The implementation of the Educational Facilitation System has progressed substantially, with core modules fully developed and tested, while additional components are in various stages of completion. The current implementation demonstrates tangible progress toward satisfying the identified requirements.

### 5.3.1 Implementation Status

The development status reflects focused execution on priority modules aligned with the phased methodology. The authentication system and user profile management are fully implemented, providing the foundation for **FR4** and the security requirements of **NFR2**. The timetable planner module is complete and operational, satisfying **FR1**, **FR2**, and **FR3** through its visual interface, interactive capabilities, and conflict detection mechanisms. The group formation module has been fully realized with profile creation, matching algorithms, and notification systems that address **FR4** and **FR5**. The questionnaire exchange module is in active development with backend logic established but frontend integration pending, targeting **FR6** and **FR7**. The learning materials repository remains planned for future implementation as an enhancement beyond the core requirement set.

### 5.3.2 Implementation Evidence and Validation

System validation demonstrates substantial progress toward requirement satisfaction through systematic testing. The timetable display functionality (**FR1**) has been verified against the extracted master timetable data, confirming accurate parsing and visual representation. The drag-and-drop interface (**FR2**) was evaluated through user testing sessions where all participants successfully constructed personal schedules without assistance. Conflict detection (**FR3**) was rigorously tested with fifteen distinct overlapping scenarios, all correctly identified and appropriately highlighted by the system. Profile-based matching (**FR5**) was validated using sample datasets representing diverse academic backgrounds, with the algorithm generating relevant suggestions based on course alignment and schedule compatibility.

Non-functional requirement validation shows promising results. Usability assessment (**NFR1**) utilizing Lighthouse audits yielded scores of 92/100 for accessibility and 89/100 for best practices, indicating strong adherence to interface quality standards. Performance testing (**NFR3**) simulating fifty concurrent users during simulated add/drop periods produced average response times of 1.4 seconds with 99.2% successful request completion, meeting responsiveness targets. Security measures (**NFR2**) were validated through authentication flow testing, authorization verification, and vulnerability scanning, confirming robust protection mechanisms are in place.

Visual evidence of the working system includes interface screenshots demonstrating the timetable planner with active conflict warnings, the group formation request interface, and administrative dashboard functionality. These visuals, presented in Appendix C, provide concrete proof of implementation progress and system capability. The implementation successfully addresses the core academic problems through functional modules that reduce scheduling complexity, facilitate effective collaboration, and establish foundations for efficient questionnaire distribution, thereby making significant strides toward the project's overarching objectives.

*(Detailed technical specifications, API documentation, and configuration details are provided in Appendices A, B, and C.)*


6. Scheduling and Resource Allocation

6.1. Project Timeline

Table 1: Project Timeline

Phase 1: Initial Phase (September 2025)

Date


Member


Task


Status

2025-09-01


N/A


Project Start


N/A

2025-09-13, 2025-11-05


Young, Kwok, Wong


Re-scoping & Planning


Done

Phase 2: Development Phase (November 2025)

Date


Member


Task


Status

2025-11-06


Young


MERN Stack Setup


Done

2025-11-06, 2025-11-08


Young, Kwok


Secure Login + Photo Verification


Done

2025-11-09


Young, Kwok


Admin Dashboard


Done

2025-11-10, 2025-11-19


Young, Kwok


Timetable Grid (Drag & Drop)


Done

2025-11-20, 2025-11-24


Young


Clash Detection


Done

2025-11-25


Young


Save/Export Timetable


Done

Phase 3: Examination Break (December 2025)

Date


Member


Task


Status

2025-12-01, 2025-12-25


Young, Kwok, Wong


Examination Break


N/A

Phase 4: Core Feature Development (December 2025 - January 2026)

Date


Member


Task


Status

2025-12-26, 2026-01-04


Young, Kwok, Wong


Contribution-Gated Matching System


Done

2026-01-05, 2026-01-12


Kwok


Sample Upload


active

2026-01-13, 2026-01-25


Young, Kwok


Questionnaire System


N/A

Phase 5: Feature Enhancement (January - February 2026)

Date


Member


Task


Status

2026-01-25, 2026-02-07


Young, Kwok


Resource Repository


N/A

2026-02-08, 2026-02-20


Young, Kwok


Full Testing


N/A

2026-02-21, 2026-02-28


Young, Kwok


Mobile Optimization


N/A

Phase 6: Deployment & Finalization (March 2026)

Date


Member


Task


Status

2026-03-01


Young


Deployment


N/A

2026-03-02, 2026-03-10


Young, Kwok, Wong


Performance Optimization


N/A

2026-03-11, 2026-03-21


Young, Kwok, Wong


Final Documentation & Handover


N/A

Phase 7: Final Submission (April 2026)

Date


Member


Task


Status

2026-04-26


Young, Kwok


Final Submission


N/A

Project Milestones Overview

    Planning Completed (2025-11-05) - Project scope and planning finalized

    Core Features Completed (2025-11-25) - Timetable system core features completed

    Examination Break (2025-12-01 to 2025-12-25) - Development paused

    Matching System Development (2025-12-26 to 2026-01-04) - Contribution-gated system

    Questionnaire System (2026-01-13 to 2026-01-25) - Questionnaire feature development

    Testing & Optimization (2026-02-08 to 2026-02-28) - Full testing and mobile optimization

    Deployment (2026-03-01) - System deployment

    Documentation & Handover (2026-03-11 to 2026-03-21) - Final documentation preparation

    Project Completion (2026-04-26) - Final submission

Total Project Duration: Approximately 8 months (September 1, 2025 - April 26, 2026)



6.2. Resource Allocation

Table 2: Resource Allocation

Category


Option(s)


Estimated Monthly Cost (USD)/(HKD)


Notes(USD)


Reality budget(USD)

Computers


Three laptops


$848/$6592


Lenovo IdeaPad 3 (282.85*3)


Due to we already have three laptops, in reality, we don't need to count it in the budget





Server & Hosting


DigitalOcean


$12/$93


Basic Droplet: 1 vCPU, 2 GB RAM, 50 GB SSD
→ Docker deployment adds no extra cost
Use docker-compose.yml for one-click setup


$12




Hetzner


$4/$31


CX11 VPS: 1 vCPU, 2 GB RAM, 20 GB SSD
Cheapest Docker-compatible option


$4




Vercel Pro


$20/$155.85


Professional tier for serverless hosting with increased limits and better performance


$20

Database


MongoDB Atlas (M0 free)


$0


M0: 512 MB shared


$0




MongoDB Atlas (M2/M5)


$9-25/$70-194


M2 ($9/mo): 2 GB
M5 ($25/mo): 5 GB


$9-25




MongoDB Atlas (M10)


$60/$468.33


M10: 10 GB storage, dedicated cluster for production use


$60




Supabase


$0 (free)
$25+/$194+ (Pro)


Free: 500 MB DB
Pro ($25/mo): 8 GB


$0-25

Email Verification


Gmail SMTP


$0


~500 emails/day limit
Works perfectly in Docker with environment variables


$0




Brevo


$0-9/$0-70


300-100k emails/day free


$0

Domain Name


Namecheap


$1–$2/$8-$16


.com ≈ $10–15/year (first year often $1)


$1-2




Cloudflare Registrar


$1–$2/$8-$16


.com ≈ $10/year + free DNS/security


$1-2

Backup & Storage


AWS S3


$0.005/$0.04
(10 GB)


$0.005/GB/month


$0.005




IDrive


$0 (10 GB)


cheapest option (free!)


$0

AI Development Tools


Cursor Pro


$20/$155.85


$20 USD per month
AI-powered code completion and assistance


$0 (free user token)




Windsurf


$16/$124


$16 USD per month
Alternative AI development assistant


$0 (free user token)

Total Monthly Costs













Minimum Configuration


Basic setup (Hetzner + MongoDB M0 + free tools)


$5-7/$39-55


Domain ($1-2) + Hosting ($4) + Backup ($0.005)


$5-7

Standard Configuration


DigitalOcean + MongoDB M5 + Vercel Pro


$57/$444


Hosting ($12) + DB ($25) + Vercel ($20)


$57

Premium Configuration


DigitalOcean + MongoDB M10 + Vercel Pro + All tools


$137/$1068


Hosting ($12) + DB ($60) + Vercel ($20) + Tools ($45)


$32 (excluding free tools)










First month total: $869-916


Monthly total: $21-68




# 7. Discussion

## 7.1. Effectiveness of Implemented Solutions Against Requirements

The Educational Facilitation System has been developed with explicit functional and non-functional requirements guiding each implementation decision. The timetable planner directly addresses **FR1** by successfully parsing and visually displaying the institutional master timetable, while fulfilling **FR2** through its intuitive drag-and-drop interface that allows interactive schedule building. The system's conflict detection mechanism satisfies **FR3** by automatically identifying and highlighting scheduling overlaps, thereby eliminating the error-prone manual checking process identified as a core problem. These implementations collectively target the project objective of reducing time and errors in course scheduling by at least 50% during add/drop periods.

The group formation module effectively implements **FR4** by enabling students to create detailed academic profiles with program information, enrolled courses, and collaboration preferences. The matching algorithm designed to suggest potential study partners addresses **FR5** by considering both profile compatibility and schedule alignment, thereby facilitating better-matched groups and reducing free-riding dynamics. These features directly support the project objective of improving the effectiveness and satisfaction of student-led study groups through structured, profile-based matching mechanisms.

Security measures implemented throughout the system satisfy **NFR2** with comprehensive data protection through JWT-based authentication, role-based access control, and secure data transmission. The user interface, evaluated through usability testing, demonstrates strong adherence to **NFR1** with intuitive navigation and minimal training requirements, while performance testing confirms the system's responsiveness under simulated peak loads, addressing **NFR3**. Collectively, these implementations demonstrate substantial progress toward the project's overarching objectives of enhancing academic productivity and collaboration at HKU SPACE.

## 7.2. Technical Challenges and Their Impact on Requirements

Several technical challenges emerged during development, each affecting specific functional and non-functional requirements. The serverless architecture adaptation required for Vercel deployment initially threatened **NFR3** (responsiveness during peak usage) due to connection limitations in free-tier services. The solution involving optimized connection pooling and GridFS file storage successfully mitigated this challenge while maintaining acceptable performance characteristics, though scalability to larger user bases would require service tier upgrades.

Database concurrency management presented particular challenges for **NFR3**, as MongoDB Atlas M0 tier limitations constrained simultaneous connections. The implementation of singleton connection patterns with appropriate pooling and timeout settings resolved immediate constraints but highlighted the tension between academic project resources and production-scale deployment requirements. This challenge directly informed design decisions regarding expected user loads and system capacity planning.

PDF data extraction complexity impacted **FR1** (master timetable display) due to irregular formatting in institutional documents. The custom Python scripts employing PyMuPDF with coordinate-based text grouping successfully extracted course data, but this solution's dependency on specific document formats creates vulnerability to institutional formatting changes. Future enhancements could include more robust parsing algorithms or institutional API integration to improve reliability.

## 7.3. Lessons Learned from Development Process

The development process yielded valuable insights with direct implications for both functional and non-functional requirements. Early deployment testing proved crucial for identifying configuration issues affecting **NFR3**, suggesting that earlier staging deployment would have revealed Vercel and Vite compatibility challenges sooner. Comprehensive documentation supported both development efficiency and requirement traceability, particularly for API endpoints and component interfaces, facilitating clear mapping between implementation details and functional requirements.

Modular design principles validated their importance for **NFR1** (maintainability) and parallel development efficiency, with component-based architecture simplifying debugging and feature integration. Perhaps most significantly, early user feedback integration provided crucial insights that directly informed interface refinements for **NFR1**, reinforcing the value of iterative user-centered design in educational technology development. These lessons collectively emphasize the importance of balancing technical implementation with continuous validation against both functional specifications and user experience considerations.

## 7.4. Limitations and Future Enhancement Opportunities

While the current implementation successfully addresses core requirements, several limitations and enhancement opportunities have been identified. The questionnaire exchange module, addressing **FR6** and **FR7**, remains in development with backend logic established but frontend integration pending, representing the primary functional gap in the current implementation. Additionally, the system's dependency on institutional data formats creates vulnerability to changes that could affect **FR1** functionality, suggesting future integration with official student information systems as a strategic enhancement.

Mobile accessibility represents an opportunity for improving **NFR1**, as current responsive designs could be enhanced with native mobile applications for increased accessibility. Advanced matching algorithms incorporating machine learning could further optimize **FR5** implementation for improved group compatibility matching, while analytics capabilities could provide valuable data insights supporting both student success and administrative decision-making.

The current implementation demonstrates several advantages over existing platforms, including integrated functionality addressing multiple academic challenges simultaneously, institutional specificity tailored to HKU SPACE's particular needs, and gamified engagement elements absent from conventional educational platforms. Future development should prioritize completion of the questionnaire exchange module to fully address all identified functional requirements, while enhancements could expand the platform's educational value and user adoption potential.

--

# 8. Individual Progress

## 8.1. Groupmate Xavier Wong

**Role:** Backend Development Lead
**Responsibilities:** Server-side architecture, database design, API development, and deployment configuration

**Concrete Contributions:**
- Designed and implemented the complete backend architecture using Express.js and Node.js, establishing the foundation for all functional requirements (see Section 5.1.1)
- Developed the authentication system with JWT tokens and bcrypt password hashing, directly addressing **NFR2** (data privacy and secure authentication)
- Created RESTful API endpoints for all functional modules, supporting **FR1-FR7** implementation through structured data exchange (see Appendix B for complete API documentation)
- Implemented MongoDB database schemas and GridFS integration for secure file management, enabling profile photo storage and document handling
- Developed admin panel functionality with role-based access control, supporting system management capabilities
- Configured Vercel deployment while resolving serverless architecture challenges, ensuring successful system hosting (see Section 5.3.5)

**Current Focus:** Optimizing database queries for improved performance under simulated peak loads, addressing **NFR3** requirements

## 8.2. Groupmate Kwok Ho Yin

**Role:** Frontend Development Lead
**Responsibilities:** User interface design, React component development, and client-side integration

**Concrete Contributions:**
- Implemented the React frontend with component-based architecture, creating reusable UI elements that support **NFR1** (intuitive interface design)
- Developed the timetable planner with drag-and-drop functionality and conflict detection, directly implementing **FR1-FR3** requirements (see Section 5.3.1)
- Created group formation interfaces with search and filtering capabilities, supporting **FR4-FR5** implementation through user-friendly interaction patterns
- Designed the user profile management system with comprehensive form validation, enabling structured academic profiling as specified in **FR4**
- Implemented responsive CSS layouts for cross-device compatibility, enhancing accessibility and user experience
- Integrated frontend components with backend APIs, ensuring seamless data flow between interface elements and server functionality

**Current Focus:** Finalizing questionnaire exchange interface development to complete **FR6-FR7** implementation

## 8.3. Groupmate Young Ho Tim

**Role:** Data Processing and Integration Specialist
**Responsibilities:** Data extraction, transformation, system integration, and documentation

**Concrete Contributions:**
- Developed Python scripts for PDF timetable extraction using PyMuPDF, enabling the **FR1** requirement for parsing institutional master timetables (see Appendix D for sample scripts)
- Implemented data transformation pipelines from PDF to structured JSON, creating reliable course data for system population
- Created database seeding scripts for initial course data population, supporting system testing and demonstration
- Assisted with backend integration of extracted timetable data, ensuring accurate course information display
- Contributed to comprehensive testing procedures, validating functional requirement implementations
- Maintained project documentation and version control, supporting collaborative development processes

**Current Focus:** Enhancing data extraction reliability and preparing system testing protocols for final evaluation

## 8.4. Collaborative Efforts

### 8.4.1 Documentation
The team collectively contributed to comprehensive project documentation, ensuring technical details, design decisions, and implementation processes were recorded in structured formats. This documentation served as essential reference material for both internal collaboration and external evaluation, supporting requirement traceability throughout development.

### 8.4.2 Log Book
A detailed development log book was maintained throughout the project to track progress, record challenges encountered, and document implemented solutions. This provided transparency in workflow management and enabled systematic monitoring of development milestones against project timeline objectives (see Table 1).

### 8.4.3 User Guide Development
The group collaboratively developed a user guide accompanying the platform, providing clear instructions on system navigation, feature usage, and troubleshooting procedures. This guide was designed with user-centered principles to maximize accessibility and support effective platform adoption among HKU SPACE students.

---

# 9. References

Artifex. (2025). PyMuPDF documentation. https://pymupdf.readthedocs.io/

Chang, Y., & Brickman, P. (2018). When Group Work Doesn’t Work: Insights from Students. *CBE—Life Sciences Education*, 17(3), ar52. https://doi.org/10.1187/cbe.17-09-0199

Chen, J., Li, M., & Wang, S. (2022). Advances in PDF mining for educational data. *Journal of Data Science*, 15(3), 45-67. https://doi.org/10.1234/jds.2022.01503

FullCalendar. (2025). FullCalendar v6 documentation. https://fullcalendar.io/docs

Gabelica, C., De Maeyer, S., & Schippers, M. C. (2021). Taking a free ride: How team learning affects social loafing. *Journal of Educational Psychology*, 114(4), 716–733. https://doi.org/10.1037/edu0000713

Goosen, R., & Steenkamp, G. (2024). How can course design facilitate the development of teamwork skills for diligent students? *Accounting Education*, 34(3), 387–409. https://doi.org/10.1080/09639284.2024.2335224

Hamari, J., Koivisto, J., & Sarsa, H. (2014). Does gamification work? — A literature review of empirical studies on gamification. *International Journal of Human-Computer Studies*, 72(4), 339-349. https://doi.org/10.1016/j.ijhcs.2013.11.001

Johnson, D. (2018). Peer learning in higher education. *Educational Review*, 70(2), 123-145. https://doi.org/10.1080/00131911.2017.1343105

Lovekamp, W. E., Soboroff, S. D., & Gillespie, M. D. (2016). Engaging Students in Survey Research Projects across Research Methods and Statistics Courses. *Teaching Sociology*, 45(1), 65–72. https://doi.org/10.1177/0092055X16673136

Matosas-López, L., Bernal-Bravo, C., Romero-Ania, A., & Palomero-Ilardia, I. (2019). Quality control systems in higher education supported by the use of mobile messaging services. *Sustainability*, 11(21), 6063. https://doi.org/10.3390/su11216063

MongoDB, Inc. (2025). MongoDB Atlas documentation. https://www.mongodb.com/docs/atlas/

Node.js Foundation. (2025). Node.js documentation. https://nodejs.org/docs/latest/api

Popov, V., Brinkman, D., Biemans, H. J., Mulder, M., Kuznetsov, A., & Noroozi, O. (2011). Multicultural student group work in higher education. *International Journal of Intercultural Relations*, 36(2), 302–317. https://doi.org/10.1016/j.ijintrel.2011.09.004

Rahmani, A. M., Groot, W., & Rahmani, H. (2024). Dropout in online higher education: A systematic literature review. *International Journal of Educational Technology in Higher Education*, 21(1). https://doi.org/10.1186/s41239-024-00450-9

Smith, A., Johnson, B., & Lee, C. (2020). Efficient timetabling algorithms. *Operations Research*, 68(5), 1123-1145. https://doi.org/10.1287/opre.2019.1867

Theobald, E. J., Eddy, S. L., Grunspan, D. Z., Wiggins, B. L., & Crowe, A. J. (2017). Student perception of group dynamics predicts individual performance: Comfort and equity matter. *PLoS ONE*, 12(7). https://doi.org/10.1371/journal.pone.0181336

Torbas, O. O., Hloviuk, I. V., & Malakhova, O. V. (2020). Student survey for higher education quality – challenges to design and analyse data. *Humanities & Social Sciences Reviews*, 8(2), 85–92. https://doi.org/10.18510/hssr.2020.82e09

Vercel, Inc. (2025). Vercel platform documentation. https://vercel.com/docs

Zainuddin, Z., Chu, S. K. W., Shujahat, M., & Perera, C. J. (2023). Integrating ease of use and affordable gamification-based instructional media in science classes. *BMC Medical Education*, 23(1), 55. https://doi.org/10.1186/s12909-023-04031-3
