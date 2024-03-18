sequenceDiagram
    participant Browser
    participant Server
    participant SPA

    Browser->>Server: HTTP request for https://studies.cs.helsinki.fi/exampleapp/spa
    activate Server

    Server-->>Browser: SPA files (HTML, CSS, JS) are served
    deactivate Server

    Browser->>SPA: Browser receives SPA files
    activate SPA

    SPA-->>Browser: SPA initializes and renders
    deactivate SPA

    Browser->>Server: AJAX requests for initial data/resources
    activate Server

    Server->>SPA: Initial data/resources are served
    deactivate Server
    activate SPA

    SPA-->>Browser: User creates a new note
    deactivate SPA
    Note right of SPA: Note creation action triggers an AJAX request

    Browser->>Server: AJAX request to create a new note
    activate Server

    Server-->>Browser: Confirmation of successful note creation
    deactivate Server

    Browser->>SPA: SPA updates interface to display new note
    activate SPA

    SPA-->>Browser: Executed the excercise:New note in Single page app diagram
    deactivate SPA
    Note right of Browser: Exercise 0.6