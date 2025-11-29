---

##  Risk Acknowledgement and Mitigation Strategies

| Risk    | Probability | Impact | Description | Mitigation/Contingency |
|---------|-------------|--------|-------------|------------------------|
| Groupmate lags behind/<br> becomes unresponsive|Medium|High|One member misses deadlines, has personal issues, or drops the course|<ur><li>Group meeting 4+ times per week</li><li>Mandatory commit evidence</li><li>Reallocate tasks early if someone misses 2 consecutive stand-ups</li><li>Keep a “bus factor” buffer: no single person is the only one who understands a module</li></ul>|
|Backend development delays block frontend progress|High|High|Database system not ready|<ul><li>Use .json file as a temporary backend|
|Scope creep / new feature requests from stakeholder|Low|High|User want to add new function|<ul><li>Prioritization the request(Must-have / Could-have / No need)</li><li>Any new feature requires written approval and moves to backlog</li></ul>|
|Suspension of work|High|High|During exam period, members will study for the exam|<ul><li>Do all the task as fast as possible, never being a deadline fighter</li><li>Contribute extra time for development</li></ul>|
|Third-party service downtime or quota limits (e.g., Firebase, AWS free tier)|Low|Medium-High|Deployment fails during demo|<ul><li>Use another third-party service|
|Merge conflicts and Git chaos near deadlines|High|High|Last-minute integration|<ul><li>Never being a deadline fighter</li><li>Rebase and run tests before merging</li></ul>|
|Gmail SMTP service cann't function properly|Medium|High|Sometimes the service maybe temporary unreachable because of high volume of request|<ul><li>Add a settime out function to make sure the gmail SMTP function only send email in a reasonable time|
