# HPM Anita: Accounting Ledger PDF Processing Workflow

## Overview

Processes newly uploaded accounting PDFs from Google Drive, extracts pages through a PDF tools service, parses ledger rows with JavaScript/regex logic, groups accounts, matches transactions, and generates structured accounting outputs.

## Use Case

Finance/accounting automation for reviewing ledger PDFs, finding mismatches, and reducing manual verification work.

## Main Features

- n8n workflow export included as `workflow.json`
- Credential references removed for safe GitHub publishing
- Pinned/private execution data removed
- Designed to be imported and reconnected inside n8n

## Integrations

Google Drive, HTTP APIs

## Workflow Structure

This workflow contains **16 nodes**.

| Node Type | Count |
|---|---:|
| `n8n-nodes-base.code` | 8 |
| `n8n-nodes-base.googleDrive` | 2 |
| `n8n-nodes-base.googleDriveTrigger` | 1 |
| `n8n-nodes-base.set` | 1 |
| `n8n-nodes-base.httpRequest` | 1 |
| `n8n-nodes-base.splitOut` | 1 |
| `n8n-nodes-base.splitInBatches` | 1 |
| `n8n-nodes-base.convertToFile` | 1 |

## Required Environment Variables / Credentials

Set these in n8n credentials or environment variables before activating the workflow:

- `GOOGLE_DRIVE_FOLDER_ID`
- `PDF_TOOLS_BASE_URL`
- `OUTPUT_FOLDER_ID`
- `OPENAI_API_KEY`

## Setup

1. Deploy or configure the PDF extraction service endpoint.
2. Create a Google Drive input folder for accounting PDFs.
3. Reconnect Google Drive and any downstream output credentials.
4. Replace internal service URLs with environment variables.
5. Run with a sample non-confidential ledger PDF.

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
