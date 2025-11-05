flowchart TD
    A[User Clicks Write Article] --> B[Open TipTap Editor]
    B --> C[Save Markdown + Metadata to MongoDB]
    C --> D[Render with React Markdown]
    D --> E[Star Rating → Add Points]
    E --> F[Sync User to Discourse via SSO]
    F --> G[Create Course Category in Discourse]
    G --> H[Threaded Discussions + Replies]x
