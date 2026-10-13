Reconciliation procedures — example scripts and pseudocode

Purpose
Provide reproducible steps and example SQL/pseudocode to reconcile payments to invoices and to generate reports suitable for IFMIS ingestion.

1. Reconcile payments to invoices (simplified SQL)

-- Pseudocode SQL
-- Assumes tables: invoices(id, invoice_no, total_amount), payments(id, invoice_id, amount, payment_ref, status)

SELECT i.invoice_no, i.total_amount, COALESCE(SUM(p.amount),0) AS paid_amount, i.total_amount - COALESCE(SUM(p.amount),0) AS variance
FROM invoices i
LEFT JOIN payments p ON p.invoice_id = i.id AND p.status='posted'
WHERE i.issue_date BETWEEN '2026-09-01' AND '2026-09-30'
GROUP BY i.id
HAVING ABS(i.total_amount - COALESCE(SUM(p.amount),0)) > 0.01;

- Output: list of invoices with unmatched amounts; actions: investigate payment_ref and bank statement

2. Reconcile bank statement (CSV) to payments (pseudocode)
- Import bank CSV into staging table bank_txns(txn_date, amount, description, ref)
- Run match by payment_ref and amount
- Flag unmatched bank_txns and unmatched payments

3. Automating reconciliation
- Use Excledge cron job patterns (Postman + backend automation) to schedule daily runs and produce reconciliation_report.csv

4. Evidence in repositories
- Excledge: Postman collection and cron job descriptions under Backend/README.md and Postman/README.md
- SMT_SCHOOL: backend endpoints for payments and receipts referenced under smart-school-bn/README.md

5. Acceptance criteria
- All payments within reporting period are either matched to an invoice or classified as unidentified cash with a follow-up ticket
- Reconciliation log retained for audit (30+ years per policy where required)

