# AI SLA Breach Prediction Automation

AI-powered support workflow built with **n8n** and **OpenAI** to proactively identify support tickets at risk of missing SLA before a breach occurs.

---

## Overview

Most support teams only react to SLA breaches after they happen — when it’s already too late.  

This project extends a multi-stage AI support pipeline to **predict SLA risk in advance**, enabling teams to prioritize work more effectively and intervene before deadlines are missed.

This is **Project 3** in a broader system:

- Project 1 → AI Ticket Triage  
- Project 2 → Escalation Risk Detection  
- Project 3 → SLA Breach Prediction (this project)

---

## AI Support Automation Series

This project is part of a multi-stage AI-powered support operations system designed to move teams from reactive workflows to proactive, intelligence-driven operations.

Each project builds on the previous one:

### 🔹 Project 1: AI Ticket Triage  
Classifies incoming support tickets, enriches them with structured metadata, and establishes a clean foundation for downstream automation.  
👉 https://github.com/jesseautomates/ai-support-ticket-triage

---

### 🔹 Project 2: Escalation Risk Detection  
Identifies tickets likely to escalate by analyzing urgency, sentiment, and response patterns, enabling earlier intervention.  
👉 https://github.com/jesseautomates/ai-support-escalation-risk-detection

---

### 🔹 Project 3: SLA Breach Prediction *(this project)*  
Predicts which tickets are at risk of missing SLA before deadlines are breached, allowing teams to prioritize and act proactively.

---

Together, these projects form a layered AI pipeline:

**Triage → Risk Detection → Predictive SLA Intervention**

This progression demonstrates how AI can be applied incrementally to transform support operations at scale.
## What this workflow does

- Ingests support ticket data
- Leverages prior AI enrichment (triage + escalation signals)
- Predicts SLA breach likelihood using AI
- Classifies tickets as **Low / Medium / High risk**
- Routes or flags tickets based on risk level
- Logs structured outputs for reporting and analysis

---

## How it works

### 1. Data Intake & Normalization
- Receives ticket data from source (API, CSV, webhook)
- Cleans and standardizes key fields:
  - Priority
  - Status
  - Queue
  - Time remaining to SLA
  - Customer message

---

### 2. AI Ticket Enrichment (Project 1)
- Classifies ticket type and intent
- Assigns structured metadata
- Generates initial priority signals

---

### 3. Escalation Risk Detection (Project 2)
- Evaluates likelihood of escalation
- Analyzes:
  - Urgency
  - Sentiment
  - Delays / response gaps
- Outputs escalation risk label

---

### 4. SLA Context Building
- Combines:
  - Ticket data
  - Triage output
  - Escalation risk signal

- Calculates:
  - Time remaining to SLA
  - Backlog pressure
  - Response gaps

---

### 5. Predictive SLA Risk Modeling (AI)
- Predicts likelihood of SLA breach **before deadline**
- Evaluates:
  - Time remaining to SLA
  - Urgency & sentiment
  - Ticket aging trends
  - Queue backlog conditions

- Returns:
  - Risk level (Low / Medium / High)
  - Reasoning

---

### 6. Decision & Action Layer

| Risk Level | Action |
|-----------|--------|
| High | Route to priority queue + trigger alert |
| Medium | Flag for monitoring + prioritized review |
| Low | Continue standard workflow |

---

### 7. Reporting & Logging

- Stores prediction results
- Enables dashboarding / reporting
- Captures:
  - Ticket ID
  - Escalation risk
  - SLA risk
  - Reasoning
- Supports trend analysis over time

---

## Example Output

| Ticket ID | Escalation Risk | SLA Risk | Reason |
|----------|----------------|----------|--------|
| 10428 | High | High | Urgent language + low time remaining |
| 10429 | Medium | Medium | Moderate backlog and delayed response |
| 10430 | Low | Low | Sufficient SLA buffer |

---

## Architecture

This project is part of a layered AI support pipeline:

1. **Triage Layer** → structures and enriches tickets  
2. **Escalation Layer** → detects risk signals  
3. **SLA Layer (this project)** → predicts deadline failure  

Together, they enable a shift from **reactive support → proactive operations**

---

## Tech Stack

- **n8n** (workflow orchestration)
- **OpenAI API** (AI classification + prediction)
- Optional integrations:
  - Google Sheets
  - Slack / Email
  - Help desk platforms

---

## Setup

1. Import the workflow JSON into n8n
2. Add API credentials (OpenAI, etc.)
3. Configure your ticket input source
4. Set up output destination (alerts / logging)
5. Run test data through the workflow
6. Tune prompts and thresholds as needed

---
