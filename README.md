# AI-Powered Automation Pipelines (n8n + RAG)

This repository contains three prototype automation pipelines designed to demonstrate the use of **n8n**, **vector databases**, and **LLM-powered retrieval-augmented generation (RAG)** for streamlining business and support workflows in a healthcare context.

---

## 🚀 Overview

These pipelines show how modern AI and low-code automation can:
- **Ingest and index knowledge** from internal documents.
- **Classify and enrich inbound inquiries** with AI research.
- **Assist technical support teams** by retrieving relevant documentation and drafting actionable summaries.

The goal is to reduce manual work, speed up responses, and provide plain-English outputs for non-technical staff.

---

## 📂 Pipelines

### 1. Knowledge Database Pipeline
**Trigger:** New PDF uploaded to Google Drive.  
**Process:**
- Downloads the file and extracts its text.
- Chunks content and generates embeddings.
- Stores embeddings in a Pinecone vector database with metadata.
- Logs metadata in a SQL/SharePoint table for audit and compliance.

**Outcome:** A searchable knowledge base ready to power RAG workflows.

<img width="1387" height="526" alt="Knowledge Database Pipeline" src="https://github.com/user-attachments/assets/e0f6e110-eb3b-49fd-a6ad-888ff5004bfc" />

---

### 2. Contact Routing & Sales Insights
**Trigger:** User submits a Contact Us form.  
**Process:**
- Classifies the inquiry as **Sales** or **Other** via LLM.
- **Sales Inquiry:**
  - Stores lead in CRM.
  - Sends auto-acknowledgment email.
  - Performs background research on the organization.
  - Prepares an enriched email for the Sales Team with:
    - Contact details
    - Company research
    - Healthcare relevance
    - Suggested next actions
- **Other Inquiry:**
  - Stores in a separate CRM/DB table.
  - Routes for general follow-up.

**Outcome:** Faster lead triage, enriched sales intelligence, and structured record-keeping.

<img width="1390" height="658" alt="Smart Lead Capture Pipeline" src="https://github.com/user-attachments/assets/87e91d15-7886-460a-aecf-253d0b1adfc5" />

---

### 3. Technical Support Pipeline
**Trigger:** Secure webhook (POST request with JWT authentication).  
**Process:**
- Validates request and parses payload.
- Queries Pinecone vector DB for relevant documents.
- Uses RAG to draft a support email containing:
  - Ticket details
  - Request summary
  - Relevant documentation
  - Suggested next steps
- Sends to the Technical Support Team.
- Escalates urgent issues via Teams/SMS if needed.

**Outcome:** Support staff receive AI-assisted summaries and relevant resources, enabling faster, more accurate responses.

<img width="1209" height="618" alt="Technical Support Pipeline" src="https://github.com/user-attachments/assets/a31ccd1a-d275-4c4d-bddb-4276ff2cb4fc" />

---

## 🛠️ Tech Stack

- **Automation & Orchestration:** n8n  
- **Vector Database:** Pinecone  
- **Embedding & LLM:** Gemini Embeddings / Gemini LLM  / Cohere
- **Data Sources:** Google Drive, Google Sheets
- **Security:** JWT authentication, audit logging
- **Notifications:** Gmail 

---

## 📜 Disclaimer
This repository is for **demonstration and educational purposes only**.  
It does not contain real patient data or production healthcare integrations.
