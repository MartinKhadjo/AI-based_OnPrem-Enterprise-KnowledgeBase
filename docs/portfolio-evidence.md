# Portfolio Evidence

This document translates the Knowledge Base into engineering evidence for software engineering roles, AI engineering roles and technical interviews.

## What this project demonstrates

- **System architecture:** clear separation of UI, backend, ingest, storage, retrieval, reranking, RAG generation, chat persistence and model serving.
- **AI application engineering:** practical RAG workflow with OCR, partitioning, chunking, lexical/vector indexing, hybrid retrieval, reranking and cited generation.
- **Operational thinking:** health checks, readiness, incremental refresh, job state, processed-data boundaries and troubleshooting order.
- **Product thinking:** browser-based operator workflow, status cards, refresh actions, chat continuity and transcript export.
- **Privacy-aware design:** on-premises model serving and no public exposure of source code, prompts, secrets or internal data.
- **Maintainability:** documentation explains runtime stages, folder responsibilities, failure propagation and regression checklists.

## Why this is stronger than a code dump

A public source dump would expose proprietary implementation logic and weaken trade-secret protection. This repository instead provides an evidence layer: architecture, workflows, diagrams, operational reasoning and security boundaries. It shows the ability to design and deliver a production-oriented AI software system while keeping the private implementation protected.

## Interview talking points

- How the system prevents self-indexing by separating raw input from processed search artifacts.
- Why ingest-time and ask-time are modeled as separate lifecycles.
- Why hybrid retrieval and reranking address different failure modes.
- How local LLM serving changes deployment and concurrency assumptions.
- How incremental refresh improves operational practicality compared with full rebuilds.
- How chat persistence and memory influence the RAG answer path.

## Evidence included in this repository

- High-level architecture diagram.
- End-to-end ingest and answer pipeline diagram.
- Ask/answer sequence diagram.
- Incremental refresh sequence diagram.
- Deployment and operating guidance.
- Security/privacy boundaries.
- Scalability and troubleshooting notes.

## Evidence intentionally omitted

- production source code;
- exact prompt templates;
- model weights;
- secrets/configuration;
- raw corpora and processed indexes;
- internal deployment paths;
- binaries/installers.
