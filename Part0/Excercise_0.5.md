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
    
    SPA-->>Browser:Executed the excercise:Single page app diagram
    deactivate SPA

    Note right of Browser:Excercise 0.5