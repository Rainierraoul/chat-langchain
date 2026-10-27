# chat-langchain

Historical fork of [langchain-ai/chat-langchain](https://github.com/langchain-ai/chat-langchain), retained for local PDF-ingestion experiments. The application originates with the upstream contributors; this fork includes changes to local document ingestion.

## Credentials

Provide `OPENAI_API_KEY` through the process environment using a key from your own account. The ingestion and query clients read that variable and fail when it is missing. Never put a credential into source code or commit an environment file.

Any key that has appeared in repository history must be treated as exposed and revoked at its provider. Removing a key from the current files does not revoke it or remove copies from Git history.

## Scope and use

This is historical prototype code. Compatibility with current LangChain releases and production operation have not been established. Dependency versions are recorded in `requirements.txt`.

The `ingest_docs(file)` function in `ingest.py` reads a PDF from `docs/`, splits its text and creates a local FAISS store. `query_data.py` builds the conversational retrieval chain used by the application. Only load local vector-store files from a trusted source, because the prototype uses Python pickle files.

The original framework and this fork's ingestion work should be attributed separately when describing the project.
