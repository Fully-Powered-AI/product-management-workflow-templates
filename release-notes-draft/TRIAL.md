# Release notes draft: tried on its invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-10

The inputs are the invented example in `public/example.md` (Fennel Rota 4.2: the release brief, eight release items, three known issues and a four-row glossary). No client data was used. The assistant did not write the template. It followed the fenced instruction block and the output format in `member/template.md` as they stand after the review edits described below.

History of this record. The template was first run once on 10 November 2026. An independent review the same day found that the published example added words that were not in the inputs, and found gaps in the instructions. The template and the example were then corrected, and the run was repeated on the revised text. The record below is of the repeated run. The first run's observations that led to the edits are summarised under "Corrections made after the first run".

Limits on this trial. It is not a blind run. The assistant had seen the earlier run and the review's findings before the second run, and the example file prints the published output next to the inputs. The draft was written from the instruction block, the output format and the inputs, then compared with the example. A person has not repeated it independently.

## What came out

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

## What was observed

- Every part the format requires was produced, in the right order, and all counts match the sections (1 new, 1 changed, 1 removed, 1 fixed, 2 needing action, 2 limitations). Nothing made the assistant stop: headers matched, codes were unique, every value was on its list, and both items needing action had steps.
- Held out correctly: R4 (speed claim, no evidence), R6 (behind a flag), R7 (no description), R8 (planned) and the closed issue K3. Each held-out line gives the one reason from the instructions and adds nothing to it. Limitations K1 and K2 took the user terms of their related items as headings.
- R7 failed two tests (no description and no audience). The first reason in the instruction order was used, and a check line notes the second.
- The entries keep the sheet's wording, capitals and punctuation ("Managers", "Rota page: Download menu"), because the instructions now say the sheet's wording wins. The brief asked for wording addressed to "you"; the draft says in the checks that the entries do not follow it.
- Every held-out item with a status, a missing description or missing evidence got a numbered question (R4, R6, R7, R8). The questions state facts and ask; none suggests what the answer might be.
- Facts not in the inputs: none found in the draft. The held-out lines and questions were checked against the inputs one by one.
- The draft's text is the same as the output now published in `public/example.md`. The example was corrected first and this run was written to the revised instructions, so agreement does not show that a fresh run would match; it shows that the example follows the instructions.
- Where the instructions were still open and the assistant had to choose:
  1. The loose match for readers ("Managers" is inside "shop and cafe managers") relies on the new wording "match loosely". A case such as "Everyone" or "Admins" has not been tried.
  2. The question wording for a held-out status ("Has its status changed?") is a choice; the instructions only say a question is asked.
  3. Only the normal path was run. The stops (renamed header, repeated code, value off its list) and the refusals were not run.

## Corrections made after the first run

The first run's observations recorded these departures in the published example. They were corrected afterwards, and the first run's text is not kept here.

- The example's held-out line for R4 said "no measurement or test result in claim_evidence" in place of "a claim about speed with no evidence supplied". Corrected.
- The example added "so not available to everyone" to R6 and "and planned work stays out" to R8. Neither is in the inputs or the template's reasons. Both were removed.
- The example's question 3 suggested "planned downtime or a new sign-in step" for R7. That was a guess at what R7 might be and broke the rule to recommend nothing. Removed.
- The example lower-cased "Managers" and "Staff" and turned the colons in "Where" into commas. The template now says to copy them from the sheet, and the example was changed to match.
- The instruction block was thinner than the procedure: no heading rule for limitations, no "Not ready to publish", no dates in words, no sheet order, no settings input and no pasting line. The first run's record also said the block left out the rule about personal details and passwords; that was wrong, because the block has it. Only the settings input and the longer refusals were missing. The block now covers all of these.
- Repeated codes, which first only became a line in the checks, now stop the work. Several open points the first run recorded (the tone, questions for held-out items, which reason to give when two apply, the match on readers) now have a rule in the template.
