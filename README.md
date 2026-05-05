# AI-based On-Premises Enterprise Knowledge Base

**Documentation-only public showcase for a proprietary on-premises RAG system.**

This repository presents the architecture, operating model and engineering evidence of an AI-based enterprise knowledge base built around retrieval-augmented generation (RAG). It is intended for recruiters, engineering managers and technical interviewers who want to understand the system design without accessing private source code, prompts, credentials, customer data or deployable binaries.

## What the system does

The Knowledge Base transforms internal documents into searchable, evidence-based answers. Raw files are ingested, normalized, OCR-processed when needed, partitioned, chunked, embedded and indexed. Users interact through a browser UI; requests are routed through a Flask Web UI to a FastAPI backend, which works against processed artifacts and a local OpenAI-compatible LLM server.

The important architectural principle is that the application does **not** answer directly from the raw file folder. It answers from processed artifacts: OCR outputs, parsed elements, chunk records, lexical indexes, vector indexes and chat state.

## Core capabilities

- Local or network-accessible on-premises RAG workspace.
- Browser-based operator UI for status, refresh, ask/chat and exports.
- FastAPI control plane for health, ingest orchestration, retrieval, reranking, chat persistence and ask endpoints.
- Incremental ingest pipeline: registry scan, optional staging, OCR, partitioning, chunking, embedding and index update.
- Hybrid retrieval using lexical and vector search, followed by reranking before prompt construction.
- Local LLM generation through an OpenAI-compatible model server.
- Separate raw, processed-data and application folders to avoid self-indexing and operational confusion.
- Designed for maintainability: documented runtime stages, storage layers, failure propagation and operator/developer checklists.

## Repository structure

```text
.
├── README.md
├── CHANGELOG.md
├── LICENSE.md
├── NOTICE.md
└── docs/
    ├── architecture.md
    ├── user-workflows.md
    ├── deployment-and-operations.md
    ├── security-and-privacy.md
    ├── performance-and-scalability.md
    ├── portfolio-evidence.md
    ├── engineering-boundaries.md
    ├── deutsche-kurzbeschreibung.md
    ├── github-repository-description.txt
    ├── source-notes/
    │   └── diagram-provenance.md
    └── assets/
        ├── raw-to-searchable-knowledge.png
        ├── ask-answer-sequence.png
        ├── component-architecture.png
        └── incremental-ingest-sequence.png
```

## Diagrams

The diagrams in `docs/assets/` are extracted from the original technical manual at high resolution and kept as portfolio-safe architecture evidence. They show the real system topology and flows without exposing implementation code.

| Diagram | Purpose |
|---|---|
| `raw-to-searchable-knowledge.png` | End-to-end ingest and retrieval pipeline from raw input to cited answer. |
| `ask-answer-sequence.png` | Ask-time sequence across UI, backend, chat store, memory, retrieval, reranking and LLM generation. |
| `component-architecture.png` | Component-oriented architecture view across UI, API, ingest, retrieval, chat and LLM subsystems. |
| `incremental-ingest-sequence.png` | Incremental refresh sequence from browser action to background worker completion. |

## Technology profile

The public documentation intentionally stays at a professional architecture level. The system is described by its observable layers and responsibilities rather than by copyable source code. The technical stack includes Python web services, RAG orchestration, document processing, OCR, lexical/vector retrieval, reranking, local model serving and operational health checks.

## What is intentionally not included

This repository does **not** contain:

- production source code;
- model weights;
- private prompts;
- API keys, `.env` files or local paths;
- binaries, installers or deployment payloads;
- customer, research or institute documents;
- full source inventory that would make the private implementation easy to reproduce.

For deeper review, code walkthroughs or deployable artifacts, access should be handled privately under appropriate NDA/licensing terms.

## Copyright

Copyright © 2026 Martin Khadjavian. All rights reserved.
