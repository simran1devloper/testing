
```mermaid

  flowchart TB
    subgraph A[Code Context MCP 9000]
        A1[upsert_context_tool]
        A2[query_context_tool]
        A3[delete_paths_tool]
        A4[get_file_context_tool]
    end

    A --> B[Vectorstore FAISS/DB]
    B --- B1[Stores semantic chunks]
    B --- B2[Enables fast search]
     
