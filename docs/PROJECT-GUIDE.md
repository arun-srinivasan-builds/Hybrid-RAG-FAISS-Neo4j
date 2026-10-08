# Hybrid RAG — FAISS + Neo4j

**Learning Build · Hybrid RAG and knowledge graphs**

A hands-on retrieval project combining FAISS vector search, Neo4j graph capabilities, LangChain and a Streamlit interface.

> The repository is an evolving technical learning build; retrieval quality and coverage should be validated against the specific documents and questions used.

## Project overview

This project explores document ingestion, retrieval and knowledge-graph-assisted question answering. The codebase separates ingestion, retrieval, graph, guardrails and evaluation modules.

## Architecture

```text
Documents → Ingestion → FAISS vector store
                        ↘ Neo4j graph
User question → Retrieval → Context → Answer
                         ↘ Guardrails & evaluation
```

The diagram is a conceptual overview; consult the code for the implemented execution path.

## Technology

Python · LangChain · OpenAI · FAISS · Neo4j · Streamlit · Docker Compose

## Repository layout

- `backend/ingestion/` — document processing
- `backend/retrieval/` — retrieval logic
- `backend/graph/` — graph-related components
- `backend/vector_store/` — vector store components
- `backend/guardrails/` — safety checks
- `backend/evaluation/` — evaluation code
- `frontend/streamlit_app.py` — interface

## Run locally with Docker

1. Clone this repository and enter its directory.
2. Copy `.env.example` to `.env`, then set your own API key and Neo4j password.
3. Start the services:

```bash
docker compose up --build -d
docker compose ps
```

4. Open Streamlit at `http://localhost:8501`. Neo4j Browser is mapped to `http://localhost:7475`.

Never commit your `.env` file or credentials. The Compose setup uses named volumes for Neo4j data and logs.

## Validation and learnings

Review the guardrail and evaluation modules before relying on generated answers. Compare retrieved evidence with the original documents and record failures or gaps as part of the learning process.

## Scope

This is a technical learning project, not a claim of comprehensive document understanding or production readiness.
