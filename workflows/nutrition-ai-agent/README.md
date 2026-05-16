# Telegram Nutrition AI Agent

## Overview

Handles Telegram text, voice, and food photo inputs. It analyzes food images with AI, transcribes voice notes, logs calories/macros to Google Sheets, reads user goals, and sends nutrition coaching feedback.

## Use Case

Personal nutrition tracking assistant with multimodal input and goal-aware coaching.

## Main Features

- n8n workflow export included as `workflow.json`
- Credential references removed for safe GitHub publishing
- Pinned/private execution data removed
- Designed to be imported and reconnected inside n8n

## Integrations

Google Drive, Google Sheets, HTTP APIs, OpenAI, Telegram

## Workflow Structure

This workflow contains **25 nodes**.

| Node Type | Count |
|---|---:|
| `n8n-nodes-base.telegram` | 4 |
| `n8n-nodes-base.googleSheets` | 4 |
| `@n8n/n8n-nodes-langchain.openAi` | 2 |
| `n8n-nodes-base.merge` | 2 |
| `n8n-nodes-base.set` | 2 |
| `@n8n/n8n-nodes-langchain.lmChatOpenAi` | 2 |
| `@n8n/n8n-nodes-langchain.agent` | 2 |
| `n8n-nodes-base.telegramTrigger` | 1 |
| `n8n-nodes-base.switch` | 1 |
| `n8n-nodes-base.httpRequest` | 1 |
| `n8n-nodes-base.googleDrive` | 1 |
| `n8n-nodes-base.code` | 1 |
| `n8n-nodes-base.aggregate` | 1 |
| `@n8n/n8n-nodes-langchain.memoryBufferWindow` | 1 |

## Required Environment Variables / Credentials

Set these in n8n credentials or environment variables before activating the workflow:

- `OPENAI_API_KEY`
- `TELEGRAM_BOT_TOKEN`
- `GOOGLE_SHEETS_FOOD_DATA_ID`
- `GOOGLE_DRIVE_FOLDER_ID`
- `CLOUDINARY_CLOUD_NAME`
- `CLOUDINARY_UPLOAD_PRESET`

## Setup

1. Create Google Sheets tabs for food data and goals.
2. Create a Telegram bot and connect credentials in n8n.
3. Configure Cloudinary or replace image hosting with your preferred storage.
4. Reconnect OpenAI, Telegram, Google Drive, and Google Sheets credentials.
5. Send a food photo, voice note, and text message to test all branches.

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
