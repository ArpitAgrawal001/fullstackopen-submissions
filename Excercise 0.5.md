sequenceDiagram
    participant browser
    participant server

    browser->>server:Executes the JavaScript code fetched from the server
    activate server
    server-->>browser:fetches the notes as JSON data and adds HTML elements for displaying the notes
    deactivate server

    Note left of server:uses DOM-API

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: the contents of are manipulated with JavaScript that executes in the browser.
    deactivate server

    Note right of browser:comprise only one HTML page

    browser->>server:data is sent via form's submit
    activate server
    server-->>browser:instructs to reload the Notes page with a redirect
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser:here,the JavaScript file is spa.js
    deactivate server
    
    browser->>server: On creation of new note,only one request is being sent
    activate server
    server-->>browser:responds with status code 201 created
    deactivate server

    Note left of server:does not ask for a redirect
    Note right of browser:stays on same page,and it sends no further HTTP requests

    browser->>server:note list on the page is rerenderedd and the new note is being sent
    activate server 
    server-->>browser:the data type is determined with a Content-type header and then it is sent as JSON string
    deactivate server

    browser->>server:the user goes to the 'spa' version of the notes app
    activate server
    server-->>browser:Executed the excercise:Single page app diagram
    deactivate server

    Note right of browser:Excercise 0.5