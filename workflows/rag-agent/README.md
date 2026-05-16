# RAG Agent: Google Drive PDF Ingestion to Pinecone

## Overview

Automatically watches a Google Drive folder for new PDF files, downloads them, splits the document text, creates OpenAI embeddings, and stores the chunks in a Pinecone vector index for RAG/search workflows.

## Use Case

Knowledge-base ingestion for AI assistants, document search, and retrieval-augmented generation pipelines.

## Main Features

- n8n workflow export included as `workflow.json`
- Credential references removed for safe GitHub publishing
- Pinned/private execution data removed
- Designed to be imported and reconnected inside n8n

## Integrations

Google Drive, Pinecone

## Workflow Structure

This workflow contains **6 nodes**.

| Node Type | Count |
|---|---:|
| `n8n-nodes-base.googleDriveTrigger` | 1 |
| `n8n-nodes-base.googleDrive` | 1 |
| `@n8n/n8n-nodes-langchain.vectorStorePinecone` | 1 |
| `@n8n/n8n-nodes-langchain.embeddingsOpenAi` | 1 |
| `@n8n/n8n-nodes-langchain.documentDefaultDataLoader` | 1 |
| `@n8n/n8n-nodes-langchain.textSplitterRecursiveCharacterTextSplitter` | 1 |

## Required Environment Variables / Credentials

Set these in n8n credentials or environment variables before activating the workflow:

- `OPENAI_API_KEY`
- `PINECONE_API_KEY`
- `GOOGLE_DRIVE_FOLDER_ID`
- `PINECONE_INDEX`
- `PINECONE_NAMESPACE`

## Setup

1. Create or choose a Google Drive folder for source PDFs.
2. Create a Pinecone index and namespace.
3. Reconnect Google Drive, OpenAI, and Pinecone credentials in n8n.
4. Replace placeholder folder/index/namespace values.
5. Upload a sample PDF and confirm vectors are inserted.

## Import Into n8n

1. Open n8n.
2. Go to **Workflows**.
3. Select **Import from File**.
4. Upload `workflow.json`.
5. Reconnect all credentials.
6. Review all placeholder values such as `REPLACE_WITH_YOUR_ID`.
7. Test manually before activating.

## Security Notes

- This export has been sanitized for GitHub.
- Real credential references were removed.
- Pinned execution data was removed.
- Hardcoded API keys, personal emails, private Drive/Sheets links, and webhook identifiers were replaced where detected.
- Before making the repository public, run a final secret scan.

## Suggested Improvements

- Replace hardcoded IDs with environment variables.
- Add sample input/output screenshots.
- Add a short demo GIF or workflow canvas screenshot.
- Add error handling and retry logic where external APIs are used.
