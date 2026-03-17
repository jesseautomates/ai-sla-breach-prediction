# AI SLA Breach Prediction Automation

AI-powered support workflow built with **n8n** and **OpenAI** to identify support tickets that are at risk of missing SLA before a breach occurs.

## Overview

Support teams often find out about SLA problems too late — once a ticket is already overdue, escalated, or causing customer frustration. This workflow helps solve that by analyzing ticket data in-flight and predicting which cases are most likely to breach SLA.

The automation reviews ticket context, evaluates breach risk, and flags high-risk tickets for earlier action so support teams can prioritize work more effectively.

## What this workflow does

- Ingests support ticket data
- Evaluates ticket context and urgency
- Uses AI to assess likelihood of SLA breach
- Flags tickets as low / medium / high risk
- Routes or alerts on high-risk cases
- Creates a structured output that can be used in dashboards, queues, or notifications

## Example use case

A support organization receives a high volume of incoming and in-progress tickets. Some look normal at first, but are likely to miss SLA because of urgency, wording, backlog pressure, response lag, or issue complexity.

Instead of waiting for the SLA clock to expire, this workflow identifies risky tickets early and helps operations teams intervene before the breach happens.

## Why this matters

This automation can help support teams:

- Reduce SLA misses
- Prioritize work more intelligently
- Surface risk before escalation
- Improve customer experience
- Create a more proactive support operation

## Workflow logic

1. Ticket data is received by the workflow
2. Relevant ticket fields are normalized and prepared
3. AI analyzes the ticket for SLA breach risk
4. A risk label and rationale are returned
5. The workflow branches based on risk level
6. High-risk tickets can be routed, logged, or alerted on

## Tech stack

- **n8n**
- **OpenAI API**
- Optional data source: help desk, spreadsheet, CSV, or webhook
- Optional outputs: Slack, email, Google Sheets, Airtable, dashboard layer

## Inputs

Typical fields used by the workflow may include:

- Ticket ID
- Created date / last updated date
- Priority
- Category
- Customer sentiment or wording
- Current status
- Time remaining to SLA
- Assigned queue or owner
- Historical indicators if available

## Outputs

The workflow can return structured fields such as:

- Ticket ID
- SLA breach risk
- Confidence / reasoning
- Suggested next action
- Priority signal
- Queue recommendation

## Business impact

This project demonstrates how AI can move support operations from reactive reporting to proactive intervention.

Potential value includes:

- Better queue prioritization
- Lower breach volume
- Faster operational response
- Stronger SLA performance visibility
- More scalable support triage processes

## Files included

- n8n workflow export
- architecture / workflow screenshots
- sample ticket data
- setup notes
- project documentation

## Setup

1. Import the workflow JSON into n8n
2. Add your API credentials and environment variables
3. Connect your chosen ticket input source
4. Configure your output destination
5. Run test data through the workflow
6. Review and tune prompts or thresholds as needed

## Notes

This project is designed as a portfolio example for **Support Operations Automation** and **AI-enabled service workflows**. It can be adapted for multiple help desk environments and expanded with additional scoring, prioritization, or reporting logic.

## Author

**Jesse Snow**  
Support Operations | Automation | AI Workflow Design  
[LinkedIn](https://linkedin.com/in/jesse-snow)
