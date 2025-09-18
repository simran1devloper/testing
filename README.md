
```mermaid

  flowchart TB
    subgraph MCP[Code Context MCP 9000]
        O[Orchestrator / Unifier]
    end

    O --> T1[upsert_context_tool]
    O --> T2[query_context_tool]
    O --> T3[delete_paths_tool]
    O --> T4[get_file_context_tool]

    T1 --> V[Vectorstore FAISS/DB]
    T2 --> V
    T3 --> V
    T4 --> V

    V --> V1[Stores semantic chunks]
    V --> V2[Enables fast search]
