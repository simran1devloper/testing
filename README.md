
```mermaid
flowchart TD
    A[VS Code] --> B[Gateway]

    B -->|Logs| C[Checker]
    B -->|User Query (UQ)| D[Coder]
    B -->|Human Feedback Response| E[Coder]

    C -->|Logs Good| F[Success]
    F --> B
    C -->|Logs Bad| D
    D --> G[Translator]
    G --> B


    %% Case A: Logs
    C -->|Logs Good| F[Success]
    F --> B
    C -->|Logs Bad| D
    D --> G[Translator]
    G --> B

    %% Case B: User Query (UQ)
    D --> G
    G --> B
    B --> A
    A --> H[Logs]
    H --> C
    C -->|Loop until success| F

    %% Case C: Human Feedback Response
    E --> D
    D --> G
    G --> B
    B --> A
    A --> H
    H --> C
    C -->|Loop until success| F
