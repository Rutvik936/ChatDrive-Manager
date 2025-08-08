# WhatsApp Chatbot with Google Drive + PDF Summary

An n8n-based chatbot that uses WhatsApp via Twilio to perform commands on Google Drive such as:

- 📄 List files
- 🗑 Delete files
- 📂 Move files to another folder
- 📚 Summarize PDF content into bullet points

## 🚀 Features

- Built using [n8n](https://n8n.io)
- Twilio WhatsApp integration
- Google Drive file access & manipulation
- PDF text extraction via PDF.co
- AI-powered summarization using LangChain agent + Cohere

## 📂 Folder Structure

- `workflows/` — Contains exported `whatsapp_chat bot.json` of n8n workflow
- `assets/` — Screenshots or sample output (optional)

## 🔐 Note

All credentials (Twilio, Google Drive, PDF.co, Cohere) are stripped out and replaced with placeholders. You need to configure them in your n8n instance.

## 🔧 Setup

1. Import the JSON in `workflows/` to your local n8n instance.
2. Create credentials for:
   - Twilio API
   - Google Drive OAuth2
   - PDF.co API Key
   - Cohere API
3. Deploy and test with WhatsApp commands like:
LIST /ProjectX
DELETE /ProjectX/report.pdf
MOVE /ProjectX/report.pdf /Archive
SUMMARY /null/File.pdf/null
