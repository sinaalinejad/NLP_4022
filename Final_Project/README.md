## Medical Advisor using Retrieval Augmented Generation (RAG) Pipeline 
In this notebook I have medalpaca/medical_meadow_wikidoc dataset which contains input question and its answer. Both are in medical context. This project doesn't use
any specific library for using RAG pipeline, like LangChain and LlamaIndex.  
This notebook is divided into below parts:
- Retriever: For this porpuse, I used all-MiniLM-L6-v2 to get the embeddings and then using cosine similarity to find relevant documents to the query.
  Here there were multiple approaches: first to find the most similar question to the query. second to find the most similar answer to the query. third to use a
  combination of them. I used second approach as it made more sense to me. Because in real world we don't have the queries and we should find relevant documents
  from those in Internet.
- Generator: For this part, I conducted multiple experiments using different models like Phi-3-medium-4k-instruct, gorilla_llm, and deepseek_ai. I gave it the
  most relevant answer as context, the query, and the prompt saying that it should use the context to answer the query.
- Evaluation: For this porpuse, I used another LLM for Text Generation. I gave it the query, answers of the 3 models, and the prompt saying which model's answer
  is the best
