# Login process flow chart:

```mermaid
graph TD
  st[Login Start] --> op0[enter course code]-->op1[Enter User name]-->op2[Enter password]--> ed[Login success]
  op2 --> cond{First time user?}
  cond -->|Yes| op3[enter new username]-->op4[enter new password]-->op5[upload student card photo]
  cond -->|No| op6[forgetpassword]-->op3
  op5-->cond{Is HKUSPACE student?}
  cond-->|No| op7-->[deny access]-->op8[login failed]
  cond-->|Yes| op9-->[accept access]-->op0
