Expenditure and Revenue Workflows — process flows and user stories

Purpose
Define typical expenditure and revenue workflows and provide user stories and acceptance criteria that can be used to generate functional specs and UAT scripts for IFMIS/SDMS modernization.

1. Revenue workflow (example: Smart School fees)
- Actors: School Admin, Accountant, Parent/Payer
- User story: As a School Admin I want to create an invoice for student fees so that the student can pay online or in cash.
- Main flow:
  1. Admin creates invoice in system (invoice_no generated)
  2. System maps invoice lines to COA codes
  3. Parent receives invoice via portal/email
  4. Parent pays online (gateway) or at cashier (cash)
  5. Payment recorded and receipt issued (receipt_no)
  6. Payment triggers journal entry: debit Cash/Bank (COA 3001), credit Revenue (COA 1001)
  7. Reconciliation job marks bank transfers as matched when bank statement import matches payment_ref

2. Expenditure workflow (example: school procurement)
- Actors: Requestor, Procurement Officer, Approver, Accountant
- User story: As a Requestor I want to submit a purchase request so that needed items are procured.
- Main flow:
  1. Requestor submits PR with estimated cost
  2. Procurement Officer obtains quotations and selects vendor
  3. Approver approves PR and raises PO
  4. Goods received note (GRN) created on receipt
  5. Supplier invoice submitted and matched to PO/GRN
  6. Accountant posts invoice to system and schedules payment
  7. Payment executed and bank transaction reconciled

3. Acceptance criteria & controls
- Segregation: Requestor cannot approve own PRs; approvals must be at least one level higher
- Matching: Invoice must match PO and GRN for payment to proceed
- Audit trail: All actions logged with user_id and timestamp

4. Mapping to repositories
- Use Excledge endpoints for purchase/sales flows as reference for PO/GRN/invoice lifecycle
- Use Smart School invoice/payment flows for revenue lifecycle

