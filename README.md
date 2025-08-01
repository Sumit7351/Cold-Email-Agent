n8n Gemini Internship Email Agent
An automated workflow designed to send personalized internship opportunity emails to a list of contacts stored in a Google Sheet, powered by Google Gemini.

🚀 Overview
This project is a practical example of leveraging AI for automation. It uses the n8n workflow automation platform to connect to Google Sheets and a Gemini language model to generate unique, personalized emails. The goal is to streamline the process of reaching out for internship opportunities, making each message more effective and personal.

The workflow performs the following steps:

Triggers the automation manually.

Retrieves a list of emails from a Google Sheet.

Iterates through each email address individually.

Prompts the Gemini model to draft a unique email body for an internship inquiry.

Sends the AI-generated email to the contact using your configured email service.

⚙️ How to Use
1. Download the Workflow
You can download the n8n workflow JSON file directly from this repository:
internship-email-agent.json

2. Set Up Your Google Sheet
You will need a Google Sheet with a list of email addresses. The workflow is configured to read the following column (you can adjust this in the n8n workflow):

Column Header

Example Content

Email

jane.doe@example.com

Note: Ensure your sheet has this exact column header in the first row.

3. Import and Configure the n8n Workflow
Import: In your n8n instance, go to "Workflows" and click "New". Then, use the three-dot menu to "Import from JSON" and upload the file you downloaded.

Credentials: You will need to set up credentials for the following nodes:

Google Sheets: Connect your Google account.

Google Gemini: Connect your Google Gemini API key.

Email Send: Connect your email service (e.g., Gmail via SMTP).

Update Node Parameters:

Google Sheets: In the "Get Emails" node, provide your specific Sheet ID and Sheet Name.

Gemini: In the "Basic LLM Chain" node, review the prompt. Since the sheet only contains emails, the prompt will need to be more generic. For example: "You are an enthusiastic student applying for an internship. Write a brief, professional, and eager email body to express interest in an internship opportunity. End with 'Best regards, [Your Name]'."

Email Send: In the "Send Email" node, update the From Email field and verify that the To and Subject fields are correctly referencing the data from the previous nodes. The email address will be referenced as {{ $json.Email }}.

4. Run the Workflow
Once everything is configured, click the "Execute Workflow" button to run a test. You can check your email's sent folder to verify that the emails were drafted and sent correctly.

💡 Learning Points from This Project
This project is a great learning tool for anyone interested in automation and AI. By using this workflow, you can understand:

Workflow Design: How to create a sequential flow of operations (trigger -> data source -> AI -> action).

Dynamic Data Handling: Using expressions and variables to pass information between different services.

AI Integration: How a language model can be a dynamic part of an automation pipeline, not just a standalone tool.

Prompt Engineering: The importance of crafting a clear and specific prompt to get the desired output from an LLM.

Feel free to fork this repository and adapt the workflow for your own needs!
