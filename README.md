
```mermaid

  flowchart TB
    O[Orchestrator / Unifier]

    T1[upsert_context_tool]
    T2[query_context_tool]
    T3[delete_paths_tool]
    T4[get_file_context_tool]

    V[Vectorstore FAISS/DB]
    V1[Stores semantic chunks]
    V2[Enables fast search]

    %% Orchestrator calls tools
    O --> T1
    O --> T2
    O --> T3
    O --> T4

    %% Tools call Vectorstore
    T1 --> V
    T2 --> V
    T3 --> V
    T4 --> V

    %% Vectorstore features
    V --> V1
    V --> V2
