# 📧 Cold-Email-Agent

An automated n8n workflow designed to send **personalized internship opportunity emails** to contacts stored in a Google Sheet, powered by **Google Gemini AI**.

---

## 🚀 Overview
This project is a practical example of leveraging AI for **cold email automation**.  
It uses the [n8n](https://n8n.io) workflow automation platform to:

✅ Retrieve emails from a Google Sheet  
✅ Generate unique, personalized internship emails using **Gemini LLM**  
✅ Send the emails automatically via Gmail (or any SMTP email service)

The workflow performs the following steps:
1. **Manual Trigger** – Start the workflow manually.
2. **Google Sheets Integration** – Fetch a list of email addresses.
3. **Iterate Through Contacts** – Process each email one-by-one.
4. **Gemini Email Generation** – Draft personalized internship inquiry emails.
5. **Email Sending** – Send the AI-generated email via Gmail/SMTP.

---

## ⚙️ How to Use

### 1️⃣ Download the Workflow
Download the workflow file from this repository:  
`cold-email-agent.json`

### 2️⃣ Set Up Your Google Sheet
Create a Google Sheet with the following structure:

| Email                |
|----------------------|
| jane.doe@example.com |
| john.smith@company.com |

> **Note:** Ensure the column header is exactly `Email` in the first row.

### 3️⃣ Import and Configure the n8n Workflow
1. **Import Workflow:**  
   - Open your n8n instance.
   - Go to **Workflows → New → ⋮ → Import from File** and upload `cold-email-agent.json`.

2. **Configure Credentials:**  
   - **Google Sheets:** Connect your Google Account.  
   - **Google Gemini:** Add your Gemini API key.  
   - **Email Sending:** Connect Gmail (via OAuth2) or any SMTP service.

3. **Update Node Parameters:**  
   - **Google Sheets Node:** Add your Google Sheet ID and sheet name.  
   - **Gemini Node:** Adjust the prompt as needed. For example:
     ```
     You are an enthusiastic student applying for an internship. 
     Write a brief, professional, and eager email expressing interest in an internship opportunity. 
     End with 'Best regards, Sumit Singh Rana'.
     ```
   - **Email Node:** Verify `To` is set to `{{ $json.Email }}` and customize the subject line.

---

## ▶️ Running the Workflow
- Click **Execute Workflow** to test.
- Check your email **Sent Folder** to verify messages are being delivered.

---

## 💡 Learning Points from This Project
- **Workflow Design:** How to chain trigger → data → AI → action in n8n.
- **Dynamic Data Handling:** Pass data between nodes using variables and expressions.
- **AI Integration:** Use Gemini as a dynamic part of automation pipelines.
- **Prompt Engineering:** Craft prompts for high-quality, professional email output.

---

## 📌 Tech Stack
- [n8n](https://n8n.io)
- Google Sheets API
- Google Gemini AI (LLM)
- Gmail/SMTP

---

## 🛠️ Customization Ideas
- Attach your resume automatically via Google Drive or local file.
- Use company names from the sheet for even more personalized emails.
- Add follow-up email logic for non-responses.

---

### 📜 License
This project is for educational and personal use. Feel free to fork and modify for your needs!
