# NDT Work Order & Inspection App: Project State

Last updated: 2026-10-06
Current stage: 1. Discovery (in progress; sample documents reviewed, client questions not yet asked)

## How to use this document

This is the single source of truth for the project. Any AI agent or person consulted on this work should read it first.

- "Decided" items are settled. Do not reopen them without a reason.
- "Open" items are undecided. Do not assume an answer.
- The project owner is not a coder. Explain technical points in plain language.
- No code is to be written until the planning stages (1 to 3) are complete.

## Overview

A web app to log and track NDT (non-destructive testing) work orders and inspections, and to generate inspection reports, typically as PDF.

- First client: RiskCON (Brampton, Ontario), an engineering, consultation, inspection and certification company. The client contact is referred to as "Anton".
- RiskCON currently uses Drive NDT and is unhappy with it.
- Long-term goal: use this build as the base for a product sold to other NDT companies, competing with Drive NDT.

## Files in this folder

| File | What it is |
|---|---|
| `PROJECT_STATE.md` | This document: what the project is and what has been decided. |
| `PROJECT_PLAN.md` | The tracker: stages, steps, and how far along we are. |
| `client-samples/DRAFT-0010383_0010383-1_MT_Rev_0.pdf` | Sample Magnetic Particle Examination Report (14 pages). This is the deliverable sent to RiskCON's customers. Anton likes this format. |
| `client-samples/Times_Iron_Works_Inc-0010440.pdf` | Sample Field Work Order (1 page). A tech takes this to the job site. |

The `client-samples/` folder holds real customer names and contact details. It is excluded from git and exists only on the owner's computer. Never commit its contents. An agent without access to it should rely on the "What the sample documents show" section below.

## Client's problems with Drive NDT

- UI is messy and hard to read.
- They need many custom fields.
- Field names follow European NDT standards, not North American ones.
- Dashboards are not helpful or easy to read.

## Known requirements

- Log and track work orders.
- Log and track NDT inspections.
- Generate an NDT inspection report as PDF, matching the layout of the sample MT report.
- The data entry screen for a report should follow the same sections and order as the printed report, so entering data feels like filling in the report.
- Generate a printable Field Work Order.
- User login.
- More requirements to come from discovery.

## What the sample documents show

### Magnetic Particle Examination Report

Page 1 is a one-page form. Pages 2 to 14 are photos, one per page, each with a number and caption.

Sections on page 1, in order:

1. **Header:** logo, company address, report title, report number, page count.
2. **Client & Project Information:** client name and address, client order no., client contact, project, work location, RiskCON order no., NDE request no., inspection date, report no., revision details.
3. **Codes, Standards & Procedures:** specification, procedure, technique, code/standard and level, acceptance criteria and level.
4. **Job/Part(s) Description & Surface Conditions:** scope/purpose, part examined, part no./ID, quantity, material, thickness, test surface condition, surface temperature, painted surface, paint thickness.
5. **Test Details:** type, medium, method, current, lighting condition, post-cleaning, verification, demagnetization. These fields are specific to the MT method.
6. **Equipment:** a list of devices, each with serial no., device no. and expiry date.
7. **Consumables:** a list with batch no. and expiry.
8. **Details of Examination:** free text.
9. **Result:** e.g. "Acceptable according specified criteria".
10. **Disclaimer:** fixed legal text.
11. **Sign-off:** technician, assistant(s), supervisor, customer. Technician and supervisor show level, certificate no. and certification scheme (e.g. "MT II | 0000 | SNT-TC-1A"), plus date.

What this implies for the design:

- **Numbering.** Order no. `0010383`, report no. `0010383-1_MT_Rev.0`. So one work order can have several reports, each with a method and a revision number.
- **Draft vs issued.** The sample carries a DRAFT watermark, so reports have a status.
- **Method-specific section.** Only "Test Details" is specific to MT. The other sections look common to all methods. This suggests a shared report structure with one swappable section per method. To be confirmed against reports for other methods.
- **Photos.** Reports carry many captioned photos, so photo upload and storage is a core feature.
- **Sign-off pulls from employee records:** certification level, number, scheme.
- **Equipment pulls from an equipment register:** serial no., device no., calibration expiry.

### Field Work Order

Sections: work report details (client, client no., business line, date of request, quote no., customer order no., purchase order, contacts), project information (dates, facility, shift start, return kilometres, site contact, technicians, assistants, scope of work, classification, procedure, testing standard, acceptance criteria, test object), and general safety (site conditions, PPE, comments).

What this implies for the design:

- **Work orders are not only NDT.** The sample is for "Retained Engineering" under the "Engineering" business line. The app must handle work orders with no inspection attached.
- **The work order feeds the report.** Client, procedure, standard and acceptance criteria appear on both, so they should be entered once.
- **Job costing data** such as return kilometres is captured, which hints at invoicing needs.
- **Quotes** have their own number, so quoting may be part of the workflow.

### Data quality issues seen in the samples

These are the kind of errors the new app should prevent.

- Code/standard cites ASME BPVC VIII.1 **2021**; acceptance criteria cites the **2025** edition of the same clause.
- "Demagnitization" is misspelled on the report.
- Consumables section is empty, although a wet fluorescent medium was used.
- Technician certificate number is a placeholder ("0000").
- Work order "date of request" (09/28/2026) is after the start date (09/25/2026).
- Work order client address says Stouffville; the facility address says Gormley, for the same street address.
- Work order "Company/Site" field contains only ", ,".

## Candidate data tables (draft, not a final data model)

- Customers (with contacts and sites)
- Employees (with certifications)
- Quotes
- Work Orders
- Inspections / Reports (with revisions)
- Report Photos
- Equipment (with calibration expiry)
- Consumables (with batch no. and expiry)
- Procedures
- Codes / Standards / Acceptance Criteria

## Decided

| Date | Decision |
|---|---|
| 2026-10-06 | Follow a proper SDLC. Plan fully before building. |
| 2026-10-06 | Build in small slices, each reviewed with the client, not one big build. |
| 2026-10-06 | Multi-tenant foundation from day one: every record is tied to the company that owns it. |
| 2026-10-06 | Stack and hosting are NOT chosen yet. They will be decided in the Design stage, after requirements are known. |
| 2026-10-06 | Maintain this document as the project state record. |
| 2026-10-06 | Keep the existing MT report format. The data entry screen mirrors the report layout. |
| 2026-10-06 | Use git for version control, with a private remote copy so files do not live only on the owner's computer. |
| 2026-10-06 | Client documents containing customer data stay out of git, even though the repository is private. |
| 2026-10-06 | Track progress in `PROJECT_PLAN.md`. |

## Design principles to carry forward

- **Per-tenant configuration.** Each client should have its own configuration, so that features and customizations can be switched on or off per client from our side. The owner has worked with this pattern before (an app ID tied to each client's configuration). Not needed for v1, but the design must not block it.
- **Resellable base.** Avoid hard-coding anything specific to RiskCON that another NDT company would need differently. Logo, address, disclaimer text and numbering format are per-company settings.
- **North American terminology** for field names and standards.
- **Pick from lists, don't retype.** Standards, procedures, equipment and certifications are chosen from maintained lists, to prevent the errors listed above.

## SDLC stages

1. **Discovery:** learn the client's workflow; produce a requirements document.
2. **Scope:** split requirements into v1 and later.
3. **Design:** data model, screen wireframes, report layout, stack and hosting choice.
4. **Build:** one working slice at a time.
5. **Test:** internal testing, then the client's techs run real jobs alongside Drive NDT.
6. **Launch:** migrate data, train users, switch over.
7. **Maintain:** backups, fixes, change requests.

## Open questions for Discovery

- Which NDT methods does RiskCON perform (MT is confirmed; UT, PT, RT, VT, ET, others)? Can we get a sample report for each?
- Were the two sample PDFs produced by Drive NDT, or by another tool?
- Should non-NDT work (e.g. retained engineering) be managed in the app, or only NDT jobs?
- How many users, and in what roles?
- Workflow from job intake to report delivery: who does what, and who approves? Where do quotes and invoices fit?
- Field use: do techs enter data on site? On what devices? With poor or no signal? Photos are confirmed.
- Data migration: can RiskCON export its history from Drive NDT, and in what format? How much history must come across?
- Which custom fields do they need, per method?
- Which codes, standards and acceptance criteria do they work to?
- Audit needs: technician certifications and expiry, equipment calibration dates, sign-offs, report revisions, locking of issued reports, retention period.
- How are signatures applied: drawn, typed, or an uploaded image? Does the customer sign?
- Do RiskCON's customers need their own login to view reports?
- What should the dashboards show?
- Any data residency requirement (e.g. data must stay in Canada)?

## Open questions (commercial)

- Contract and IP: the owner must retain ownership of the code in order to resell it. Not yet confirmed.
- Pricing and support obligations for RiskCON.
- Whether billing and self-signup belong in v1 or later (currently assumed later).

## Risks

- Scope creep. The work order sample suggests quoting, invoicing and non-NDT work could all be pulled in.
- Building something too specific to RiskCON to resell.
- Custom fields: how flexibly these are handled is the largest design decision.
- Report correctness: clients and auditors rely on these reports.
- Single maintainer for a system holding a business's quality records.

## Next steps

See `PROJECT_PLAN.md` for the full tracker.

1. Connect the private GitHub repository and push.
2. Draft the discovery question list for the owner to take to Anton.
3. Obtain sample reports for the other NDT methods.

## Change log

- 2026-10-06: Document created. Project approach, stages and initial decisions recorded.
- 2026-10-06: Sample MT report and field work order reviewed; findings, new requirements and new open questions added. Client identified as RiskCON. Git decided.
