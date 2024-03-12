sequenceDiagram
    participant Browser
    participant Server
    participant SPA

    Browser->>SPA: User requests the SPA URL
    SPA->>Browser: SPA files (HTML, CSS, JS) are served by the server
    Browser->>Server: HTTP request for SPA files
    Server->>Browser: SPA files (HTML, CSS, JS) are served
    Browser->>SPA: Browser renders the SPA
    SPA->>Server: AJAX requests for data/resources (optional)
    Server->>SPA: Data/resources are served (optional)
