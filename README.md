
```mermaid
flowchart TD
    %% Root
    A[VS Code]

    %% Gateway
    A --> B[Gateway]

    %% Main inputs from Gateway
    B --> C[Checker]
    B --> D[Coder]
    B --> E[Human Feedback]

    %% Checker path
    C -->|Logs Good| F[Success]
    C -->|Logs Bad| D

    %% Coder path
    D --> G[Translator]
    G --> B

    %% Human Feedback path
    E --> D

    %% Loops
    F -.-> B
    D -.-> B
    G -.-> B
