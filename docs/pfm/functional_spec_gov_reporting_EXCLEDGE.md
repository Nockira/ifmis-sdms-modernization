Functional Specification: Government Reporting & Fiscal Sales (Excledge) — prepared by Nockira

Project: Excledge — Government Reporting Module
Source evidence: https://github.com/TangaHubService/Excledge (Backend and Postman docs)

1. Overview
Define functional requirements to extract fiscal sales and produce government-ready reports (daily fiscal sales, electronic journal, payment reconciliation) using Excledge APIs and mapping to IFMIS/SDMS formats.

2. Use cases
- UC-101: Export Daily Fiscal Sales
  - Actor: Accountant / System Owner
  - Description: Export all fiscal sales for date range in CSV/JSON matching government schema
  - Input: start_date, end_date, org_id
  - Output: daily_sales.csv with fields: date, branch, sales_total, tax_total, fiscal_device_receipts

- UC-102: Reconcile Payments to Bank Statement
  - Actor: Accountant
  - Description: Match payment records (gateway/bank) to system receipts and flag mismatches
  - Input: bank_statement.csv, date_range
  - Output: reconciliation_report.csv (matched, unmatched, variance)

3. API Endpoints & Collections
- Use Excledge Postman collections (Postman/Excledge-API-Collection.json) and backend routes under /api/sales, /api/reports
- Example endpoints:
  - GET /api/reports/daily-fiscal-sales?date=YYYY-MM-DD
  - GET /api/sales/{id} — sale details including fiscal receipt data

4. Data mapping & COA
- Map sale types to COA codes (see chart_of_accounts_mapping.md)
- Provide mapping table and transformation rules for export

5. Business Rules
- Fiscal receipts must include device_id and sequential receipt_no
- Void/cancelled receipts must be included with negative amounts and reversal markers

6. Acceptance Criteria
- Exported daily totals equal sum(sale.amount) across returned records
- Each exported record contains a valid COA code
- Postman collection runs produce zero failing tests for critical endpoints

7. Attachments
- Reference: Postman/README.md and Backend/README.md in the Excledge repo

