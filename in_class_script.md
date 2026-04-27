Here is a **5-7 minute presentation script** written **specifically based on your PowerPoint slides**. The script follows your slide order and uses your exact data, quotes, and technical details.

---

# Presentation Script: EFS Platform – Final Project Outcomes & Testing

**Duration:** ~5-7 minutes  
**Presenters:** Xavier Wong, Kwok Ho Yin, Young Ho Tim  
**Supervisor:** Mr. Lau Chung Yin | April 2026

---

## SLIDE 1: Title Slide

**Speech:**

"Good morning everyone. I'm Xavier Wong, joined by my group members Kwok Ho Yin and Young Ho Tim. We're presenting the final outcomes and testing results for our Educational Facilitation System – the EFS Platform – developed for CCIT4080 Knowledge Product Development.

Our supervisor is Mr. Lau Chung Yin. The platform is fully deployed and live at **hku.wiki**."

---

## SLIDE 2: Outcomes at a Glance

**Speech:**

"Let me start with a quick snapshot of what we've achieved.

First, we have a fully deployed platform with four complete modules running live.

Our user survey with 51 respondents showed **96% rated the platform as good or excellent** overall.

Performance testing with k6 under 200 concurrent users resulted in a **0% failure rate** across 5,000 requests, with an **average response time of just 15 milliseconds** and p95 at 29 milliseconds.

All four core modules are production-ready and functioning as designed."

---

## SLIDE 3: Four Core Modules – Prototype Status

**Speech:**

"Let me walk you through each module briefly.

**First, the Timetable Planner** – this allows scheduling. Users can export their timetable as a PNG using html2canvas, which we've calibrated for accurate output.

**Second, Group Formation** – this enables profile-based matching. When users send invitations, email notifications are triggered. Once a match is accepted, real-time chat with polling is activated.

**Third, the Questionnaire Exchange** – this uses a credit system. New users start with 5 credits. Filling a survey earns you 1 credit; posting a survey costs 1 credit. You can have unlimited active surveys simultaneously, and daily login gives an additional 2-credit bonus.

**Fourth, the Materials Repository** – this allows administrators to upload course files using GridFS storage with download tracking for analytics.

Beyond these four modules, we've also built an admin dashboard, implemented JWT authentication, and added responsive breakpoints at 768 and 1024 pixels for mobile and tablet devices."

---

## SLIDE 4: Performance Testing – k6 & Lighthouse

**Speech:**

"Now let's look at our performance testing results.

We conducted a **k6 load test with 200 concurrent virtual users** sustained over 30 seconds, generating 5,000 total requests. The results were excellent: **zero percent failure rate**, average HTTP duration of 15 milliseconds, and p95 latency at 29 milliseconds. Throughput was 162 iterations per second with 139 kilobytes per second data transfer.

We also ran **Lighthouse testing on mobile emulation** with slow 4G throttling to simulate real-world conditions.

Our performance score came in at 75. But more importantly, we achieved a **perfect 100 on Best Practices**, **96 on Accessibility** – which is excellent – and 90 on SEO.

Our Largest Contentful Paint is 3.6 seconds, Cumulative Layout Shift is zero – meaning no unexpected page movement – and Total Blocking Time is 270 milliseconds.

Several optimizations were applied to achieve these results: code splitting reduced initial bundle size, we removed 366 kilobytes of unused JavaScript, and render-blocking CSS was resolved."

---

## SLIDE 5: User Evaluation – N=51

**Speech:**

"Beyond automated testing, we conducted structured user surveys with 51 participants to validate our solution against real academic pain points.

The results were very encouraging. **92% of users found the platform useful** for addressing their academic needs. **86% said they are likely to adopt EFS** as part of their regular study routine. This indicates strong product-market fit.

**94% rated mobile design as important or very important** – which validates our investment in responsive design.

The **Timetable Planner received a 4.53 out of 5** rating for time-saving effectiveness. When asked about the Materials Repository, **85.7% demanded past exam papers** specifically, which gives us clear direction for future content expansion.

Qualitative feedback included comments like 'faster, efficient', 'specialised for HKU SPACE', and 'convenient, powerful'. The most valued feature was the Timetable Planner at 26.5% of responses.

Users recommended a starting credit balance of **3.8 on average** – our current system uses 5 credits, so we may adjust this in the next iteration."

---

## SLIDE 6: Problem Validation

**Speech:**

"Our pre-deployment survey confirmed three major student pain points that EFS directly addresses.

**First**, 85% of students found manual PDF-based timetable checking time-consuming. Our Timetable Planner addressed this, and post-deployment, **91.6% agreed it saves them time**.

**Second**, 66% reported difficulty forming project groups. After using EFS, **83.3% found it easier to find group members** through our platform.

**Third**, 60% struggled to collect 30 questionnaire responses for EAP II course requirements. With our Questionnaire Exchange module, **83.3% said it helps them reach that target**.

Additionally, **79.1% agreed the credit system is fair** and encourages participation – validating our reciprocal economy design."

---

## SLIDE 7: Key Challenges & Solutions

**Speech:**

"Throughout development, we encountered several technical constraints and solved each one.

**First**, Vercel's serverless architecture required migrating our Express routes to individually exported handler functions. We accomplished this by refactoring our routing structure.

**Second**, the Multer library failed in serverless context. We resolved this by implementing **GridFS streaming with a base64 encoding fallback**.

**Third**, MongoDB's hard connection limit of 20 connections was mitigated using a **singleton connection pool capped at 15 connections** – well within the limit.

**Fourth**, real-time chat without WebSockets was implemented using **polling – 3 seconds for messages, 5 seconds for group updates** – as a lightweight alternative that works within serverless constraints.

**Finally**, PNG timetable export required html2canvas with manual calibration to produce accurate, shareable schedule exports. This is now functioning reliably."

---

## SLIDE 8: Future Scope

**Speech:**

"Based on user feedback, we've identified clear priorities for future development.

**First**, deadline reminders integrated into the dashboard and calendar for assignment and exam alerts.

**Second**, an AI assistant with smart FAQ and course recommendation powered by large language models.

**Third**, native mobile apps for iOS and Android with push notifications for real-time updates.

**Fourth**, upgrading from polling to WebSockets to significantly reduce chat latency.

**Fifth**, achieving WCAG 2.1 Level AA accessibility compliance – we're currently at 96 Lighthouse accessibility score, so we're close – plus HKU SPACE API integration.

**And finally**, expanding the Materials Repository with past exam papers, which 85.7% of users identified as top demand."

---

## SLIDE 9: Credit System Deep Dive

**Speech:**

"I want to briefly highlight the credit system design, as it's central to the Questionnaire Exchange module.

New users receive **5 credits upon admin approval**. You earn **1 credit for filling someone else's survey**, plus a **2-credit daily login bonus**. Posting your own questionnaire costs **1 credit**.

So if you fill two surveys and log in daily, you earn 4 credits, which allows you to post up to four surveys. This creates a reciprocal economy where everyone is incentivized to participate.

Our survey rated fairness at **4.38 out of 5**. Users recommended a starting balance of 3.8 credits on average. Since we currently use 5, we may adjust this in the next iteration based on this feedback."

---

## SLIDE 10: Summary & Conclusion

**Speech:**

"To summarize: EFS Platform is **production-ready** and live at **hku.wiki**. All four modules are fully implemented, tested, and validated with real users.

**User satisfaction is high** – 96% good or excellent rating, 92% found it useful, 86% likely to adopt.

**Performance is validated** – 15ms average response, zero percent failure rate under 200 concurrent users, and a Lighthouse accessibility score of 96.

**Our unique capabilities** include a credit-based exchange system, PNG timetable export, and real-time chat working entirely on serverless infrastructure.

Thank you for your attention. The live demo is at hku.wiki, and the code is on GitHub. We welcome any feedback or questions."

---

## Q&A Preparation Notes

| Likely Question | Suggested Answer |
|----------------|------------------|
| Why 3-second polling instead of WebSockets? | Serverless functions have execution limits; WebSockets require persistent connections. Polling is lightweight and works within Vercel's architecture. |
| How did you handle the MongoDB connection limit? | Singleton connection pool capped at 15 connections, reused across all serverless function invocations. |
| What's your plan for the 3.8 credit recommendation? | Review usage analytics over next semester and adjust starting balance if average user credits drop too quickly. |
| Why is LCP at 3.6s? | Largest element is the login card text. Further optimization could preload critical CSS. Currently acceptable for an educational tool. |
| How many users have tested the platform? | 51 survey respondents plus additional ad-hoc testing during development. |

---

**Total estimated presentation time: 6-7 minutes**
