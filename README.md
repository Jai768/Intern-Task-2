# Intern-Task-2

# n8n Workflow Setup Guide

This repository contains exported n8n workflows and instructions for setting up the required integrations:

- Twilio Sandbox for WhatsApp
- Google API credentials for Drive/Docs/Sheets
- Command syntax for n8n expressions
- Exporting and importing workflows

---

## 1. Twilio Sandbox Setup (WhatsApp)

1. Go to the [Twilio Console](https://www.twilio.com/console) and sign in.
2. Navigate to **Messaging → Try it Out → Send a WhatsApp message**.
3. Click **Activate Sandbox** to enable the WhatsApp sandbox environment.
4. Follow the on-screen instructions:
   - Save the Twilio sandbox number to your phone contacts.
   - Send the join code (e.g., `join light-trees`) via WhatsApp to that number.
5. Locate your **Account SID** and **Auth Token** from the Twilio dashboard.
6. In n8n, create a new Twilio credential and enter these values.

---

## 2. Google API Credentials Setup

1. Open the [Google Cloud Console](https://console.cloud.google.com/).
2. Create or select an existing project.
3. Go to **APIs & Services → Credentials**.
4. Click **Create Credentials → OAuth Client ID**.
   - Select **Web Application**.
   - Set **Authorized redirect URIs** to:
     ```
     https://<your-n8n-domain>/rest/oauth2-credential/callback
     ```
5. Download the generated credentials JSON file.
6. In n8n, add a new Google Drive (or Sheets, Docs) credential:
   - Upload the credentials JSON or enter `client_id` and `client_secret`.
7. Test the credential connection in n8n before using it in workflows.

---

## 3. n8n Command Syntax Examples

### Trimming text to 1600 characters
```javascript
{{ $json.content.parts[0].text.slice(0, 1600) }}
