sequenceDiagram
    participant browser
    participant server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: sended the user input to the server
    activate server
    server-->>browser: causes the submit event
    deactivate server
    
    browser->>server:Called an Http post request from the URL:https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    server-->>browser: responded with HTTP status code 302
    deactivate server

    Note right of browser: The browser reloads the notes page and causes three more HTTP requests.
    

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes
    
    browser->>server:Created a new element
    activate server
    server-->>browser:Executed the excercise:New note diagram
    deactivate server

    Note right of browser:Excercise 0.4