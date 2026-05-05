# User Workflows

## Daily operator workflow

1. Confirm that the Web UI, API and LLM status cards are healthy.
2. Place new or changed source documents only in the raw folder.
3. Run an incremental refresh from the data-pipeline card.
4. Wait until the job reaches the finished state.
5. Ask one or two targeted validation questions to confirm that the updated corpus is active.
6. Export important chats to PDF when they need to be archived or shared.

## Adding new documents

Operators add documents by copying them into the raw folder. The processed-data folder should not be edited manually. After copying files, run an incremental refresh so the registry can identify changes and propagate them into OCR outputs, chunk records, lexical indexes and vector indexes.

## Replacing documents

If possible, replace a document at the same path. This helps the registry recognize it as a changed file rather than a completely unrelated document. Then run incremental refresh and validate the result with a narrow test question.

## Removing documents

Delete the document from the raw folder and run incremental refresh. The pipeline should propagate deletion into processed search artifacts, so removed documents no longer appear as answer evidence.

## Asking questions

The ask workflow is chat-oriented. The backend stores conversation turns, optionally builds memory from recent or relevant earlier messages, retrieves evidence, reranks candidate passages and generates the final answer with references.

## Exporting results

For workflows that require auditability or handover, important chats can be exported. Public showcase material should never include private answers, customer data or internal documents.
