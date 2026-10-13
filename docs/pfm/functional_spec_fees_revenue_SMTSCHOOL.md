Functional Specification: Fees & Revenue Module (Smart School) — prepared by Nockira

Project: Smart School — Fees & Revenue Module
Source evidence: https://github.com/niyobertin/SMT_SCHOOL (smart-school-bn backend docs)

1. Overview
Provide an implementation-ready functional spec that describes the Fees module, API endpoints, data model, business rules, and acceptance criteria.

2. Use cases
- UC-001: Create Invoice
  - Actor: School Admin
  - Description: Create invoice for student fees, with lines mapped to COA codes
  - Input: student_id, items[{code, amount}], due_date
  - Output: invoice_id, invoice_no, total_amount
  - Acceptance: invoice stored, COA mapping applied, notification sent

- UC-002: Record Payment
  - Actor: Cashier / Parent
  - Description: Record payment (cash/gateway), generate receipt, post journal
  - Input: invoice_id, payment_method, amount, payment_ref
  - Output: receipt_id, journal_entry_id
  - Acceptance: receipt created, invoice status updated, journal created with debit/credit

3. API Endpoints (examples)
- POST /api/fees/invoices — create invoice
- GET /api/fees/invoices/{id} — fetch invoice
- POST /api/fees/invoices/{id}/payments — record payment
- GET /api/fees/reports/monthly-revenue — export report

4. Data model (key entities)
- Invoice: id, invoice_no, student_id, issue_date, due_date, total_amount, status
- InvoiceLine: id, invoice_id, description, amount, coa_code
- Payment: id, invoice_id, date, amount, method, txn_ref, receipt_no
- JournalEntry: id, date, lines[{coa_code, debit, credit}], source_ref

5. Business Rules
- Partial payments allowed; invoice status updates when sum(payments) >= total_amount
- Late fees calculation rule: after due_date + 7 days charge X%
- Refunds reversed with linked reference to original receipt

6. Security & Access
- Roles: ADMIN, CASHIER, ACCOUNTANT, TEACHER, PARENT
- Only ACCOUNTANT can post manual journals; CASHIER can record payments

7. Acceptance Criteria & Tests (Given/When/Then)
- Given an unpaid invoice, when a payment equal to invoice total is recorded, then invoice status = PAID and corresponding journal exists

8. Attachments & references
- Reference backend README indicating Swagger in SMT_SCHOOL: /smart-school-bn/README.md

