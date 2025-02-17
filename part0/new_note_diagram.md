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
    Server-->>Browser: Updated HTML page
    deactivate Server

    Browser->>Server: GET /data.json
    activate Server
    Server-->>Browser: Updated notes in JSON format
    deactivate Server

    Note right of Browser: The page reloads and fetches the updated list of notes.
