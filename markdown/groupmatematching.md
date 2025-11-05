```mermaid
flowchart TD
    A[User Joins Group Finder] --> B{Must Upload Sample Work}
    B -- No --> C[Start 48h Timer]
    C -- Expired --> D[Redirect to Temp Discourse Forum]
    D --> E[Resolve Issue → Approve Group]
    E --> F[Delete Temp Thread]
    B -- Yes --> G[Match with Peers]
    G --> H[Group Chat via Discourse PM]
    H --> I["Embed: Post-it (Canvas), FullCalendar"]
    I --> J[Auto Reminder Email 7 Days Before Deadline]
