```mermaid
sequenceDiagram
    participant Browser
    participant Server

    Browser->>Server: POST https://studies.cs.helsinki.fi/exampleapp/new_note (note data)
    activate Server
    Server-->>Browser: HTTP 302 Redirect to /notes
    deactivate Server

    Browser->>Server: GET /notes
    activate Server
    Server-->>Browser: HTML document (updated)
    deactivate Server

    Browser->>Server: GET /main.css
    activate Server
    Server-->>Browser: CSS file
    deactivate Server

    Browser->>Server: GET /main.js
    activate Server
    Server-->>Browser: JavaScript file
    deactivate Server

    Note right of Browser: The browser starts executing JavaScript

    Browser->>Server: GET /data.json
    activate Server
    Server-->>Browser: Updated JSON data with new note
    deactivate Server

    Note right of Browser: The browser renders the updated list of notes.
