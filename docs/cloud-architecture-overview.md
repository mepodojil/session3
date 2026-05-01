# Cloud Architecture Overview

This project is a simple monorepo-based TODO application with a React frontend and an Express backend that stores data in memory.

## System Context

```mermaid
flowchart LR
    User[User]
    Browser[Web Browser]
    Frontend[React Frontend\npackages/frontend]
    API[Express API\npackages/backend]
    Store[(In-Memory Store\npackages/backend)]

    User --> Browser
    Browser --> Frontend
    Frontend -->|HTTP requests| API
    API --> Store
```

## User Flow: Create a New Activity

```mermaid
sequenceDiagram
    actor User
    participant Frontend as React Frontend
    participant API as Express API
    participant Store as In-Memory Store

    User->>Frontend: Enter activity details
    User->>Frontend: Submit form
    Frontend->>API: POST /tasks
    API->>Store: Save new activity
    Store-->>API: Created activity
    API-->>Frontend: 201 Created + activity data
    Frontend-->>User: Show updated activity list
```

## Notes

- The **React frontend** renders the task UI and sends requests to the backend.
- The **Express API** handles application logic and exposes task endpoints.
- The **in-memory store** keeps task data only while the backend process is running.
- No persistent database is shown because the backend currently stores data in memory.