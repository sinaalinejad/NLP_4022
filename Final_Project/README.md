## Medical Advisor using Retrieval Augmented Generation (RAG) Pipeline (RAG_without_library)
In this notebook, I have used medalpaca/medical_meadow_wikidoc dataset which contains the input question and its answer. Both are in a medical context. This project doesn't use
any specific library for using the RAG pipeline, like LangChain and LlamaIndex.  
This notebook is divided into the following parts:
- Retriever: For this purpose, I used all-MiniLM-L6-v2 to get the embeddings and then used cosine similarity to find relevant documents to the query.
  Here there were multiple approaches: first to find the most similar question to the query. second to find the most similar answer to the query. third to use a
  combination of them. I used the second approach as it made more sense to me. Because in the real world, we don't have the queries and we should find relevant documents
  from those in Internet.
- Generator: For this part, I conducted multiple experiments using different models like Phi-3-medium-4k-instruct, gorilla_llm, and deepseek_ai. I gave it the
  most relevant answer as context, the query, and the prompt saying that it should use the context to answer the query. Since all of these models are heavy with many
  parameters, I used Quantization as a technique to load heavy models. For this purpose, I used BitsAndBytes library.
- Evaluation: For this purpose, I used another LLM for Text Generation. I gave it the query, answers of the 3 models, and the prompt saying which model's answer
  is the best


## Implementation of RAG architecture on Organizational Reports (RAG_with_library)
This is the same as the above project, except that it targets another task, plus it uses specialized libraries for RAG like LangChain and LlamaIndex.
The task is to give advice about legal issues.
