# AI Document Q&A Assistant (RAG + FastAPI + FAISS + OpenAI + Streamlit)

An end-to-end **Retrieval-Augmented Generation (RAG)** project that lets users upload PDF documents and ask questions about them.  
The system retrieves relevant chunks using **FAISS** and generates grounded answers using **OpenAI LLMs**, exposed through a **FastAPI** backend and a **Streamlit** frontend.

## ✨ Features

- 📄 Upload PDF documents
- 🔁 RAG pipeline:
  - PDF text extraction
  - Text chunking with overlap
  - Embedding generation using OpenAI
  - Vector indexing and retrieval using FAISS
- 🧠 LLM answer generation with context & basic hallucination control
- 🌐 FastAPI backend with clean endpoints:
  - `POST /upload` – ingest and index documents
  - `POST /ask` – ask questions and get answers with sources
  - `GET /health` – health check
- 💬 Streamlit chat-style UI for interactive Q&A
- 📚 Source chunk display with document names and similarity scores

## 🏗️ Tech Stack

- **Backend**: FastAPI, Python
- **Vector Store**: FAISS
- **LLM & Embeddings**: OpenAI API (`gpt-4o-mini`, `text-embedding-3-small`)
- **Frontend**: Streamlit
- **Others**: pypdf, numpy, python-dotenv, requests

## 📁 Project Structure

```text
ai-doc-assistant/
│
├── backend/
│   ├── main.py            # FastAPI app
│   ├── rag_pipeline.py    # RAG logic (FAISS + OpenAI)
│   ├── models.py          # Pydantic models
│   ├── utils.py           # PDF loading, chunking, paths
│   └── data/
│       ├── uploaded_docs/ # Uploaded PDFs
│       └── vector_store/  # FAISS index + metadata
│
├── frontend/
│   └── app.py             # Streamlit UI
│
├── .env                   # OpenAI API key (not committed)
└── requirements.txt
