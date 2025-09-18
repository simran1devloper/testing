
```mermaid
flowchart TB
    subgraph A[LangChain Agent]
        A1[(Registered tools & wrappers)]
    end

    subgraph B[Context Agent MCP]
        B1[orchestrate]
        B2[embeddings]
        B3[loaders]
    end

    A <--> B

    subgraph C[Subcomponents]
        direction LR
        subgraph C1[GitHub Repo Manager MCP]
            C1a[clone]
            C1b[pull_all]
        end

        subgraph C2[Loader MCP]
            C2a[load docs]
            C2b[list repos]
        end

        subgraph C3[Embedding MCP]
            C3a[build idx]
            C3b[semantic search]
        end

        subgraph C4[GitHub Context System MCP]
            C4a[query RAG]
            C4b[upsert ctx]
        end
    end

    B --> C1
    B --> C2
    B --> C3
    B --> C4
