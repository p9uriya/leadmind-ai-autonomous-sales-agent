# leadmind-ai-autonomous-sales-agent
autonomous-ai-sales-agent-n8n multi-agent-lead-generation-system ai-sales-automation-n8n leadmind-ai
# LeadMind AI 🚀

## Autonomous Multi-Agent Sales Automation System

LeadMind AI is an autonomous AI-powered sales automation system designed to automate the lead research, qualification, customer conversation, and meeting scheduling workflow.

Built using a multi-agent architecture, the system combines AI agents, workflow automation, search intelligence, CRM storage, and conversational interfaces.

---

## Features

### 🔍 Autonomous Lead Research

The AI Research Agent generates targeted search queries based on an Ideal Customer Profile (ICP) and searches for relevant companies across the web.

Workflow:

AI Research Planner → Search API → Company Discovery → Deduplication → Website Analysis

---

### 🧠 Company Intelligence

Each discovered company is analyzed by an AI agent.

The system extracts and evaluates:

* Company name
* Website
* Industry
* Estimated company size
* Services
* Potential pain points
* ICP compatibility
* AI confidence score

---

### 🎯 AI Lead Scoring

LeadMind combines rule-based scoring with AI intelligence to classify potential customers.

Lead categories:

* 🔥 HOT Lead
* 🟡 WARM Lead
* ❄️ COLD Lead

Qualified leads are automatically stored in the CRM database.

---

### 💬 AI Sales Agent

The Sales Conversation Agent communicates with users through Bale Bot.

The AI can:

* Answer product questions
* Detect customer intent
* Identify objections
* Analyze sentiment
* Detect meeting readiness
* Route complex requests to human support

---

### 📅 Automated Meeting Scheduling

When a potential customer is ready for a meeting:

1. The AI detects meeting intent.
2. The workflow checks calendar availability.
3. Available meeting slots are generated.
4. The user receives available options.
5. The selected meeting can be scheduled automatically.

Google Calendar integration is used for scheduling.

---

### 🧠 Conversation Memory

LeadMind supports persistent conversation history using PostgreSQL.

Each user receives a unique session identity:

```text
bale_user_id
```

This allows the AI system to maintain contextual conversations.

---

## Architecture

```text
                        BALE BOT
                           │
                           ▼
                    BALE WEBHOOK API
                           │
                           ▼
                    INPUT NORMALIZATION
                           │
                           ▼
                    INTENT CLASSIFIER
                           │
                           ▼
                    MASTER ROUTER
                           │
          ┌────────────────┼────────────────┐
          │                │                │
          ▼                ▼                ▼
     LEAD RESEARCH      SALES AI       MEETING AGENT
          │                │                │
          ▼                ▼                ▼
      SERPAPI          OPENAI         GOOGLE CALENDAR
          │                │                │
          ▼                ▼                ▼
  COMPANY ANALYSIS   CONVERSATION     MEETING SLOTS
          │              MEMORY
          ▼                │
      LEAD SCORING         │
          │                │
          └────────┬───────┘
                   ▼
              POSTGRESQL
                   │
                   ▼
             CRM / ANALYTICS
```

---

## Technology Stack

* n8n
* OpenAI API
* Bale Bot API
* PostgreSQL
* Google Calendar API
* SerpAPI
* REST APIs
* JavaScript

---

## Workflow Components

The system includes:

* Bale Webhook
* Input Validation
* Intent Classification
* AI Research Planning
* Search Query Generation
* SerpAPI Integration
* Search Rate Limiting
* URL Deduplication
* Website Analysis
* Company Intelligence Agent
* AI Lead Scoring
* CRM Storage
* Outreach Draft Generation
* Human Approval Queue
* AI Sales Agent
* Conversation Memory
* Meeting Detection
* Google Calendar Integration
* Automated Meeting Slot Generation
* Error Handling
* Execution Logging

---

## Environment Variables

Configure the following environment variables:

```env
OPENAI_API_KEY=your_openai_api_key

BALE_SEND_MESSAGE_URL=your_bale_api_endpoint
BALE_BOT_TOKEN=your_bale_bot_token

SEARCH_API_URL=https://serpapi.com/search.json
SEARCH_API_KEY=your_serpapi_key

ADMIN_ALERT_WEBHOOK_URL=your_alert_webhook
```

---

## Required Credentials

Configure the following credentials inside n8n:

* OpenAI API
* PostgreSQL
* Google Calendar OAuth2

---

## Database Schema

The workflow automatically works with the following tables:

### leads

Stores qualified companies and lead scores.

### conversations

Stores user conversations for memory and context.

### approval_queue

Stores AI-generated outreach drafts awaiting human approval.

### agent_logs

Stores workflow execution logs.

---

## Commands

Example commands for Bale Bot:

```text
/lead B2B SaaS companies in Germany
```

```text
/status
```

Users can also communicate naturally with the AI Sales Agent.

---

## Security

Never store API keys or tokens directly inside workflow files.

Use:

* n8n Credentials
* Environment Variables
* Secret Management

Before publishing the project, remove all production credentials.

---

## Roadmap

* [ ] Redis memory layer
* [ ] Advanced CRM dashboard
* [ ] Automated follow-up sequences
* [ ] Email integration
* [ ] WhatsApp integration
* [ ] Telegram integration
* [ ] Human-in-the-loop approval dashboard
* [ ] Advanced analytics
* [ ] Multi-language sales agents
* [ ] Google Meet automatic conference generation

---

## Project Goal

The goal of LeadMind AI is to demonstrate how modern AI agents and workflow automation can be combined to create an adaptive sales automation system.

Instead of building a simple chatbot, LeadMind AI uses multiple specialized components responsible for:

Research → Intelligence → Qualification → Conversation → Scheduling → Analytics

---

## Author

Built as an AI Automation and Multi-Agent Systems project.

---

## License

MIT License
