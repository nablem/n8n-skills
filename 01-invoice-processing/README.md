# Invoice Processing & Validation Pipeline



## Purpose

An automated gateway for incoming financial data that enforces strict validation rules, routes invoices based on fiscal priority, and ensures 100% auditability through comprehensive error handling.



## Key Skills Demonstrated



**Rigorous Data Validation**

- **Schema Enforcement:** Validates the presence of mandatory ERP fields including `invoiceNumber`, `customerName`, and `totalAmount`.

- **Regex & Format Verification:** Ensures data integrity at the entry point using Regex for date formats (YYYY-MM-DD) and currency strings.

- **Cross-Field Logic:** Implements mathematical verification to ensure the sum of individual line items matches the declared total before allowing ingestion.

- **Error Accumulation:** Designed to collect and report all validation failures simultaneously rather than terminating on the first error.



**Resilient Error Management**

- **Fault-Tolerant Routing:** Utilizes "Continue on Error" paths to ensure that invalid data is logged and investigated without crashing the core service.

- **Automated Retries:** Includes exponential backoff/retry logic (3 attempts at 2-second intervals) to handle transient network issues or API rate limits.

- **Contextual Logging:** Parallelizes error reporting to both an external HTTP service and an internal Data Table, enriching logs with specific invoice metadata for faster debugging.



**Intelligent Business Routing**

- **Priority Tiering:** Automatically flags and routes high-value transactions (≥$1000) through a dedicated approval path.

- **Status Segmentation:** Dynamically separates valid datasets from "quarantined" records, ensuring only clean data reaches the downstream accounting systems.


## Test Input

```json
{
    "invoiceNumber": "INV-001", 
    "date": "2024-02-07",
    "customerName": "Acme Corp",
    "items": [
        { 
            "description": "Service A", 
            "amount": 1000
        },
        {
            "description": "Service B", 
            "amount": 500
        }
    ], 
    "totalAmount": 1500
}
```

