# Performance and Scalability

The Knowledge Base separates expensive ingest-time work from latency-sensitive ask-time work. This is essential for scaling an internal corpus.

## Ingest-time characteristics

Ingest-time is dominated by document processing and index freshness:

1. Registry scan detects new, changed or deleted files.
2. Optional staging moves files into a faster working directory.
3. OCR handles scanned PDFs and images.
4. Partitioning creates normalized document elements.
5. Chunking creates retrieval-ready passages.
6. Embedding and lexical preparation produce search features.
7. Stores and vector indexes are updated.

The slowest stage depends on corpus composition. OCR-heavy corpora are CPU-bound and can dominate full initial ingest. Incremental ingest is much cheaper because unchanged documents can be skipped.

## Ask-time characteristics

Ask-time focuses on relevance and responsiveness:

1. User question enters the backend.
2. Chat and memory context are prepared.
3. Hybrid retrieval builds a candidate set.
4. Fusion and reranking improve the final evidence set.
5. Prompt construction passes only selected evidence to the LLM.
6. Local generation returns a cited answer.

The retrieval layer can scale well once indexes are built. The most visible runtime bottleneck is often local LLM generation rather than search itself.

## Design choices that support scale

- Separate raw and processed data to avoid repeated full parsing.
- Incremental registry logic so changed/deleted files are propagated without full rebuilds.
- Lexical plus vector retrieval to improve recall across exact and semantic queries.
- Reranking before generation to reduce irrelevant context.
- Local LLM server isolation so model lifecycle can be monitored and restarted.
- Chat storage independent of raw artifacts to preserve continuity.

## Practical scaling recommendations

- Keep processed-data on fast SSD storage.
- Use GPU acceleration for embeddings and local generation where possible.
- Treat OCR as the main full-ingest bottleneck for scanned corpora.
- Use representative question sets to compare answer quality after chunking, retrieval or reranking changes.
- Monitor model-server busy states and protect local generation with sensible concurrency limits.
