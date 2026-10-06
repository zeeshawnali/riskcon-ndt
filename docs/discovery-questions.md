# Discovery Questions for RiskCON

Status: draft, not yet asked
Prepared: 2026-10-06

## How to use this

- The goal is to learn how RiskCON works today, not to pitch features. Ask Anton to describe real recent jobs.
- Questions marked **(key)** change the design or the cost the most. If time is short, ask those first.
- Write answers under each question. "Don't know yet" is a useful answer.
- Plan for two sessions of about an hour. Sections 1 to 6 first, the rest second.

## Documents to ask for

- [ ] A sample report for every NDT method they perform, other than MT
- [ ] A filled-in field work order for an NDT job (the sample we have is for engineering work)
- [ ] Any other forms they issue: quotes, invoices, certificates, timesheets
- [ ] Their equipment list, with calibration dates
- [ ] Their list of procedures, and the codes and standards they work to
- [ ] Their list of technicians with certifications
- [ ] The list of custom fields they have added, or wanted to add, in Drive NDT
- [ ] Screenshots of the Drive NDT screens and dashboards they dislike, and any they like
- [ ] A sample export of data from Drive NDT, if one is possible
- [ ] Logo and brand files

## 1. The company and its people

1. **(key)** How many people will use the app? What does each of them do?
2. Who creates work orders? Who does inspections? Who reviews and approves reports? Who sends them to customers?
3. Is anything restricted, for example who can see pricing, or who can edit an issued report?
4. Do subcontractors or temporary techs ever do work under RiskCON's name?
5. Is the team expected to grow in the next two years?

## 2. A job from start to finish

6. **(key)** Walk me through a recent NDT job, from the customer's first call to the final report and invoice. What happens at each step, who does it, and in what tool?
7. Where does the process slow down or go wrong today?
8. What gets entered more than once?
9. What is still done on paper, in Excel, or by email?
10. How long does it take from finishing an inspection to sending the report? How long should it take?

## 3. Work orders

11. **(key)** RiskCON does engineering, consultation, inspection and certification. Should the app handle work orders for all of these, or only NDT jobs?
12. How are job numbers assigned? Must the new app continue the current sequence (e.g. 0010440)?
13. What statuses does a work order go through (e.g. requested, scheduled, in progress, reported, invoiced, closed)?
14. Can one work order cover several days, several techs, several sites, or several inspection methods?
15. Which fields on the current field work order are always filled in, and which are rarely used?
16. Is the safety and PPE section filled in for every job? Is there a hazard assessment or sign-off on site?
17. Do techs record hours, travel and kilometres on the work order? What is that used for?
18. Do you schedule techs in Drive NDT, or elsewhere? Do you want a calendar?

## 4. Inspections and reports

19. **(key)** Which NDT methods do you perform? Roughly how many reports of each per month?
20. **(key)** For each method, which fields are specific to that method? (On the MT report, that is the "Test Details" section.)
21. **(key)** Which custom fields do you need that Drive NDT doesn't give you, or makes awkward?
22. Which field names in Drive NDT are wrong for North America? What should they be called?
23. What do you like about the current MT report layout? Is there anything on it you would change?
24. Can one work order have several reports? How is the report number built (e.g. 0010383-1_MT_Rev.0)?
25. When a report is revised, what happens? Who is allowed to revise, and does the customer get both versions?
26. Who signs a report, and how: typed name, drawn signature, or an image? Does the customer sign?
27. Must a supervisor or Level III review a report before it goes out?
28. Once a report is issued, should it be locked?
29. How many photos does a typical report have? Do you annotate them, for example arrows or markings? Do they need to be in a set order?
30. Do reports record individual welds or locations, each with its own result, or one overall result as in the MT sample?
31. When something fails, what is recorded? Is there a re-inspection after repair, linked to the first report?
32. Do you use standard wording for common findings that you would like to pick from a list?
33. Do different customers require different report layouts, or their own forms?
34. Are reports only in English?

## 5. Equipment and consumables

35. What equipment do you track? What needs calibration, and how often?
36. Should the app warn you before a calibration expires? Should it stop expired equipment being used on a report?
37. The sample MT report shows no consumables, although a wet fluorescent medium was used. Should consumables always be recorded, with batch number and expiry?
38. Do you need to keep calibration certificates and consumable batch certificates on file in the app?
39. Do you need to track stock levels of consumables, or only which batch was used?

## 6. Procedures, codes and standards

40. How many procedures do you have? How often are they revised?
41. Which codes, standards and acceptance criteria do you use most? Who decides which applies to a job?
42. Do procedures need to be attached to the report or sent to the customer?
43. The sample report cites the 2021 edition of ASME VIII for the code and the 2025 edition for the acceptance criteria. Is that deliberate? Would it help if the app only let you pick valid combinations?
44. Do you work under any regulator's or customer's program that sets rules for your records, for example TSSA or CWB?

## 7. Technicians and certifications

45. Which certification schemes do your techs hold (e.g. SNT-TC-1A, CGSB)? By method and level?
46. Should the app track certification expiry and vision test dates, and warn you?
47. Should the app stop a tech signing a report for a method they are not certified in?

## 8. Working in the field

48. **(key)** Do techs enter data on site, or back at the office from notes?
49. **(key)** What devices would they use on site: phone, tablet, laptop? Company-owned or personal?
50. **(key)** How often is there no signal on site? Would they need to work with no connection at all?
51. Are photos taken on the same device? How do they get into the report today?
52. Are there sites where phones or cameras are not allowed?

## 9. Customers

53. How do customers receive reports today? Email, a portal, paper?
54. **(key)** Would customers want their own login to see their reports and history?
55. Do customers have several sites, and several contacts per site?
56. Do any customers have special requirements that apply to every job for them?

## 10. Dashboards, search and reporting

57. **(key)** What do you want to see when you log in each morning?
58. What is wrong with the Drive NDT dashboards?
59. What questions do you often need answered and currently struggle with? (e.g. "all reports for this customer last year", "which jobs are not invoiced")
60. Do you need to find past reports by part number, serial number or CRN?

## 11. Drive NDT and existing data

61. **(key)** How long have you used Drive NDT? Roughly how many work orders and reports are in it?
62. **(key)** Can you export your data from it? In what format? Do exported reports include the photos?
63. How much history must be brought into the new app, and how much can stay as archived PDFs?
64. When does your Drive NDT subscription renew or end? Is there a notice period?
65. What does Drive NDT do well that you would not want to lose?
66. What else have you tried or looked at?

## 12. Quotes, invoices and other software

67. **(key)** Do you want quoting and invoicing in the app, or do those stay in your accounting software?
68. What accounting software do you use? Should the app send data to it?
69. What other software should the app connect to, for example email, calendar or file storage?

## 13. Records and compliance

70. How long must inspection records be kept?
71. Do customers or auditors audit your records? What do they ask to see?
72. Do any customers require that data stays in Canada?
73. Do you need a record of who changed what, and when?

## 14. Priorities and timing

74. **(key)** If the first version could do only three things well, what should they be?
75. What would make you say this was worth it, six months after switching?
76. Is there a date you need to be off Drive NDT by?
77. Who at RiskCON will test the app and give feedback, and how much time can they give?
