# Question Answering with Retrieval-Augmented Generation
This project implements a Retrieval-Augmented Generation (RAG) pipeline for answering user queries by combining information retrieval with text generation. It combines semantic retrieval and Hugging Face's Question Answering models for context-aware solution.

## RAG Pipeline Overview

- **Text Embedding**: Use a SentenceTransformer model to convert text into vector embeddings.
- **Indexing**: Store embeddings in `FAISS` for efficient semantic similarity searches.
- **Retrieval**: Retrieve top-k text chunks most relevant to a user query.
- **Answer Generation**: Use a pre-trained Hugging Face Question Answering model (`tinyroberta-squad2`) to generate answers from retrieved contexts.

## Workflow

1. Preprocess PDFs and generate embeddings for text chunks.
2. Index embeddings in FAISS for semantic retrieval.
3. Input user query:
   - Retrieve relevant text chunks.
   - Pass chunks to the QA model for answer generation.
4. Output context-specific answers.