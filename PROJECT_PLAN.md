# Project Plan & Tracker

Last updated: 2026-10-06

This document tracks how far along the project is. For what the project is, and what has been decided, see `PROJECT_STATE.md`.

How to read it:

- `[x]` done, `[ ]` not done.
- Each stage has a "Done when" line. A stage is finished only when that is true.
- Steps in later stages are a first outline. They get more detailed as we reach them.

## At a glance

| # | Stage | Status |
|---|---|---|
| 0 | Project setup | In progress |
| 1 | Discovery | In progress |
| 2 | Scope | Not started |
| 3 | Design | Not started |
| 4 | Build | Not started |
| 5 | Test | Not started |
| 6 | Launch | Not started |
| 7 | Maintain | Not started |

**Current focus:** finish setup (remote git copy), then draft the discovery questions for Anton.

## 0. Project setup

Done when: the project folder is under version control with a private remote copy, and the contract is settled.

- [x] Create project folder
- [x] Create project state document (`PROJECT_STATE.md`)
- [x] Create project plan and tracker (this document)
- [x] Start git in the project folder
- [x] Keep client documents out of git (`client-samples/` is excluded)
- [x] First commit
- [ ] Connect the private GitHub repository and push
- [ ] Confirm contract terms with RiskCON, including that the owner keeps ownership of the code

## 1. Discovery

Done when: there is a written requirements document that Anton has read and agreed with.

- [x] Record the client's problems with Drive NDT
- [x] Review sample MT report
- [x] Review sample field work order
- [ ] Draft the discovery question list
- [ ] Hold discovery session(s) with Anton
- [ ] Collect sample reports for every other NDT method RiskCON performs
- [ ] Map the workflow from job intake to report delivery
- [ ] List users and roles
- [ ] Confirm field use (devices, signal, photos)
- [ ] Find out what can be exported from Drive NDT
- [ ] Confirm audit and record-keeping needs
- [ ] Write the requirements document
- [ ] Anton reviews and agrees to the requirements

## 2. Scope

Done when: there is an agreed v1 feature list, and a "later" list, both signed off by Anton.

- [ ] Sort every requirement into v1, later, or not doing
- [ ] Decide whether quoting, invoicing and non-NDT work orders are in v1
- [ ] Define what "finished" means for v1
- [ ] Rough timeline and cost
- [ ] Anton signs off on v1 scope

## 3. Design

Done when: there is a blueprint complete enough to build from without guessing.

- [ ] Data model (tables and how they relate)
- [ ] Approach for custom and method-specific fields
- [ ] Roles and permissions
- [ ] Screen wireframes, reviewed with Anton
- [ ] Report layout specification for each method
- [ ] Choose the stack
- [ ] Choose hosting and infrastructure
- [ ] Security, backup and data residency plan
- [ ] Data migration plan
- [ ] Build plan: the order of the slices

## 4. Build

Done when: every v1 slice is built and has been shown to Anton.

Slices will be listed here once the build plan exists.

## 5. Test

Done when: RiskCON's techs have run real jobs through the app and the reports are correct.

- [ ] Internal testing of each slice
- [ ] Generated reports compared against real ones
- [ ] Trial migration of Drive NDT data
- [ ] RiskCON runs real jobs in parallel with Drive NDT
- [ ] Fix issues found

## 6. Launch

Done when: RiskCON is working in the new app and no longer in Drive NDT.

- [ ] Final data migration
- [ ] User accounts created
- [ ] User training
- [ ] Switch over
- [ ] Close monitoring for the first weeks

## 7. Maintain

Ongoing.

- [ ] Backups running and a restore tested
- [ ] Process for bug reports and change requests
- [ ] Plan for turning the base into a product for other clients
