# Release notes draft: an invented example

*Illustrative example with invented data.* Fennel Rota is an invented shift-planning web app for small shops and cafes. Its product owner needs the notes for release 4.2. Everything below, the product, the people, the items and every date, is invented.

## What the person supplies

**Release brief**

Product: Fennel Rota. Release: 4.2, shipped 9 November 2026. Readers: shop and cafe managers who build rotas, and staff who read them. Published as: one page in the help centre. Plain wording, addressed to "you". Where users get help: Contact support, in the Help menu. The draft is prepared on 10 November 2026.

**Release items** (`item_code, item, change_type, what_changed_for_users, who_is_affected, where_to_find_it, user_action_needed, user_action_steps, status, claim_evidence`)

```
R1,shift_swap_v2,new,"Staff can offer one of their shifts to a named colleague. The colleague accepts or declines, and the manager approves the swap before the rota changes.","Managers and staff","My Rota: open a shift and choose Offer shift",no,,shipped,
R2,rota_export,changed,"The rota can now be downloaded as a PDF as well as a spreadsheet file. In the spreadsheet, the first column is now called Staff member instead of Name.",Managers,"Rota page: Download menu",yes,"1. Open any saved spreadsheet that reads the rota download. 2. Change the column name it looks for from Name to Staff member.",shipped,
R3,import_tpl_v1,removed,"The version 1 import template no longer works. Use the version 2 template.",Managers,"Rota page: Import, then Download template",yes,"1. In Import, choose Download template. 2. Copy your staff and shifts into the new file. 3. Import it.",shipped,
R4,rota_perf,performance,"The rota page opens faster for large teams.",Managers,"Rota page",no,,shipped,
R5,reminder_dupe_fix,fixed,"Break reminders no longer appear twice on phones set to a 12-hour clock.",Staff,"Notifications on the phone",no,,shipped,
R6,payroll_hours_view,new,"Weekly hours for each person are shown in a report for payroll.",Managers,"Reports menu",no,,behind_flag,
R7,db_upgrade,changed,,,,no,,shipped,
R8,role_colours,new,"Shifts are coloured by role.","Managers and staff","My Rota",no,,planned,
```

**Known issues** (`issue_code, issue, who_is_affected, workaround, status, related_item`)

```
K1,"A swap offered to a colleague who has a day off booked on that date can still be accepted. The manager sees a clash warning only when approving the swap.",Managers,"Check the clash warning before approving a swap.",open,R1
K2,"In the PDF download, names longer than 24 characters are cut off.",Managers,"Use the spreadsheet download for those names.",open,R2
K3,"After editing on two devices at once, the rota page sometimes shows old shifts.",Managers,"Reload the page.",closed,
```

**Glossary** (`internal_term, user_term`)

```
shift_swap_v2,Shift swaps
rota_export,Rota download
import_tpl_v1,Version 1 import template
reminder_dupe_fix,Break reminders
```

## What comes out

```
RELEASE NOTES DRAFT: Fennel Rota 4.2

Prepared 10 November 2026 for the product owner. Readers: shop and cafe managers who build rotas, and staff who read them. Shipped 9 November 2026. Status: DRAFT, not approved. Blockers: none.
In this release: 1 new, 1 changed, 1 removed, 1 fixed; 2 of these need action from the user. Known limitations: 2.
Item codes in square brackets are for the checker. Delete them before publishing. Sections 1 to 7 are the notes; sections 8 to 11 are for the product owner only.

1. WHAT YOU NEED TO DO
Rota download [R2]. Who: Managers. Where: Rota page: Download menu. Steps: 1. Open any saved spreadsheet that reads the rota download. 2. Change the column name it looks for from Name to Staff member.
Version 1 import template [R3]. Who: Managers. Where: Rota page: Import, then Download template. Steps: 1. In Import, choose Download template. 2. Copy your staff and shifts into the new file. 3. Import it.

2. WHAT IS NEW
Shift swaps [R1]. Staff can offer one of their shifts to a named colleague. The colleague accepts or declines, and the manager approves the swap before the rota changes. Who: Managers and staff. Where: My Rota: open a shift and choose Offer shift.

3. WHAT HAS CHANGED
Rota download [R2]. The rota can now be downloaded as a PDF as well as a spreadsheet file. In the spreadsheet, the first column is now called Staff member instead of Name. Who: Managers. Where: Rota page: Download menu. Action needed: see Rota download under What you need to do.

4. WHAT HAS BEEN REMOVED
Version 1 import template [R3]. The version 1 import template no longer works. Use the version 2 template. Who: Managers. Where: Rota page: Import, then Download template. Action needed: see Version 1 import template under What you need to do.

5. WHAT HAS BEEN FIXED
Break reminders [R5]. Break reminders no longer appear twice on phones set to a 12-hour clock. Who: Staff. Where: Notifications on the phone.

6. KNOWN LIMITATIONS
Shift swaps [K1]. A swap offered to a colleague who has a day off booked on that date can still be accepted. The manager sees a clash warning only when approving the swap. Affects: Managers. What to do: Check the clash warning before approving a swap.
Rota download [K2]. In the PDF download, names longer than 24 characters are cut off. Affects: Managers. What to do: Use the spreadsheet download for those names.

7. GETTING HELP
Contact support, in the Help menu.

8. HELD OUT
R4 rota_perf: a claim about speed with no evidence supplied.
R6 payroll_hours_view: status behind_flag.
R7 db_upgrade: no change for users was described.
R8 role_colours: status planned.
K3: status closed.

9. CHECKS ON THE INPUTS
- Headers matched on the release items sheet, the known issues sheet and the glossary. Every change_type, user_action_needed and status value is on its list. The ship date and the preparation date are real dates.
- 8 items and 3 known issues were read. Item codes and issue codes are unique. Every related_item named, K1 to R1 and K2 to R2, is on the items sheet.
- Statuses: 6 shipped, 1 behind_flag, 1 planned. 4 items are in the notes and 4 are held out. 2 known issues are in the notes and 1 is held out.
- The 2 included items that need user action, R2 and R3, have steps; they are copied as supplied.
- All 4 included items matched a row in the glossary.
- No word that promises more than was supplied is used. The one speed claim, R4, is held out.
- R7 also has a blank who_is_affected; it is held out for the first reason only.
- The help route was supplied in the release brief.
- The brief asks for plain wording addressed to "you". The entries keep the sheet's wording, which is mostly in the third person, as the sheet's wording wins. The wording is left to the product owner.

10. QUESTIONS FOR THE PRODUCT OWNER
1. R4 (rota_perf) is a performance item and no measurement or test result was supplied. Can you supply the evidence, or should it stay out of the notes?
2. R6 (payroll_hours_view) has the status behind_flag, so it is held out. Has its status changed?
3. R7 (db_upgrade) is shipped, and no description of a change for users and no affected group were supplied. Did it change anything users meet?
4. R8 (role_colours) has the status planned, so it is held out. Has its status changed?

11. APPROVALS
[ ] The product owner confirms that every entry in sections 1 to 6 matches what shipped, and approves publication. Name and date: ______
[ ] The engineer confirms the steps in section 1 and the limitations in section 6. Name and date: ______
[ ] The support lead confirms section 7 and that support can answer questions on sections 1 to 6. Name and date: ______
Nothing is published until a person ticks the first box.

This draft was prepared on 10 November 2026 from the release brief, the release items, the known issues and the glossary supplied. It publishes nothing and changes no record.
```
