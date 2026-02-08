\# n8n ERP Integration Workflows



\## Overview



Three n8n workflows demonstrating skills relevant to ERP integration work:

\- Data validation and transformation

\- Error handling with retry logic

\- API integration and conflict resolution

\- Scheduled automation and reporting

\- Audit logging



\## Workflows



\### 1. Invoice Processing \& Validation Pipeline

\*\*Purpose:\*\* Validate incoming invoices, route by priority, log errors

\*\*Skills:\*\* Data validation, conditional routing, parallel execution, error handling

\[View Workflow](./01-invoice-processing/)



\### 2. Multi-System Data Sync with Conflict Resolution

\*\*Purpose:\*\* Sync customer data between systems, detect and resolve conflicts

\*\*Skills:\*\* Data comparison, merge strategies, API orchestration, audit logging

\[View Workflow](./02-multi-system-sync/)



\### 3. Scheduled Report Aggregator

\*\*Purpose:\*\* Daily sales reporting with threshold-based notifications

\*\*Skills:\*\* Scheduled automation, data aggregation, conditional logic

\[View Workflow](./03-report-aggregator/)



\### 4. AI-Powered Support Ticket Classifier

\*\*Purpose:\*\* Automatically classify and route support tickets using LLM

\*\*Skills:\*\* LLM integration, prompt engineering, intelligent routing, API orchestration

\[View Workflow](./04-ai-ticket-classifier/)



\## How to Use



1\. Import JSON files into your n8n instance

2\. Review the individual workflow READMEs for test payloads

3\. Configure Data Tables if needed



\## Tech Stack



\- n8n (self-hosted via Ansible)

\- JavaScript (Code nodes)

\- HTTP Request nodes

\- Anthropic Claude API

\- Data Tables for persistence

\- Webhook and Schedule triggers

