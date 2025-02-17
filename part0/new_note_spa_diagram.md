```mermaid
sequenceDiagram
    participant Browser
    participant Server

    Browser->>Server: POST /new_note_spa (note data)
    activate Server
    Server-->>Browser: HTTP 201 Created (confirmation)
    deactivate Server

    Note right of Browser: JavaScript updates the UI dynamically without reloading

    Browser->>Server: GET /data.json (Fetch latest notes)
    activate Server
    Server-->>Browser: Updated JSON data with new note
    deactivate Server

    Note right of Browser: The new note appears instantly without a full-page refresh.
