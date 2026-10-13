Internal Controls Matrix — proposed for Fees/Sales systems

Purpose
Define a concise internal controls matrix that demonstrates segregation of duties, approval points, and audit trails required by PFM systems.

Columns: Control ID | Process Area | Control Description | Control Owner | Frequency | Evidence | Risk Mitigated

C-001 | Invoice creation | Only ADMIN role can create official invoices; system records created_by and timestamp | Admin | Per invoice | invoice record with metadata | Unauthorized invoicing

C-002 | Approval for discounts/refunds | All refunds require Accountant approval and an approval record | Accountant | Per refund | Refund request + approval log | Unauthorized refunds

C-003 | Payment posting | Cashier records payments; Accountant reviews daily cash report and posts manual adjustments | Cashier/Accountant | Daily | Daily cash report, receipts | Misposted payments

C-004 | Bank reconciliation | Reconciliation job compares bank imports with payments; Accountant signs off monthly | Accountant | Monthly | reconciliation_report.csv | Bank variance not detected

C-005 | Access control reviews | Quarterly review of role assignments; removal of inactive users | System Owner/IT | Quarterly | access log | Privilege creep

How to evidence controls using the repos
- SMT_SCHOOL: show invoice/payment APIs and audit fields (created_by, timestamps)
- Excledge: show role definitions (SYSTEM_OWNER, ACCOUNTANT) and logging/cron jobs for reconciliation

Acceptance
- Evidence files (audit logs, reconciliation CSVs, approval records) attached in docs/reports when available

