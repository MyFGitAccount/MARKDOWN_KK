# Login process flow chart:

```mermaid
graph TD
  st[Login Start] --> op0[Enter course code]
  op0-->op1[Enter User name]
  op1-->op2[Enter password]
  op2 --> cond{First time user?}
  cond -->|Yes| op3[enter new username]-->op4[enter new password]
  op4-->op5[upload student card photo]
  op5-->studentCheck{Is HKUSPACE student?}
  studentCheck-->|Yes| op9[Accept access]
  op9-->op0
  studentCheck -->|No| op7[Deny access]
  op7-->op8[Login failed]
  cond-->|No| op6{Is HKUSPACE student?}
  op6-->op3
  op2-->ed[Login success]
