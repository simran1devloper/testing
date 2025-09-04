
```mermaid
flowchart TB
    %% Input Layer
    A1[RF Spectrogram Input Top Branch]
    A2[RF Spectrogram Input Bottom Branch]

    %% Top Branch
    B1[RF Preprocessing]
    B2[Temporal-Aware CNN]
    B3[Attention Module]
    B4[Feature Embedding]

    %% Bottom Branch
    C1[RF Preprocessing]
    C2[Temporal-Aware CNN]
    C3[Attention Module]
    C4[Feature Embedding]

    %% Similarity Computation and Decision
    D[Similarity Computation Module]
    E[Verification Decision]

    %% Connections Top Branch
    A1 --> B1 --> B2 --> B3 --> B4 --> D

    %% Connections Bottom Branch
    A2 --> C1 --> C2 --> C3 --> C4 --> D

    %% Final Decision
    D --> E

    %% Optional: indicate shared weights
    B1 --- C1
    B2 --- C2
    B3 --- C3
    B4 --- C4

