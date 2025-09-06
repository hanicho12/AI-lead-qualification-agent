# 🤖 AI Lead Qualification Agent

An **AI-powered automation workflow** built with [n8n](https://n8n.io), Google Gemini, Google Sheets, Gmail, and Discord.  
This project acts as a **24/7 AI sales assistant** that receives new leads, analyzes them with AI, and routes them to the right actions automatically.

---

## 📌 Project Overview
The **AI Lead Qualification Agent** simulates how a creative agency could automatically qualify incoming leads.  

- **Trigger (Perceive):** A lead submits a Contact Us form → webhook receives data.  
- **Reasoning (AI):** Google Gemini analyzes the lead (project details + budget) and returns structured JSON:
  - `summary`  
  - `serviceCategory`  
  - `qualificationScore` (1–10)  
  - `priority` (High, Medium, Low)  
  - `suggestedResponse` (draft email)  
- **Actions (Act):** Based on the priority:  
  - **High Priority:** Add to Google Sheets (CRM) + send Discord alert + send personalized Gmail.  
  - **Medium Priority:** Add to Google Sheets + send Gmail follow-up.  
  - **Low Priority:** Send polite rejection/redirect email.  

This demonstrates **prompt engineering, workflow orchestration, and multi-service integration**.

---

## ⚙️ Workflow Architecture
```text
Contact Form (HTML) 
   ↓
Webhook (n8n Trigger) 
   ↓
Google Gemini (AI Analysis) 
   ↓
Code Node (Parse & Clean JSON) 
   ↓
Switch (Priority Routing) 
   ├─ High → Google Sheets + Discord + Gmail
   ├─ Medium → Google Sheets + Gmail
   └─ Low → Gmail only


🛠️ Tech Stack

n8n (workflow automation)

Google Gemini (AI reasoning)

Google Sheets (CRM storage)

Gmail (automated email responses)

Discord (team notifications)

HTML/CSS/JS (Contact Us form)


📄 Files in This Repo
ai-lead-qualification-agent/
│── README.md                # Project overview & case study
│── workflow.json             # Exported n8n workflow
│── llm-prompt.txt             # Final AI prompt for Gemini
│── contact-form/             # Example frontend form
│    └── index.html
│    └── style.css
│── sample-payload.json      # Example JSON test payload
│── loom-video-links.txt/              # Workflow & live results video walkthtough




📂 How to Run This Project

Import workflow.json into your n8n instance.

Update API keys (Google Gemini, Gmail, Sheets, Discord).

Deploy the Contact Us form and update webhook URL.

Send test payloads to the webhook.

Observe AI analysis + actions in Sheets, Discord, and Gmail.



👤 Author: Hana Wubet# AI-Lead-Qualification-Agent
