## 1. Authentication & Access Control

```mermaid
flowchart TD
    A[User Opens Login Page] --> B{Valid JWT in Cookies?}
    B -- Yes --> C[Load Protected Dashboard]
    B -- No --> D[Show Login Form]
    D --> E[Submit Email + Password]
    E --> F[Backend: Verify Credentials]
    F -- Success --> G[Generate JWT + Set HttpOnly Cookie]
    F -- Fail --> H[Show Inline Error]
    G --> I[Redirect to Dashboard]
    I --> J[Role Check: Student / Admin]
