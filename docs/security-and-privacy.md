# Security and Privacy

This repository is intentionally documentation-only. It is designed to prove engineering ability without publishing the private code or exposing operational secrets.

## Public showcase boundaries

Do not include:

- source code;
- prompt templates;
- local `.env` files;
- API keys;
- model weights;
- raw document corpora;
- processed indexes;
- internal customer or institute data;
- binaries or installers.

## Operational security principles

- Keep application files, raw documents and processed-data artifacts separated.
- Restrict write access to configuration, models, processed-data and logs.
- Treat raw documents and chat exports as potentially sensitive.
- Use network-visible raw paths only when references must work across machines.
- Keep local model services and backend ports inside trusted network boundaries unless explicitly hardened.

## Secrets management

Configuration files may contain paths, runtime options or service configuration. In production, secrets belong in local environment files or a secure secret store, never in a public repository.

## Data protection note

The system is designed for on-premises operation, which supports privacy-sensitive internal knowledge workflows. However, on-prem deployment alone is not a complete security model. Access control, backup strategy, disk encryption, logging policy and operational procedures must be defined by the deploying organization.
