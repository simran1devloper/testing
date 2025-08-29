sequenceDiagram
    participant U as User
    participant VSE as VS Code Extension
    participant VSB as VS Code Backend
    participant MCP as MCP Code Microservice
    participant AG as Coding Agent
    participant GR as GitHub RAG
    participant GD as GitHub-Docker Agent
    participant CR as Context RAG
    participant GW as MCP Gateway

    U->>VSE: Open project & install extension
    U->>VSE: Ask query (e.g., integrate Beckn order API)
    VSE->>VSB: Send prompt + context
    VSB->>MCP: Forward request
    MCP->>AG: Assign task
    AG->>GR: Fetch repo/docs (if needed)
    AG->>CR: Fetch context (if needed)
    AG->>GD: Deploy service (if needed)
    AG->>MCP: Return code/plan
    MCP->>GW: Forward result
    GW->>VSB: Send response
    VSB->>VSE: Apply in VS Code
    VSE->>U: Working code returned
