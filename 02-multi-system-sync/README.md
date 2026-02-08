# Multi-System Data Sync with Conflict Resolution

## Purpose
Automates bidirectional synchronization between two disparate systems (e.g., ERP and CRM) while detecting and resolving data discrepancies using a "Newest Wins" logic.

## Key Skills Demonstrated

*\*Advanced Data Reconciliation\*\*

- \*\*Conflict Detection:\*\* Custom JavaScript logic identifies mismatches across specific fields (email, phone, credit limits) between System A and System B.

- \*\*Timestamp-Based Resolution:\*\* Implements a programmatic "Newest Wins" strategy by comparing ISO 8601 `lastModified` dates.

- \*\*Granular Differencing:\*\* Maps exactly which fields changed (e.g., "System B has a different phone number and credit limit") rather than just identifying a general change.

*\*System Integration \& Persistence\*\*

- \*\*Bidirectional Updates:\*\* Orchestrates parallel HTTP PUT requests to ensure both systems remain in parity after resolution.

- \*\*Audit Logging:\*\* Transforms complex resolution objects into structured log entries stored in a centralized Data Table for compliance and monitoring.

- \*\*State Management:\*\* Uses a unique `syncId` and ISO timestamps to create a traceable history of every synchronization event.

*\*Error Handling \& Reliability\*\*

- \*\*Trigger-Based Scheduling:\*\* Configured via Cron expressions (`\*/15 \* \* \* \*`) for consistent, production-grade polling.

- \*\*Graceful Failure:\*\* Utilizes "Continue on Error" for individual system updates to prevent a single API timeout from halting the entire logging process.

- \*\*Failure Notification:\*\* Includes a dedicated "Stop and Error" path to alert administrators if system writes fail after a conflict is resolved.

