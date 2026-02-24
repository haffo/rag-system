# Context 
Build AI knowledge-worker using RAG to become an expert on all company-related matters. The knowledge is a set of markdown documents chunked, indexed for retrieval as part of the RAG pipeline. The project consist of buikding a basic RAG system and an advanced RAG system with more pipeline components. 


# Basic RAG System 
Key Concepts Coverered

- LangChain Text Splitters to create document chunks, experimenting with different chunking strategies including TextRecursive, Markdown and Semantic Chunking and Hierarchical Chunking
- HuggingFaceEmbeddings and OpenAIEmbeddings as embedding modelsǐ
- Chroma for vector store for quick retrieval. Preferred to use an open-source vs paid versions such as pinecone or Weaviate. 
- Build a RAG Pipeline using LangChain for Retriever abstraction on Chroma vector store.  
- Evaluation of the RAG system components with UI for performance visualization
  - Measuring Retrieval  
    - MRR (Mean Reciprocal Rank)
    - nDCG (Normalized Discounted Cumulative Gain)
    - Keyword match 
    - Recall@K
    - Precision@K
  - Measuring Generation with LLM-as-judge to score the answer against criteria like accuracym completeness and releveance. 

Pipeline Components 

- Create Chunks 
- Create embeddings 
- Add Query rewriting 
- Add Query Expansion 
- Retrieve Context
- Generate Answer 


## Run App
`uv run basic_rag/app.py` 

## Run evaluation 
`uv run evaluator.py` 

## Update vector store 
`uv run basic_rag/ingest.py`

## Change chunking strategy 
- Run `uv run implementation/ingest.py` 


# Advanced RAG System 

Key Concepts Coverered

- LangChain Text Splitters to create document chunks, experimenting with different chunking strategies including TextRecursive, Markdown and Semantic Chunking and Hierarchical Chunking
- HuggingFaceEmbeddings and OpenAIEmbeddings as embedding modelsǐ
- Chroma for vector store for quick retrieval. Preferred to use an open-source vs paid versions such as pinecone or Weaviate. 
- Build a RAG Pipeline using LangChain for Retriever abstraction on Chroma vector store.  
- Evaluation of the RAG system components with UI for performance visualization
  - Measuring Retrieval  
    - MRR (Mean Reciprocal Rank)
    - nDCG (Normalized Discounted Cumulative Gain)
    - Keyword match 
    - Recall@K
    - Precision@K
  - Measuring Generation with LLM-as-judge to score the answer against criteria like accuracym completeness and releveance. 
- Query Rewriting & Expansion before Retrieval
- Re-ranking by using LLM to sub-select from RAG results.
- Graph RAG to retrieve content closely related to similar documents.
- Agentic RAG using Agents for retrieval, combining with memory and tools such as SQL. 


Pipeline Components 

- Multi-thread chunks creation with retry with exponential backoff
- Multi-thread embeddings creation  with retry with exponential backoff
- Add Query rewriting with retry with exponential backoff
- Add Query Expansion 
- Retrieve Context 
- Re-rank retrieved chunks with retry with exponential backoff
- Generate Answer 


## Update vector store 
`uv run advanced_rag/ingest.py`

## Change chunking strategy 
`uv run advanced_rag/ingest.py` 

## Run evaluation 
`uv run evaluator.py` 

## Run App
`uv run basic_rag/app.py` 