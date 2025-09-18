
```mermaid

  flowchart TB
    subgraph A[Code Context MCP 9000]
        direction TB
        A --> T1[upsert_context_tool]
        A --> T2[query_context_tool]
        A --> T3[delete_paths_tool]
        A --> T4[get_file_context_tool]
    end

    T1 --> V[Vectorstore FAISS/DB]
    T2 --> V
    T3 --> V
    T4 --> V

    V --- V1[Stores semantic chunks]
    V --- V2[Enables fast search]
