# 💬 WhatsApp Chatbot with Google Drive + PDF Summary

An **n8n-based chatbot** that connects **WhatsApp (via Twilio)** with **Google Drive** to perform automated actions such as:

- 📄 List files in a folder  
- 🗑 Delete specific files  
- 📂 Move files to another folder  
- 📚 Summarize PDF files into bullet points using AI

---

## 🚀 Features

- ⚙️ Built using [n8n](https://n8n.io/)
- 💬 Integrated with **Twilio WhatsApp API**
- 📁 File operations with **Google Drive**
- 📑 PDF text extraction via **PDF.co**
- 🧠 Summarization powered by **LangChain + Cohere AI**

---

---

## 🔐 Credentials Note

All sensitive keys are stripped and replaced with placeholders.  
You’ll need to create credentials in your n8n instance:

- `TWILIO_ACCOUNT_ID_PLACEHOLDER`
- `GOOGLE_DRIVE_ACCOUNT_ID_PLACEHOLDER`
- `PDF_CO_API_KEY_PLACEHOLDER`
- `COHERE_API_ID_PLACEHOLDER`

---

## 🔧 Setup Guide

1. Open your [n8n cloud](https://cloud.n8n.io) or local instance.
2. Go to `Workflows → Import` and upload the `whatsapp_chatbot.json`.
3. Create the required credentials:
   - Twilio API
   - Google Drive OAuth2
   - PDF.co API
   - Cohere API
4. Replace all placeholders with actual credential references.

---

## 💬 Supported WhatsApp Commands

| Command          | Format                                                | Description                                 |
|------------------|-------------------------------------------------------|---------------------------------------------|
| List Files       | `list `                                               | Lists all files                             |
| Delete a File    | `delete /FolderName/FileName.pdf/null`                | Deletes the file at given path              |
| Move a File      | `MOVE /Folder/FileName.pdf /TargetFolder`             | Moves a file from one folder to another     |
| Summarize PDF    | `SUMMARY /null/File_name.pdf/null`                    | Summarizes PDF content into bullet points   |

---

## 🐳 Docker Deployment (Optional)

To test n8n locally using Docker:

```bash
docker run -it --rm \
  -p 5678:5678 \
  -v ~/.n8n:/home/node/.n8n \
  -e N8N_BASIC_AUTH_USER=admin \
  -e N8N_BASIC_AUTH_PASSWORD=password \
  n8nio/n8n
```
## Watch Demo Video :
[Watch Demo](https://youtu.be/Pvz6HTVCSXE)
