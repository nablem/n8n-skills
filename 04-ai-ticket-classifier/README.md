\# AI-Powered Support Ticket Classifier



\## Purpose

Leverages LLM capabilities to automatically classify incoming support tickets by urgency and category, then routes them to appropriate teams based on AI-determined priority.



\## Key Skills Demonstrated



\*\*LLM Integration \& Prompt Engineering\*\*

\- \*\*API Orchestration:\*\* Direct integration with Anthropic's Claude API using structured HTTP requests with proper authentication headers.

\- \*\*Prompt Design:\*\* Crafted explicit instructions to enforce JSON-only responses, ensuring consistent, parseable outputs for downstream automation.

\- \*\*Response Parsing:\*\* Implemented regex-based extraction to handle markdown-wrapped JSON responses and convert them into structured workflow data.



\*\*Intelligent Routing \& Decision Logic\*\*

\- \*\*AI-Driven Triage:\*\* Delegates classification decisions (HIGH/MEDIUM/LOW urgency, TECHNICAL/BILLING/ACCOUNT categories) to Claude rather than hardcoded rules.

\- \*\*Conditional Branching:\*\* Routes HIGH urgency tickets to senior support with Slack+email alerts, while MEDIUM/LOW go to standard queue.

\- \*\*Cross-Node Data Preservation:\*\* Uses `$('node\_name')` syntax to reference upstream data (ticketId, customerEmail) and merge with AI classification results.



\*\*Audit Trail \& Observability\*\*

\- \*\*Structured Logging:\*\* Captures AI reasoning alongside urgency/category in Data Table for quality monitoring and model performance analysis.

\- \*\*Timestamp Tracking:\*\* Records exact classification time to measure SLA compliance and AI response latency.

\- \*\*Action Tracking:\*\* Logs whether tickets were escalated or queued, creating a complete audit trail of automated routing decisions.

