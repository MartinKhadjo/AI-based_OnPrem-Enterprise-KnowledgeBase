# Deployment and Operations

## Installation model

A correct deployment starts with a strict separation of three locations:

| Location | Contents | Recommendation |
|---|---|---|
| Installation folder | Runnable application, runtime, models, configuration, scripts, logs and generated environment files. | Keep on fast local storage. |
| Raw folder | Original documents that users maintain and want to index. | Can be shared or network-visible when multiple users need consistent source references. |
| Processed-data folder | OCR outputs, parsed JSONL, chunk JSONL, SQLite stores, vector artifacts and chat databases. | Keep on fast SSD storage; this is the operational heart of the system. |

The raw folder and processed-data folder must not point to the same location. This prevents self-indexing, circular processing and confusing references.

## Hardware and software expectations

- Windows 10/11 64-bit environment documented for the installer, OCR tools and CUDA launcher.
- Modern multi-core CPU and at least 16 GB RAM.
- NVIDIA GPU strongly recommended for local inference and embedding throughput.
- Sufficient disk capacity for application files and growing processed-data artifacts.
- Admin rights recommended for tool installation, PATH-sensitive setup and environment actions.

## First-start validation

After installation, validate the system in this order:

1. The LLM model list endpoint responds and the LLM card is healthy.
2. The API readiness endpoint returns ready.
3. The Web UI loads and status cards render correctly.
4. The first incremental ingest progresses from queued to running to finished.
5. Parsed files, chunks, stores and vector artifacts appear in the processed-data folder.
6. A narrow test question returns a grounded answer with references.

## Operating logic

The most important operational rule is: **raw files are input; processed artifacts are the searchable truth.**

Operators should avoid editing processed-data manually. Developers should treat searcher reload, deletion propagation and readiness checks as first-class operational concerns.

## Troubleshooting quick map

| Symptom | Inspect first |
|---|---|
| Web UI works but API is red | API process, environment paths and backend readiness. |
| API works but LLM is red | GPU driver state, LLM server logs and model server process. |
| Ingest finishes but answers are empty | Parsed files, chunk files, store and vector artifacts. |
| Users cannot open references from other machines | Raw path visibility and network-accessible file references. |
