# Telegram Day Trading Analysis Agent

## Overview

Accepts a ticker symbol from Telegram, pulls multi-timeframe market candle data, fetches recent news, runs AI sentiment analysis, combines technical and sentiment context, and returns a trading-style recommendation in Telegram.

## Use Case

Educational trading assistant for combining market data, news sentiment, and AI-generated trade scenarios.

## Main Features

- n8n workflow export included as `workflow.json`
- Credential references removed for safe GitHub publishing
- Pinned/private execution data removed
- Designed to be imported and reconnected inside n8n

## Integrations

HTTP APIs, OpenAI, Telegram

## Workflow Structure

This workflow contains **14 nodes**.

| Node Type | Count |
|---|---:|
| `n8n-nodes-base.httpRequest` | 4 |
| `n8n-nodes-base.merge` | 2 |
| `n8n-nodes-base.aggregate` | 2 |
| `n8n-nodes-base.telegramTrigger` | 1 |
| `@n8n/n8n-nodes-langchain.openAi` | 1 |
| `n8n-nodes-base.code` | 1 |
| `@n8n/n8n-nodes-langchain.agent` | 1 |
| `@n8n/n8n-nodes-langchain.lmChatOpenAi` | 1 |
| `n8n-nodes-base.telegram` | 1 |

## Required Environment Variables / Credentials

Set these in n8n credentials or environment variables before activating the workflow:

- `OPENAI_API_KEY`
- `TELEGRAM_BOT_TOKEN`
- `TWELVEDATA_API_KEY`
- `NEWSAPI_KEY`

## Setup

1. Create Telegram bot credentials.
2. Add TwelveData and NewsAPI keys as n8n environment variables or credentials.
3. Reconnect OpenAI and Telegram credentials in n8n.
4. Confirm API key query parameters use env variables, not hardcoded values.
5. Send a symbol such as AAPL or TSLA to the bot.

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
