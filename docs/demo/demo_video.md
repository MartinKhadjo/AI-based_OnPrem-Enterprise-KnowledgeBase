# Demo Video – AI-based On-Premises Enterprise Knowledge Base

This page provides a public-safe video walkthrough for the **AI-based On-Premises Enterprise Knowledge Base**. The actual demo video is hosted externally because the video file is large and should not be committed directly to the Git repository.

## Watch the demo

[![Watch the Knowledge Base demo on YouTube](https://img.youtube.com/vi/2YoWu04axCs/hqdefault.jpg)](https://www.youtube.com/watch?v=2YoWu04axCs&t=30s)

**Video link:** <https://www.youtube.com/watch?v=2YoWu04axCs&t=30s>

## What the video demonstrates

The walkthrough is intended to show the product from a user and operator perspective without exposing proprietary implementation details. It can be used by recruiters, engineering managers and technical reviewers to understand the practical value of the system.

The demo focuses on:

- the browser-based interaction model;
- document ingestion and refresh workflows;
- the transition from raw documents to processed knowledge artifacts;
- ask/chat behavior over indexed enterprise documents;
- the high-level retrieval-augmented generation workflow;
- on-premises operation and privacy-oriented system design.

## Why the video is linked instead of stored in Git

The video is intentionally not stored directly in the repository because large binary files make a Git repository harder to clone, review and maintain. Hosting the walkthrough on YouTube keeps the repository lightweight while still giving reviewers direct visual evidence that the software exists and works.

This repository remains a documentation-only public showcase. The video complements the architecture documentation, diagrams and written evidence layer; it does not replace the private source code repository.

## Public-safe boundaries

The demo and this repository should not disclose:

- production source code;
- private prompts;
- API keys or `.env` values;
- model weights or deployable payloads;
- private customer, institute or research data;
- exact internal configuration details that would enable a direct copy of the system.

## Suggested README section

You can add the following section to `README.md`:

```markdown
## Demo Video

A public-safe walkthrough of the AI-based On-Premises Enterprise Knowledge Base is available on YouTube:

[![Watch the Knowledge Base demo on YouTube](https://img.youtube.com/vi/2YoWu04axCs/hqdefault.jpg)](https://www.youtube.com/watch?v=2YoWu04axCs&t=30s)

The video demonstrates the user-facing workflow and the value of the system while keeping the proprietary source code, prompts, secrets, model setup and private data out of the public repository.
```

## Recommended repository placement

Place this file at:

```text
docs/demo-video.md
```

Then link it from the main `README.md`, for example:

```markdown
- [Demo video](docs/demo-video.md)
```

## Recommended commit message

```text
Add demo video link
```
