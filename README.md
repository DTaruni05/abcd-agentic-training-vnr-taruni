🧠 DataCleaningAgent

AI-Powered Automated Data Cleaning Workflow built in n8n

📌 Overview
The DataCleaningAgent is an agentic, AI-driven workflow implemented using n8n to automate the cleaning, validation, and summarization of tabular datasets (from Google Sheets).
It uses multiple specialized LLM-based agents — Imputer, Validator, and Summarizer — coordinated through an Orchestrator Agent to ensure high-quality, analytics-ready data.

🧩 Features

✅ Automated detection of missing or invalid data
✅ Smart imputation of missing values using AI (LLMs via Hugging Face)
✅ Data validation for emails, amounts, and country names
✅ Human-readable cleaning logs and summaries
✅ Seamless Google Sheets integration (read and write)
✅ Modular and easily extensible design

⚙️ High-Level Architecture

Main Components:

Google Sheets Trigger: Detects new or updated data rows.

Orchestrator Agent: Decides per row whether to Impute, Validate, or Summarize.

Imputer Agent: Suggests missing values intelligently using an LLM.

Validator Agent: Flags incorrect data (e.g., invalid email formats, non-numeric amounts).

Summarizer Agent: Generates readable summaries and cleaning audit logs.

Merge & Update Nodes: Combine all agent outputs and update cleaned data back to Sheets.

🧱 Workflow Summary

Trigger → Detects data changes in Google Sheets.

Orchestrator Function Node → Routes rows to respective agents based on condition.

Switch Node → Directs rows to Imputer, Validator, or Summarizer.

Agents (Hugging Face APIs) → Perform specific cleaning/validation tasks.

Merge Nodes → Combine outputs from all agents.

Update Node → Writes back clean, validated, and annotated data to Google Sheets.

🧰 Tech Stack

n8n – Workflow automation platform

Google Sheets API – Data source & destination

Hugging Face APIs – LLM-powered data imputation, validation, and summarization

JavaScript Function Nodes – Custom orchestration logic

JSON-based workflow structure – Reusable and modular

🚀 How to Use

Clone this repository

git clone https://github.com/<your-username>/DataCleaningAgent.git
cd DataCleaningAgent


Import the workflow into n8n

Open your n8n instance.

Go to Workflows → Import from File.

Upload the DataCleaningAgent_NEW.json file.

Set up credentials

Configure Google Sheets OAuth2 in n8n for access.

Add your Hugging Face API key for LLM-based tasks.

Connect to your dataset

Update the Google Sheet link in the workflow nodes.

Execute the workflow

Run once manually or set a trigger to monitor your sheet continuously.

🔮 Future Enhancements

Integration with Vector Databases for memory and historical recall

Support for multiple data sources (CSV, API endpoints)

Real-time dashboard to visualize cleaning statistics

🧑‍💻 Author

Taruni Donthula
Built as part of an Agentic AI Automation Use Case leveraging n8n and LLM APIs.
