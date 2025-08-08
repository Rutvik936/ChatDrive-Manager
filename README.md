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

- `workflows/` — Contains exported `whatsapp chat bot.json` of n8n workflow
- `assets/` — Screenshots 

## 🔐 Note

All credentials (Twilio, Google Drive, PDF.co, Cohere) are stripped out and replaced with placeholders. You need to configure them in your n8n instance.

## 🔧 Setup

1. Import the JSON in 'whatsapp chat bot.json' to your local n8n instance.
2. Create credentials for:
   - Twilio API
   - Google Drive OAuth2
   - PDF.co API Key
   - Cohere API
3. Deploy and test with WhatsApp commands like:
LIST /ProjectX
DELETE /ProjectX/report.pdf
MOVE /ProjectX/report.pdf /Archive
SUMMARY /null/File_name.pdf/null


To import it into n8n:
1. Open your [n8n cloud](https://n8n.io) or self-hosted instance.
2. Go to `Workflows > Import`.
3. Select the `whatsapp chatbot .json` file.
4. Update all credential placeholders:
   - `TWILIO_ACCOUNT_ID_PLACEHOLDER`
   - `GOOGLE_DRIVE_ACCOUNT_ID_PLACEHOLDER`
   - `COHERE_API_ID_PLACEHOLDER`
   - `PDF_CO_API_KEY_PLACEHOLDER`

---

## 💬 Supported WhatsApp Commands

| Command                  | Format                                   | Description                              |
|--------------------------|------------------------------------------|------------------------------------------|
| **List files**           | `LIST /FolderName`                       | Lists all files in a folder              |
| **Delete a file**        | `DELETE /FolderName/FileName.pdf`        | Deletes the specified file               |
| **Move a file**          | `MOVE /Folder/FileName.pdf /Target`      | Moves a file to another folder           |
| **Summarize PDF**        | `Summary /null/File_name.pdf/null`       | Returns AI-based summary in bullets      |

---

## 📦 Optional Docker Deployment

To test the workflow locally with Docker:

```bash
docker run -it --rm \
  -p 5678:5678 \
  -v ~/.n8n:/home/node/.n8n \
  -e N8N_BASIC_AUTH_USER=admin \
  -e N8N_BASIC_AUTH_PASSWORD=password \
  n8nio/n8n
