# n8n Workflow Portfolio

A GitHub-ready portfolio of sanitized n8n workflows.

## Included Workflows

| Workflow | Folder | Description |
|---|---|---|
| [RAG Agent: Google Drive PDF Ingestion to Pinecone](workflows/rag-agent/) | `rag-agent` | Automatically watches a Google Drive folder for new PDF files, downloads them, splits the document text, creates OpenAI embeddings, and stores the chunks in a Pinecone vector index for RAG/search workflows. |
| [WhatsApp AI Assistant with Long-Term Memory via Supabase](workflows/long-term-memory-supabase/) | `long-term-memory-supabase` | Receives WhatsApp messages, retrieves previous conversation memory from Supabase, sends the context into an AI agent, replies on WhatsApp, and can save new memory records back into Supabase. |
| [Telegram Day Trading Analysis Agent](workflows/day-trading-agent/) | `day-trading-agent` | Accepts a ticker symbol from Telegram, pulls multi-timeframe market candle data, fetches recent news, runs AI sentiment analysis, combines technical and sentiment context, and returns a trading-style recommendation in Telegram. |
| [B2B Client Outreach and Follow-Up Automation](workflows/client-outreach-automation/) | `client-outreach-automation` | Automates lead tracking and follow-up for business outreach. It reads sent-lead records from Google Sheets, filters contacts due for follow-up, waits with randomized delay, sends follow-up emails, and updates the tracker. |
| [HPM Anita: Accounting Ledger PDF Processing Workflow](workflows/hpm-anita-accounting/) | `hpm-anita-accounting` | Processes newly uploaded accounting PDFs from Google Drive, extracts pages through a PDF tools service, parses ledger rows with JavaScript/regex logic, groups accounts, matches transactions, and generates structured accounting outputs. |
| [Telegram Nutrition AI Agent](workflows/nutrition-ai-agent/) | `nutrition-ai-agent` | Handles Telegram text, voice, and food photo inputs. It analyzes food images with AI, transcribes voice notes, logs calories/macros to Google Sheets, reads user goals, and sends nutrition coaching feedback. |

## How to Use

1. Download or clone this repository.
2. Open n8n.
3. Import the `workflow.json` file from the workflow folder you want to use.
4. Reconnect credentials inside n8n.
5. Replace placeholders like `REPLACE_WITH_YOUR_ID`.
6. Test the workflow manually before activating it.

## Security

These workflows were sanitized before export:
- Credential objects removed.
- Pinned execution data removed.
- Webhook IDs replaced.
- Known hardcoded API keys replaced with environment variable references.
- Personal emails and private Google Drive/Sheets URLs replaced where detected.

Still, before publishing publicly, run:

```bash
grep -Rni "apikey\|api_key\|token\|secret\|password\|webhookId\|credentials\|gmail\|@gmail" .
```

## Suggested Repository Name

`n8n-ai-automation-portfolio`

## Suggested GitHub Commands

```bash
git init
git add .
git commit -m "Add sanitized n8n workflow portfolio"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/n8n-ai-automation-portfolio.git
git push -u origin main
```

## License

MIT License suggested. Add a `LICENSE` file before publishing if you want others to reuse these workflows.
