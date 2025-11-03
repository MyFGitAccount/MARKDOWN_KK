# Login process flow chart:

```mermaid
graph TD
  ed[Login success]
  st[Login Start] --> op0[enter course code]-->op1[Enter User name]-->op2[Enter password]
  op2 --> cond{First time user?}
  cond -->|Yes| op3[enter new username]-->op4[enter new password]-->op0-->ed
  cond -->|No| op5[forgetpassword]-->op3
