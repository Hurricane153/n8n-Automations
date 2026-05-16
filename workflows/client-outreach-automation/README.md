# B2B Client Outreach and Follow-Up Automation

## Overview

Automates lead tracking and follow-up for business outreach. It reads sent-lead records from Google Sheets, filters contacts due for follow-up, waits with randomized delay, sends follow-up emails, and updates the tracker.

## Use Case

Automated B2B prospecting, CRM-style follow-up management, and sales operations for small businesses.

## Main Features

- n8n workflow export included as `workflow.json`
- Credential references removed for safe GitHub publishing
- Pinned/private execution data removed
- Designed to be imported and reconnected inside n8n

## Integrations

Google Sheets, HTTP APIs, OpenAI, SMTP Email, Telegram

## Workflow Structure

This workflow contains **33 nodes**.

| Node Type | Count |
|---|---:|
| `n8n-nodes-base.code` | 8 |
| `n8n-nodes-base.googleSheets` | 4 |
| `n8n-nodes-base.splitInBatches` | 2 |
| `n8n-nodes-base.wait` | 2 |
| `n8n-nodes-base.emailSend` | 2 |
| `n8n-nodes-base.telegramTrigger` | 2 |
| `@n8n/n8n-nodes-langchain.agent` | 2 |
| `@n8n/n8n-nodes-langchain.lmChatOpenAi` | 2 |
| `@n8n/n8n-nodes-langchain.outputParserStructured` | 2 |
| `n8n-nodes-base.telegram` | 2 |
| `n8n-nodes-base.scheduleTrigger` | 1 |
| `n8n-nodes-base.splitOut` | 1 |
| `n8n-nodes-base.httpRequestTool` | 1 |
| `n8n-nodes-base.set` | 1 |
| `n8n-nodes-base.if` | 1 |

## Required Environment Variables / Credentials

Set these in n8n credentials or environment variables before activating the workflow:

- `GOOGLE_SHEETS_TRACKER_ID`
- `SMTP_HOST`
- `SMTP_USER`
- `SMTP_PASSWORD`
- `OUTREACH_FROM_EMAIL`
- `TELEGRAM_BOT_TOKEN`
- `OPENAI_API_KEY`

## Setup

1. Create a Google Sheets tracker with the expected columns.
2. Reconnect Google Sheets, SMTP/email, Telegram, and AI credentials in n8n.
3. Replace sender email and sheet IDs with your own placeholders or variables.
4. Run in test mode with a small sample lead list.
5. Verify follow-up timestamps and statuses are updated correctly.

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
