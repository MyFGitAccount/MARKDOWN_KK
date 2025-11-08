```mermaid
flowchart TD
    A[User Joins Group Finder] --> B{Must Upload Sample Work}
    B -- No --> C[Start 48h Timer]
    C -- Expired --> D[Matching fail]
    D --> E[Delete Temp Thread]
    D -- Try again --> B
    B -- Yes --> G[Match with Peers]
    G --> H[Matching complete]
    H --> I[Start 1 week Timer for exchanging contact]
    I --> J[Delete Temp Thread]
```