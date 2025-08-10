# Intern-Task-2

<img width="1262" height="760" alt="image" src="https://github.com/user-attachments/assets/d94c6269-db2d-4558-9bc0-0a4126dddcc3" />

<img width="1229" height="505" alt="image" src="https://github.com/user-attachments/assets/48b3658e-1942-408c-87be-4fe6cbca1b57" />

<img width="1263" height="478" alt="image" src="https://github.com/user-attachments/assets/02b7e56a-9c76-453f-9cfc-619eb7f20725" />

<img width="1564" height="589" alt="image" src="https://github.com/user-attachments/assets/17c37949-6021-43f3-b4dc-2992700f9ec9" />


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

## 3. Exporting and Uploading Workflows to GitHub

1. In n8n, open your workflow.
2. Click on the Workflow menu (⋮) → Export → Download as file.
3. Save the file with a descriptive name, e.g. workflows/my-workflow.json.
4. Add the exported file to your Git repository:

## 4. Importing Workflows from Github

1. Download the .json workflow file from GitHub.
2. In n8n, go to the Workflows page.
3. Click Import from File.
4. Select the downloaded workflow JSON to load it into n8n.

## 5. Command Syntax

- **LIST**: LIST Folder/File
- **MOVE**: MOVE Source Destination
- **DELETE**: DELETE File/Folder
- **SUMMARY**: SUMMARY Filename

