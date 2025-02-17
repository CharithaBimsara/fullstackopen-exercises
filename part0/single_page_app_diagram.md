```mermaid
sequenceDiagram
    participant Browser
    participant Server

    Browser->>Server: GET /spa
    activate Server
    Server-->>Browser: HTML document
    deactivate Server

    Browser->>Server: GET /main.css
    activate Server
    Server-->>Browser: CSS file
    deactivate Server

    Browser->>Server: GET /spa.js
    activate Server
    Server-->>Browser: JavaScript file
    deactivate Server

    Note right of Browser: JavaScript starts executing and fetching notes data

    Browser->>Server: GET /data.json
    activate Server
    Server-->>Browser: JSON data with existing notes
    deactivate Server

    Note right of Browser: The browser dynamically renders the notes without reloading the page.
