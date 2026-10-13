# Dossier: SMT_SCHOOL (niyobertin/SMT_SCHOOL) and Excledge (TangaHubService/Excledge)

Prepared for: Business Analyst application — IFMIS & SDMS Modernization (MINECOFIN)
Repository evidence and mapping to the Terms of Reference (TOR)

Links
- SMT_SCHOOL: https://github.com/niyobertin/SMT_SCHOOL
- Excledge: https://github.com/TangaHubService/Excledge

Executive summary
This dossier summarizes findings from the two public repositories above and translates their technical and functional evidence into a consolidated package that meets the MINECOFIN TOR evaluation requirements. Both repositories show practical, production-oriented systems built with modern stacks (TypeScript, Node/Express, React, Prisma/Postgres) and include documentation, API specifications, and modular backends suitable as portfolio evidence for a Business Analyst role focused on PFM modernization.

Repository metadata (quick)
- niyobertin/SMT_SCHOOL
  - Repo ID: 1041699322
  - Visibility: public
  - Default branch: dev
  - Language: TypeScript
  - Homepage: https://smt-school.vercel.app
  - Notable files: README.md, smart-school-bn/README.md (backend), smart-school-fn/README.md (frontend)

- TangaHubService/Excledge
  - Repo ID: 1197220403
  - Visibility: public
  - Default branch: main
  - Language: TypeScript
  - Notable files: README.md (overview), Backend/README.md, Postman/README.md, OpenAPI and Postman collections indicated

How these repos meet the TOR evaluation criteria (practical evidence mapping)
The TOR evaluation includes three main score areas: academic & certifications (40), certificate of good completion (20), and practical repositories/evidence (40). This dossier focuses on maximizing the 40 marks for practical work by mapping repo artifacts to the TOR’s required deliverables.

A. Demonstrated practical and professional work through shared repositories (40 marks)
Map repository artifacts to the specific PFM-relevant deliverables requested by TOR (design of financial statements, chart of accounts, budgeting and accounting processes, expenditure and revenue workflows, functional specifications, internal controls, reconciliation procedures):

1) SMT_SCHOOL — potential evidence items
- Business processes & workflows: The repo contains modular backend and frontend components and README descriptions for API endpoints and system structure (smart-school-bn/README.md, smart-school-fn/README.md). These can support PFM-related workflows such as student fees, invoicing, and reporting.
- API & documentation: Backend README indicates Swagger/auto-generated docs — useful as evidence of documented API surfaces that can be adapted to payment and reporting integrations with IFMIS.
- Architecture & implementation: Express + TypeScript backend shows best-practice layered architecture, security middleware, logging, and environment configuration — evidence of secure, maintainable systems.
- Suggested artifacts to add for TOR alignment:
  - A functional specification for Fees & Revenue module showing: chart of accounts mapping, invoice lifecycle, payment reconciliation, and reporting outputs to Government formats (CSV/JSON/OpenAPI).
  - Sample acceptance tests / UAT scripts for fee collection, refunds, and reporting.
  - A short case study document connecting student finance workflows to PFM concepts (revenue recognition, internal controls, reconciliation).

Relevant files (examples to reference/cite):
- https://github.com/niyobertin/SMT_SCHOOL (root README)
- https://github.com/niyobertin/SMT_SCHOOL/tree/dev/smart-school-bn (backend README)
- https://smt-school.vercel.app (deployed demo)

2) Excledge — potential evidence items
- Rich API & enterprise features: Backend README and Postman docs show an extensive API (~280 routes), multi-tenant support, role-based access control, subscription/payment integration (DPO Pay), cron jobs for alerts, and a detailed Postman/OpenAPI collection. These map directly to PFM-relevant functional areas: revenue capture, payment processing, reporting, and automated reconciliation jobs.
- Reporting & integrations: The documented OpenAPI endpoints and Postman collections provide clear evidence of integration readiness and traceable REST APIs that could be extended to report to IFMIS or to produce standardized accounting outputs.
- Internal control & roles: The repo documents SYSTEM_OWNER, ADMIN, MANAGER, ACCOUNTANT roles and uses JWT and audit-friendly patterns — evidence of segregation of duties and access control.
- Suggested artifacts to add for TOR alignment:
  - A functional spec for a "Government Reporting" binder: endpoints that export fiscal sales, daily reports, and chart-of-account mappings compatible with IFMIS imports.
  - Example mapping documents that show how Excledge sales/invoice data maps to government chart of accounts or to IFMIS import formats.
  - Evidence of reconciliation procedures (scripts, SQL queries, or job definitions used to match payments to invoices).

Relevant files (examples to reference/cite):
- https://github.com/TangaHubService/Excledge (root README)
- https://github.com/TangaHubService/Excledge/tree/main/Backend (Backend README and docs)
- https://github.com/TangaHubService/Excledge/tree/main/Postman (Postman collections and instructions)

B. How to convert repository artifacts into TOR-compliant deliverables
Below are practical steps and templates that convert the code/docs in each repo into the MINECOFIN deliverables listed in the TOR (business requirements, functional specifications, process maps, test inputs, validation records):

1) Business requirements (for a Fees & Revenue module in Smart School; Revenue & Fiscal Sales in Excledge)
- Use the provided business_requirements_TEMPLATE.md (in this repo) and fill sections with: background, objective, stakeholders (MOE, school admin, finance officers), current state (manual cash/Excel flows), target state (online invoicing, receipts, IFMIS reporting), functional requirements (FR-001...FR-n), acceptance criteria, and data mappings.

2) Functional specification
- Create a functional spec per the functional_spec_TEMPLATE.md for:
  - Smart School: Fees & Student Finance Module
  - Excledge: Fiscal Sales & Government Reporting Module
- Include API endpoint definitions, payload samples, security model, business rules, reconciliation algorithms, and test cases.

3) Process maps
- Create BPMN-style process maps: Student fee lifecycle (generate invoice, payment, receipt issuance, reconciliation) and Fiscal Sales lifecycle (sale -> fiscal receipt -> reporting -> reconciliation).

4) Validation and testing
- Extract Postman collections (Excledge) and Swagger (SMT) into test suites; write UAT scenarios and acceptance criteria, record validation sessions and stakeholder sign-offs.

5) Reporting & outputs
- Draft sample report templates (daily fiscal sales, monthly revenue summary, chart of accounts journal exports) and show export formats (CSV/Excel/JSON) that IFMIS can ingest.

C. Draft case-study content to attach (ready-to-submit)
For each project the TOR expects repositories and case evidence. Below are draft case-study texts (ready to paste into portfolio) that link to the repos and highlight PFM-relevant capabilities. Replace placeholders with metrics where available.

--- Smart School (draft case study)
Project: Smart School — Student Information & Finance
Role: Business Analyst / Technical Lead (example)
Repository: https://github.com/niyobertin/SMT_SCHOOL
Live demo: https://smt-school.vercel.app

Summary
Smart School is a modular education management platform that includes student registry, attendance, grading, and a finance module supporting invoicing and payments. The project demonstrates design and implementation of secure APIs, backend financial endpoints, and documented workflows suitable for integration to national financial systems.

PFM relevance
- Fees invoicing and receipts can be mapped to government chart-of-accounts for revenue recognition.
- Provides API and Swagger documentation enabling automated reporting and reconciliation jobs.

Key deliverables for TOR
- Business requirements and functional specification for Student Fees & Revenue module (to be added to this repository).
- Process maps and user stories for fee lifecycle and reconciliation.
- UAT scripts and validation session notes.

--- Excledge (draft case study)
Project: Excledge — Inventory & Fiscal Sales / Pharmacy Management
Role: Business Analyst / System Integrator (example)
Repository: https://github.com/TangaHubService/Excledge

Summary
Excledge is an enterprise-grade inventory and pharmacy management system that includes multi-tenant support, fiscal sales, subscription billing, and payment gateway integration. It contains a detailed backend, OpenAPI/Swagger docs, and Postman collections used for API testing and integration.

PFM relevance
- Contains fiscal sales endpoints and exportable APIs for daily/monthly fiscal reports.
- Demonstrates payment reconciliation, cron jobs for recurring reports, and role-based controls aligned with internal control patterns required in government systems.

Key deliverables for TOR
- Functional specification for Government Reporting and reconciliation processes.
- Example export mappings from sales to chart-of-accounts and IFMIS-compatible formats.
- Test collections and UAT evidence (Postman).

D. Missing items & recommended actions (what the applicant must add)
To fully meet the TOR application requirements, the repositories should be augmented with the following items (applicant action required):

1) Certificates & proof
- Scanned copies or PDFs of academic degree and CPA certificate (required for the role). Attach to application (not public if sensitive) and provide certificate of good completion for a similar assignment.

2) Case-study completion certificates
- Provide a certificate of good completion or client reference letter for at least one similar assignment (20 marks). Upload to portfolio/ or provide contactable references.

3) Explicit PFM artifacts in the repos
- Add functional spec documents for fees, revenue, and reporting (examples in this repo's docs/functional/).
- Add mapping documents showing how invoice/sales data maps to a chart of accounts and to IFMIS import formats.
- Add UAT logs and validation records (docs/reports/validation_*.md).

E. Proposed deliverables I will add to this repository (next steps)
If you confirm, I will produce and push the following files into the ifmis-sdms-modernization repo under portfolio/ and docs/portfolio:
- SMT_SCHOOL_PFM_FunctionalSpec.md — functional spec for Fees & Revenue module (includes APIs, sample payloads, business rules, acceptance criteria)
- SMT_SCHOOL_ProcessMaps.png (or .svg) — BPMN maps for fee lifecycle (I will provide text-based flow if image not available)
- EXCELEDGE_GovernmentReporting_Spec.md — functional spec for Fiscal Sales and Government Reporting (API endpoints, exports, mappings)
- EXCELEDGE_Reconciliation_Procedures.md — example SQL/scripts and cron job description
- Validation_Record_TEMPLATE.md — template and a filled example based on Postman/Swagger tests

F. Ready-to-submit application package (what I'll assemble)
- Application letter (templates/COVER_LETTER_TEMPLATE.md prefilled)
- Updated CV with degree, CPA, and project links (templates/CV_TEMPLATE.md prefilled)
- Portfolio folder with the two case studies (this dossier + functional specs + mappings + validation records)
- Technical proposal adapted to MINECOFIN TOR (docs/proposal/technical_proposal_FILLED.md)

G. Timeline to finish (after your confirmation and provision of missing items)
- 0–2 days: Produce functional specs, process maps, and mapping documents (drafts)
- 1 day: Produce UAT/test inputs and validation records from Postman/Swagger
- 1 day: Prefill CV, cover letter, and technical proposal
- 1 day: Final review and packaging for submission
Total: ~5 days (depending on how quickly you provide certs and metrics)

H. Checklist for you to provide (minimum to complete package)
- Scanned CPA certificate and academic degree (or clear photos)
- GPA or confirmation of Distinction (>70%)
- Certificate of good completion (if available) or at least one reference letter from client
- Any metrics for Smart School and Excledge (time saved, users, revenue, transactions volumes)
- Which contact email to include in the application


Prepared by: Copilot (on behalf of Nockira)
Date: 2026-10-13

