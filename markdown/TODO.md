# Login process flow chart:

graph TD
    A[Start] --> B{Is it raining?};
    B -- Yes --> C[Take an umbrella];
    B -- No --> D[Go outside];
    C --> E[End];
    D --> E;
