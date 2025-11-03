# Login process flow chart:

```mermaid
graph TD
  st[Login] --> op[Enter credentials]
  op --> cond{Valid?}
  cond -->|Yes| e[Success]
  cond -->|No| op
