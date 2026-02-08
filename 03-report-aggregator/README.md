# Scheduled Report Aggregator & KPI Monitor



## Purpose

Aggregates regional sales data from multiple sources, calculates global performance metrics, and implements "Alert by Exception" logic to trigger reports only when performance fluctuates beyond defined thresholds.



## Key Skills Demonstrated



**Data Aggregation & Transformation**

- **Multi-Source Merging:** Consolidates disparate data streams (Region A, B, and C) into a single unified dataset using Merge nodes.

- **Complex Analytics via Code:** Utilizes custom JavaScript to calculate Total Revenue, Average Order Value (AOV), and target variance percentages.

- **Performance Benchmarking:** Programmatically identifies "Best" and "Worst" performing regions to provide immediate executive context.



**Conditional Governance (Alert by Exception)**

- **Threshold Logic:** Implements an automated "Go/No-Go" decision point using a custom variance check (e.g., alert if performance is < -5% or > 10% vs. target).

- **Resource Optimization:** Reduces system noise and API overhead by skipping standard reports and only escalating "out-of-bounds" data.



**Process Audit & Logging**

- **Unified Execution Logging:** Employs a merge-and-map strategy to capture both "Sent" and "Skipped" statuses in a centralized Data Table.

- **Structured Metadata:** Generates unique execution IDs and timestamps for every run to ensure a complete audit trail of automated decision-making.

- **Automated Scheduling:** Governed by production-ready Cron expressions (`0 9 * * *`) for reliable daily reporting.

