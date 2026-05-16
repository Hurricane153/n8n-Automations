# Security Policy

## Before Publishing Publicly

These workflow files have been sanitized, but you should still review them before publishing.

Run:

```bash
grep -Rni "apikey\|api_key\|token\|secret\|password\|webhookId\|credentials\|gmail\|@gmail" .
```

Check especially:
- HTTP Request nodes
- Google Drive / Google Sheets resource IDs
- Telegram / WhatsApp chat IDs
- SMTP sender addresses
- Cloudinary upload presets
- Any pinned data

## Recommended Practice

Use n8n credentials or environment variables instead of hardcoded values.

Example:

```json
"value": "={{ $env.TWELVEDATA_API_KEY }}"
```

Never commit `.env`, exported credentials, or pinned production execution data.
