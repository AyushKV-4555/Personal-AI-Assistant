# 🧠 AI-Powered Personal Executive Assistant (n8n)

An **AI-driven personal executive assistant** built using **n8n + LangChain**, capable of understanding natural language requests and safely executing actions across multiple productivity tools such as **Calendar, Email, Tasks, Notes, Weather, Search, Expenses, and Calculations**.

The system follows **agentic AI principles** with **tool orchestration**, **stateful memory**, and **human-in-the-loop (HITL) safety controls**.

---

## ✨ Key Features

- Natural language interface via Webhook (API-first design)
- LLM-powered intent detection and tool selection
- Multi-tool orchestration within a single agent
- Human-in-the-Loop (HITL) safeguards for destructive actions
- Stateful memory for contextual conversations
- Minimal, executive-style responses

---

## 🧩 Supported Capabilities

### 📅 Calendar Management
- Create calendar events  
- Retrieve one or multiple events  
- Delete events *(confirmation required)*  

### 📧 Email (Gmail)
- Send emails  
- Read recent emails  

### ✅ Task Management
- Create tasks  
- List tasks  
- Delete completed tasks *(confirmation required)*  

### 📝 Notes & Documents
- Create Google Docs  
- Append content without overwriting  
- Read existing documents  

### 💰 Expense Tracking
- Log expenses into Google Sheets  
- Retrieve expense records  
- Perform calculations on expense data  

### 🌦 Weather Information
- Fetch real-time weather by city  
- Returns temperature, conditions, and visibility  

### 🔍 Search & Information
- Web search for facts, news, and general queries  
- Concise summarized answers  

### ➗ Calculator
- Accurate numeric calculations  
- Returns final value only  

---

Client (User Request)
↓
Webhook Trigger (n8n)
↓
AI Agent (LangChain)
├── Intent Detection
├── Tool Selection
├── Input Validation
├── Safety Rules
↓
Tool Execution (External APIs)
↓
Response Formatter
↓
Webhook Response

## 🔐 Safety & Control Mechanisms

- Confirmation required for:
  - Deleting calendar events
  - Deleting tasks
  - Overwrite operations
- No assumptions without explicit user approval
- Structured tool-calling prompts
- Centralized state management



## ⚙️ Tech Stack

- **Workflow Automation:** n8n  
- **LLM Orchestration:** LangChain Agent  
- **Language Model:** LLaMA 3.1 (via Groq)  
- **APIs Integrated:**
  - Google Calendar
  - Gmail
  - Google Tasks
  - Google Docs
  - Google Sheets
  - OpenWeatherMap
  - SerpAPI
- **Memory:** Buffer Window Memory  
- **Interface:** Webhook-based REST API  

---

## 🚀 How to Use

1. Import the workflow JSON into n8n  
2. Configure API credentials (Google, Weather, SerpAPI, Groq)  
3. Activate the workflow  
4. Send a POST request to the webhook:

```json
{
  "message": "Schedule a meeting tomorrow at 10 AM"
}

## 🏗 Architecture Overview
