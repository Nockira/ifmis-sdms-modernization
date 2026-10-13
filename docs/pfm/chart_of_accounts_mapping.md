Chart of Accounts (COA) mapping — example and guidance

Purpose
Provide an example COA design and mapping document that links transactional application items (invoices, sales, fees) to government COA codes used by IFMIS.

A. Example COA structure (simplified)
- 1- Revenue
  - 10- Tuition Fees (COA 1001)
  - 11- Examination Fees (COA 1002)
  - 12- Other School Income (COA 1099)
- 2- Receivables
  - 20- Student Receivables (COA 2001)
- 3- Assets
  - 30- Cash at Bank (COA 3001)
- 4- Liabilities
  - 40- Deferred Income (COA 4001)

B. Mapping examples (application field -> COA)
- Smart School
  - invoice.type = "tuition" -> COA 1001
  - payment.method = "cash" -> cash posting to COA 3001
  - invoice.status = "unpaid" -> receivable account COA 2001
  - Refunds -> debit revenue; credit bank/cash; reversal journal with original invoice ref

- Excledge
  - sale.item_class = "pharmacy_sale" -> COA 1101 (Pharmacy Sales)
  - subscription_revenue -> COA 1201
  - payment_gateway_fees -> expense COA 5002 (if tracked)

C. Deliverables and files
- COA_MAPPING.csv (headers: app_entity, app_field, mapping_rule, coa_code, coa_description)
- Sample mapping (included in this repo as chart_of_accounts_mapping.csv)

D. How to demonstrate contribution
- Point to transaction tables and examples in each repo and include a sample SQL join used to compute COA totals (see reconciliation_procedures.md)

E. Acceptance criteria
- Each revenue/invoice type has a unique COA mapping
- Mapping reviewed and signed off by finance stakeholder (template for sign-off in docs/reports)

