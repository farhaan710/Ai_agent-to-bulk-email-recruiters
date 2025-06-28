🤖 AI Agent to Bulk Email Recruiters using n8n
This project is a no-code/low-code automation workflow built with n8n that automates personalized cold emails to recruiters based on data from Google Sheets and AI-powered email generation using OpenAI's GPT models.

🚀 Features
⏰ Scheduled Automation using a time-trigger.

📊 Google Sheets Integration to pull recruiter data (name, title, company, etc.).

🤖 AI-Powered Email Generator using OpenAI (ChatGPT/GPT-4o).

📧 Automated Email Sending via Gmail.

🧾 Status Update in Google Sheets post email delivery.

📋 Prerequisites
Before deploying this workflow, ensure the following prerequisites are fulfilled:

1. n8n Setup
Self-hosted n8n instance or n8n Cloud account.

n8n installation guide

2. Google Sheets Setup
A spreadsheet with the following columns (minimum required):

Name

FirstName

Email

Job Title

Company

Status (Todo or Done)

Ensure the sheet is accessible via the Google account you’ll connect in n8n.

3. Google OAuth Credentials
Connect a Google Sheets credential in n8n.

Connect a Gmail credential in n8n.

4. OpenAI API Key
An OpenAI account with a valid API key (recommended model: gpt-4o-mini or similar).

Set up OpenAI credentials in n8n under OpenAI API.

🧠 Workflow Overview
mermaid
Copy
Edit
graph TD
  A[Schedule Trigger] --> B[Fetch Lead from Google Sheet]
  B --> C[Generate Personalized Email with GPT-4o]
  C --> D[Send Email via Gmail]
  D --> E[Update Status in Google Sheet]
🔧 How It Works
Trigger: The schedule trigger runs every 5–7 minutes (randomized).

Fetch Lead: Pulls one recruiter with Status = Todo from your Google Sheet.

Generate Email: Uses OpenAI to generate a short personalized cold email based on recruiter info.

Send Email: Automatically sends the email using Gmail.

Update Sheet: Marks the recruiter row as DONE in the sheet after email is sent.

📄 Personalization Prompt
The email is generated with the following logic:

Introduction using the company’s mission.

Your profile highlighted as:

"As an AWS Cloud Engineer with experience of monitoring and managing AWS services."

Emphasis on alignment with the recruiter’s company.

Concludes with a conversational call-to-action.

All responses are under 100 words, suitable for cold outreach.
