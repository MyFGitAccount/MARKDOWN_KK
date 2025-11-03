# Login process flow chart:

```mermaid
graph TD
  st[Login Start] --> op0[enter course code]-->op1[Enter User name]-->op2[Enter password]--> ed[Login success]
  op2 --> cond{First time user?}
  cond -->|Yes| op3[enter new username]-->op4[enter new password]-->op0
  cond -->|No| op5[forgetpassword]-->op3
