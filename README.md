
```mermaid
flowchart TD
    %% Root
    A[VS Code]

    %% Gateway
    A --> B[Gateway]

    %% Inputs from VS Code to Gateway
    B -->|Logs| C[Checker]
    B -->|User Query (UQ)| D[Coder]
    B -->|Human Feedback Response| E[Coder]

    %% Case A: Logs
    C -->|Logs Good| F[Success]
    F --> B
    C -->|Logs Bad| D

    %% Translation Step
    D --> G[Translator]
    G --> B

    %% Case B: User Query (UQ) loop
    D --> G
    G --> B
    B --> A
    A --> H[Logs]
    H --> C
    C -->|Loop until success| F

    %% Case C: Human Feedback Response loop
    E --> D
    D --> G
    G --> B
    B --> A
    A --> H
    H --> C
    C -->|Loop until success| F
