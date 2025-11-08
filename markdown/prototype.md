
| Collection         | Key Fields                                                               | Purpose |
|--------------------|--------------------------------------------------------------------------|---------|
| **users**          | `studentId`, `password`, `name`, `email`, `role`, `photo`, `tokens`      | User auth, token balance |
| **courses**        | `code`, `name`, `semester`, `schedule`, `enrolledStudents[]`             | Course metadata |
| **resources**      | `courseId`, `title`, `filePath` (GridFS), `ratings[{userId, stars}]`     | Learning materials |
| **questionnaires** | `creatorId`, `url`, `accessedBy[]`                                       | Survey sharing |
| **timetablePlans** | `userId`, `blocks[{code, weekday, time, room}]`                          | Personal schedule |
| **adminLogs**      | `adminId`, `action`, `target`, `timestamp`                               | Audit & moderation |