flowchart LR
    A[User Selects Course] --> B[Fetch Course Collection from MongoDB]
    B --> C[Render Resources: PDFs, Videos, Slides]
    C --> D[GridFS Stream Large Files]
    D --> E[React Grid with Filter/Sort]
    E --> F[Interactive Tools: Flashcards, Matching, Quizzes]
    F --> G[CRUD via Socket.IO Real-time Sync]
