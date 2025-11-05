flowchart TD
    A[Add-Drop Period Active?] -->|No| B[Feature Disabled]
    A -->|Yes| C[Load Course Catalog]
    C --> D[Drag & Drop Blocks with React DnD]
    D --> E[Conflict Detection Engine]
    E -- Conflict --> F[Highlight in Red]
    E -- OK --> G[Save Layout to User Profile]
