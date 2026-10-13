Financial statements and reporting deliverables — prepared by Nockira

Purpose
Provide example financial statements and report definitions derived from the Smart School and Excledge projects and translate them into formats and outputs that map to IFMIS/SDMS reporting needs.

1. Suggested statement types and templates
- Daily Cash Receipt Report (Cashiering)
  - Purpose: daily summary of cash and electronic payments collected per entity (school or pharmacy)
  - Fields: date, entity_id, total_cash, total_bank_transfers, total_card, total_refunds, net_collected, currency
  - Source: Smart School invoices/payments API; Excledge fiscal sales endpoints (see Postman/Excledge-API-Collection)

- Monthly Revenue Summary (per Entity and consolidated)
  - Purpose: monthly revenue by revenue code (map to chart of accounts)
  - Fields: month, entity_id, revenue_coa_code, amount, transaction_count
  - Source: Excledge sales exports, Smart School fees ledger

- Trial Balance (system-generated for a period)
  - Purpose: reconciliation of system GL-like balances (income, receivables, reversals)
  - Fields: coa_code, account_name, opening_balance, debits, credits, closing_balance
  - Generation: export journal lines from application transactional tables and aggregate by COA mapping file

- Receipts Journal / Cash Book
  - Purpose: sequenced receipt records for audit and RRA/IFMIS submission
  - Fields: receipt_no, date, payer, amount, payment_method, txn_ref, coa_code, linked_invoice

2. Example report formats (CSV/Excel/JSON)
- Provide templates as CSV headers to be exported by application and consumed by IFMIS importers.

3. How to link to the source repos
- SMT_SCHOOL: backend API docs (smart-school-bn/README.md) indicate endpoints for receipts and ledger operations — use those endpoints to extract transaction-level data.
  - Repo: https://github.com/niyobertin/SMT_SCHOOL
  - Suggested path: /smart-school-bn (backend endpoints and swagger)

- Excledge: explicit OpenAPI/Postman collections with fiscal sales endpoints and reporting endpoints.
  - Repo: https://github.com/TangaHubService/Excledge
  - Suggested path: /Backend + /Postman

4. Acceptance criteria for reports
- Data completeness: all transactions within period included
- Mapping correctness: each transaction mapped to a valid COA code
- Format validity: CSV/JSON schema validated against IFMIS import spec
- Reconciliation: totals must match receipts journal and bank statements (if available)

5. Deliverables to include in submission
- Report templates (CSV headers) — included as annexes
- Sample exported JSON (anonymized) — derived from API responses
- Short script or SQL to aggregate transactions into report format (pseudocode provided in reconciliation_procedures.md)

