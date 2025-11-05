```mermaid
flowchart LR
    A[Admin Login] --> B[Role: admin?]
    B -- Yes --> C[Load Admin Dashboard]
    C --> D[User Management]
    C --> E[Login Audit Logs]
    C --> F[Content Moderation]
    C --> G[Photo Verification Panel]
    C --> H[Charts: Recharts / Chart.js]
