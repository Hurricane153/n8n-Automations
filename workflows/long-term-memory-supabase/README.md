# WhatsApp AI Assistant with Long-Term Memory via Supabase

## Overview

Receives WhatsApp messages, retrieves previous conversation memory from Supabase, sends the context into an AI agent, replies on WhatsApp, and can save new memory records back into Supabase.

## Use Case

Personal or business WhatsApp assistant that remembers previous interactions.

## Main Features

- n8n workflow export included as `workflow.json`
- Credential references removed for safe GitHub publishing
- Pinned/private execution data removed
- Designed to be imported and reconnected inside n8n

## Integrations

OpenAI, Supabase, WhatsApp

## Workflow Structure

This workflow contains **7 nodes**.

| Node Type | Count |
|---|---:|
| `n8n-nodes-base.whatsAppTrigger` | 1 |
| `@n8n/n8n-nodes-langchain.agent` | 1 |
| `@n8n/n8n-nodes-langchain.lmChatOpenAi` | 1 |
| `n8n-nodes-base.whatsApp` | 1 |
| `n8n-nodes-base.supabaseTool` | 1 |
| `n8n-nodes-base.aggregate` | 1 |
| `n8n-nodes-base.supabase` | 1 |

## Required Environment Variables / Credentials

Set these in n8n credentials or environment variables before activating the workflow:

- `OPENAI_API_KEY`
- `WHATSAPP_ACCESS_TOKEN`
- `WHATSAPP_PHONE_NUMBER_ID`
- `SUPABASE_URL`
- `SUPABASE_SERVICE_ROLE_KEY`
- `SUPABASE_CHAT_MEMORY_TABLE`

## Setup

1. Create a Supabase table for chat memory.
2. Reconnect WhatsApp, OpenAI, and Supabase credentials in n8n.
3. Map your WhatsApp trigger and send-message configuration.
4. Replace placeholder Supabase table/filter values.
5. Send a WhatsApp test message and verify memory retrieval/saving.

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
