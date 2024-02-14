osan 0 tehtävien vastaukset
Tehtävä 4:

sequenceDiagram
    participant browser
    participant server
    
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    server-->>browser: Response with success status
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document with updated notes
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "This is message", "date": "2024-2-14" }, ..., { "content": "New note content", "date": "2024-2-14 }]
    deactivate server

Tehtävä 5: 

sequenceDiagram
    participant browser
    participant server
    
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: HTML document (SPA framework and structure)
    deactivate server

     browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.css
    activate server
    server-->>browser: the CSS file for SPA
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server
    server-->>browser: the JavaScript file for SPA
    deactivate server
    
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "message", "date": "2024-2-14" }, ... ]
    deactivate server


Tehtävä 6

sequenceDiagram
    participant Browser as Browser
    participant Server as Server

    Note over Browser: User enters note and clicks 'Save'

    Browser->>Server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate Server
    Note over Server: Server processes the note
    Server-->>Browser: Response (success and note details)
    deactivate Server
