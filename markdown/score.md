```mermaid
flowchart TD
    A[User Action] --> B{Action Type?}
    B -->|Upload Material| C[Rate Quality 1–5]
    B -->|Create Game| D[+50 Points]
    B -->|Complete Assessment| E[+30 Points]
    C --> F[Weighted Score: (Rating × 10)]
    F --> G[Update User Profile Points]
    G --> H[Unlock: Avatars, Badges, Exclusive Content]
    H --> I[Update Leaderboard (React Table)]
