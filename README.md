# RAG Practice

A small Retrieval-Augmented Generation (RAG) project built with Python and Ollama, following a tutorial to understand the fundamentals of document embeddings, semantic search, and LLM-powered question answering.

## Overview

This project implements a basic RAG pipeline that allows users to ask questions about a collection of Markdown documents.

Instead of relying entirely on the LLM's existing knowledge, the system retrieves relevant document chunks and provides them as context when generating an answer.

## How It Works

1. **Document Loading:** Reads Markdown (`.md`) files from the `docs/` directory.
2. **Chunking:** Splits documents into smaller chunks using paragraph breaks.
3. **Embedding Generation:** Converts each chunk into a numerical vector using `nomic-embed-text`.
4. **Semantic Search:** Uses cosine similarity and NumPy to retrieve the three most relevant chunks for a question.
5. **Answer Generation:** Passes the retrieved context to Qwen, which generates an answer using the provided information.

## Tech Stack

- Python
- Ollama
- NumPy
- Requests
- `nomic-embed-text` (embedding model)
- `qwen3:4b-instruct` (LLM)

## Project Structure

```text
rag-practice/
├── docs/
│   └── example.md
├── rag.py
├── README.md
└── .gitignore
```

## Getting Started

### Prerequisites

- Python
- [Ollama](https://ollama.com/)
- [uv](https://docs.astral.sh/uv/)

### 1. Clone the repository

```bash
git clone YOUR_REPOSITORY_URL
cd rag-practice
```

### 2. Install dependencies

```bash
uv sync
```

### 3. Pull the Ollama models

```bash
ollama pull nomic-embed-text
ollama pull qwen3:4b-instruct
```

### 4. Add documents

Place your Markdown files inside the `docs/` directory.

### 5. Run the project

Make sure Ollama is running, then execute:

```bash
uv run rag.py
```

You can now ask questions about your documents through the terminal.

## Current Limitations

- Supports Markdown documents only.
- Uses basic paragraph-based chunking.
- Retrieves the top 3 chunks using cosine similarity.
- Embeddings are generated again whenever the program starts.
- No persistent vector database.
- Answers are limited to the retrieved context.

## Learning Objectives

Built as a learning exercise to understand the fundamentals of Retrieval-Augmented Generation, vector embeddings, semantic retrieval, and local LLM integration.
