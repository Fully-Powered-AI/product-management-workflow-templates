# Trial: Acceptance criteria sheet, run on its invented example

- **Product:** Claude, run in Claude Code

Model: Claude Sonnet 5.5 (model ID claude-sonnet-5-5). The assistant that ran this trial did not write the template.

Date: 2026-11-10

The inputs are the invented example in `public/example.md` (Larkfield Garden Supplies, a made-up online garden shop). No client data was used.

## Inputs used

The story, the five business rules (R1 to R5), the three design states (S1 to S3) and the two known failures (F1, F2) from the "What the person supplies" section of `public/example.md`. The example's own sheet was not read until after the output below was produced. The optional inputs (team list of vague words, glossary, maximum number of criteria) were not supplied, so the default maximum of 15 applied.

## What came out

The instruction block and output format were followed as written. The sheet below is the output, with the long coverage and question lists kept whole.

```
ACCEPTANCE CRITERIA SHEET: Enter a discount code at checkout

Story: A shopper enters a discount code at checkout to see their savings before paying, quickly.

Inputs read: 5 rules (R1 to R5), 3 design states (S1 to S3), 2 known failures (F1 to F2). Not supplied: nothing.

Expected behaviour:
AC-1 [R5, S1, S2]. Given the shopper is on checkout with an empty code field, items subtotal $60.00 and today is within 1 to 31 March 2027; when the shopper enters SAVE10 and presses Apply; then the page shows "Code SAVE10: −$6.00" with a Remove link, the items total is $54.00 and shipping is unchanged, all before the shopper pays.
AC-2 [R1, S2]. Given the same basket; when the shopper enters "save10" or "Save10"; then the result is the same as AC-1.
AC-3 [R5, S2]. Given items subtotal $300.00; when SAVE10 is applied; then the line reads "Code SAVE10: −$25.00" (not −$30.00) and the items total is $275.00.
AC-4 [R5]. Given a basket with items subtotal $60.00 and any shipping charge; when SAVE10 is applied; then the shipping charge is exactly what it was before.
AC-5 [R4, R5]. Given items subtotal $60.00 plus a gift card in the basket; when SAVE10 is applied; then the discount is worked out on $60.00 only: −$6.00.
AC-6 [story]. Given a valid code; when the shopper presses Apply; then the result shows within [T-1] seconds. Blocked by T-1, Q-1.
AC-7 [S2, S1]. Given SAVE10 applied to items subtotal $60.00; when the shopper presses Remove; then the discount line disappears and the items total is $60.00. What the field and button show afterwards is not in the design. Blocked by Q-10.

Error cases:
ERR-1 [F1, R3, S3]. Given today is 1 April 2027 and items subtotal $60.00; when SAVE10 is entered; then the message "This code has expired." shows, no discount is applied and the total stays $60.00.
ERR-2 [R4, S3]. Given items subtotal $39.99; when SAVE10 is entered; then the message "Spend $40 or more on items to use this code." shows, no discount is applied and the total is unchanged.
ERR-3 [S3]. Given any basket; when a code that does not exist (for example SAVE99) is entered; then the message "That code isn't valid." shows and the total is unchanged.
ERR-4 [S1]. Given the code field is empty; when the shopper presses Apply; then the result is not in the design. Blocked by Q-4.
ERR-5 [F2, S3]. Given the code-checking service does not answer; when the shopper presses Apply; then what the shopper sees, how long they wait, and whether they may still pay without the code are not in the design. No discount may be shown as applied unless the service confirmed the code. Blocked by T-2, Q-2, Q-3.
ERR-6 [R3, S3]. Given today is 28 February 2027; when SAVE10 is entered; then no discount is applied; the message is not in the design (the only date message says "expired"). Blocked by Q-7.
ERR-7 [R4, S3]. Given items of $30.00 and a gift card of any value in the basket; when SAVE10 is entered; then the message "Spend $40 or more on items to use this code." shows, because the gift card does not count, and no discount is applied.
ERR-8 [R2]. Given SAVE10 is applied; when the shopper enters a second code; then the order must not carry two codes; what is shown, and which code stays, is not in the rules or design. Blocked by Q-8.
ERR-9 [S3]. Given a basket within the rules; when " SAVE10 " is entered with spaces around it; then the result is not in the inputs. Blocked by Q-13.

Edge cases:
E-1 [R4, R5]. Given items subtotal exactly $40.00; when SAVE10 is applied; then it is accepted, the line reads "Code SAVE10: −$4.00" and the items total is $36.00.
E-2 [R3]. Given today is 1 March 2027; when SAVE10 is applied to a qualifying basket; then it is accepted. Which clock decides "today" is Q-5. Blocked by Q-5.
E-3 [R3]. Given today is 31 March 2027; when SAVE10 is applied to a qualifying basket; then it is accepted. Blocked by Q-5.
E-4 [R5]. Given items subtotal exactly $250.00, then $250.01; when SAVE10 is applied to each; then both discounts are $25.00 and the totals are $225.00 and $225.01.
E-5 [R5]. Given items subtotal $249.99; when SAVE10 is applied; then the discount is $24.999 before rounding, so the amount shown is not defined. Blocked by Q-6.
E-6 [R4, S3]. Given a basket holding only gift cards (items subtotal $0.00); when SAVE10 is entered; then the message "Spend $40 or more on items to use this code." shows and nothing is discounted.
E-7 [R2, S2]. Given SAVE10 is already applied; when the shopper enters SAVE10 again; then the result is not in the design. Blocked by Q-9.
E-8 [S2]. Given SAVE10 is applied; when the shopper reloads or leaves checkout and returns; then whether the code is still applied is not in the inputs. Blocked by Q-11.
E-9 [R4, S2]. Given SAVE10 is applied to $60.00; when the shopper removes items so the subtotal falls under $40.00; then what happens to the code is not in the inputs. Blocked by Q-12.

Edge categories considered and not relevant: Two people at once: no rule limits how many orders may use a code. A different kind of user: the story and rules name only "a shopper". One, many (items): no rule depends on the number of items, only on the subtotal.

Terms that need a number:
T-1. "quickly", in the story. Question: how many seconds from pressing Apply to the result showing, and on what connection?
T-2. "does not answer", in F2. Question: after how many seconds does the shop treat the service as not answering?

Conflicts between inputs: None.

Coverage:
R1 AC-2. R2 ERR-8, E-7. R3 ERR-1, ERR-6, E-2, E-3. R4 AC-5, ERR-2, ERR-7, E-1, E-6, E-9. R5 AC-1, AC-3, AC-4, E-1, E-4, E-5.
S1 AC-1, ERR-4, AC-7. S2 AC-1, AC-2, AC-3, AC-7, E-7, E-8, E-9. S3 ERR-1, ERR-2, ERR-3, ERR-5, ERR-6, ERR-7, ERR-9, E-6.
F1 ERR-1. F2 ERR-5.
No criterion: None.

Questions for the owner:
Q-1. How many seconds is "quickly" (T-1)?
Q-2. After how many seconds is the code service treated as not answering (T-2)?
Q-3. When the code service does not answer, what does the shopper see, and may they pay without the code?
Q-4. What happens if Apply is pressed with nothing typed?
Q-5. Do the SAVE10 dates run on the shop's clock or the shopper's? Which time zone? Does 31 March end at midnight?
Q-6. How is the 10% rounded when it does not come to a whole cent?
Q-7. What message shows before 1 March 2027? The design words only "expired".
Q-8. When a second code is entered while one is applied, what is shown and which code stays?
Q-9. When SAVE10 is entered again while applied, what is shown?
Q-10. After Remove, does the page return to the empty field and Apply button (S1)?
Q-11. Does an applied code survive a reload or leaving checkout?
Q-12. If the subtotal falls below $40.00 after the code is applied, is the code removed, kept, or refused with a message?
Q-13. Are spaces around a typed code ignored?
Q-14. Is "−$6.00" in S2 only an example amount, to be worked out from each basket?

Counts: 25 criteria. 12 ready to confirm. 13 blocked (AC-6, AC-7, ERR-4, ERR-5, ERR-6, ERR-8, ERR-9, E-2, E-3, E-5, E-7, E-8, E-9).
This is more than 15, so the story could be split: the core code-entry-and-discount behaviour, and the edge cases around changing the basket afterwards.

Confirmation: Proposed by the assistant, not yet agreed.
Product owner: ______  Engineering: ______  Test owner: ______  Date: ______

This sheet writes no code or tests and changes no records.
Every criterion is a proposal until the product owner confirms it.
```

## What was observed

- **Every required part was produced.** All the sections of the output format are present, the confirmation block was left blank, and nothing was stopped for: the story has a user, an action and a purpose, and "quickly" was treated as a vague word, not a second outcome.
- **Figures.** Every figure that appears traces to a rule, to the design ("−$6.00" is 10% of $60.00) or is a scenario subtotal I chose: $60.00, $300.00, $250.01, $249.99, $39.99, $30.00 and $0.00. The inputs give no baskets, so some scenario figure is unavoidable. The template does not say whether the assistant may pick them.
- **The sheet is long.** 25 criteria against a default maximum of 15, because the design leaves many gaps. The split suggestion is applied literally even though the story is already one small story.
- **Differences from the published example.** The example has 16 criteria, 6 blocked. Mine has 25, 13 blocked. The example left out: the 1 March start (my ERR-6, E-2), spaces around the code, reloading, changing the basket after applying, shipping not discounted as its own check, gift cards that do count towards nothing as a valid case (AC-5) and a basket of only gift cards. The example has a rounding case at $44.55 (mine uses $249.99). The example asserts that after Remove the page returns to the empty-field state; I blocked that as a question because the design does not say. The example gives a second code a defined outcome (not applied, SAVE10 stays) and blocks only the message; I blocked the whole outcome. The example treats "interrupted midway" and "different permissions" as not relevant; I made the first a blocked criterion. The example's ERR-2 uses a $25.00 gift card and a $30.00 subtotal and its E-4 uses $44.55; neither figure is in the inputs.
- **Facts not in the inputs.** In my output: the scenario subtotals above, the dates 28 February and 1 April 2027, and the example code SAVE99. In the published example: the gift card value, $44.55, $400.00 and the claim that Remove returns to the empty-field state.
- **Reviewer checklist.** Items 1 to 8 hold for my output on reading, with the caveat that scenario figures are mine. I did not run any code.

## Where the template was unclear

- The fenced instruction block contains the placeholder "[your maximum criteria per story]" with no default, while the default of 15 appears only in the surrounding text. An assistant given only the block has no number.
- The block has eleven numbered steps and the procedure has ten, so "step 6" means different things in each.
- "Use figures from the inputs and work each one out" conflicts with "never invent a figure" when the inputs contain no basket sizes. The template does not say that scenario amounts may be chosen, or that they should be labelled as such.
- It is not said how to treat a criterion that is only partly unclear (AC-7: the discount disappears, but the page state afterwards is not defined). I split it into a stated result and a question, and marked it blocked.
- A date-boundary criterion that depends on the time zone can be blocked or not; the template does not say which.
- "None, one, many" in the edge list is hard to apply to a story without a collection; I applied it to items in the basket.
- "Does not answer" is not on the default list of vague words but needs a number to test, so I listed it as a term.
- When the sheet runs past the maximum, "suggest the story be split" is required even when the story cannot sensibly be split.

## Changed after the run

The output and observations above are as recorded and describe the template and the example as they stood at the run. After an independent review on 10 November 2026 the template and the example were changed as listed below, and the template was not run again. Nothing in the recorded output was altered.

- **Split threshold.** The instruction block now carries "default 15" in step 10, so an assistant given only the block has a number.
- **Scenario amounts.** Procedure step 3, the instruction block, the stop conditions and the output format now say that example amounts and dates may be chosen, must be marked with an asterisk and listed on a new "Scenario amounts chosen" line, and that a rule, limit, message or outcome is never chosen. Reviewer checklist items 2 and 4 say the same.
- **Partly unclear criteria.** Write the part the inputs settle, put the rest in a question, mark the whole criterion blocked.
- **Time zone.** A criterion that depends on a date or time with no stated clock is blocked, with a question. Both ends of a date range are limits.
- **None, one, many.** With no collection, read them as what the rules count (for example codes per order).
- **Failure conditions with no limit.** Phrases such as "does not answer" are now on the list of terms that need a number, in the procedure and the instruction block.
- **Split suggestion.** It names which criteria go to which part, or says the story cannot sensibly be split. The output format has a place for it.
- **Step numbering.** The procedure now has eleven steps, matching the instruction block, so "step 6" means the same in both.
- **Instruction block.** "and so on" was added to the vague-word list, and the decline of legal, contract and employment terms was added.
- **Example.** It was rewritten to follow the changed template. It marks its chosen amounts, blocks the state after Remove and the choice of which code stays when a second is entered (neither is in the inputs), adds a date inside the SAVE10 window to the first criterion, covers both ends of the date range, the same code entered twice, and the day before the start, lists the edge categories left out with reasons from the inputs, lists "does not answer" as a term, uses the labels T-1 and Q-1 as the output format does, and carries a split suggestion because it has 19 criteria, above 15.
- **Tests.** The template's note on proposed tests now points to this record, and a ninth test (no example amounts) was added.

- **Second review, 10 November 2026.** The rule on clocks was narrowed to dates and times at or next to a limit, in the procedure and the instruction block, so a date well inside a window is not blocked. The example was edited to match: the days either side of the date range are now blocked on the clock question, the edge cases gained one step above the $40.00 and $250.00 limits, amounts at or beside a limit are stated to be worked out from the rules, and the example now has 21 criteria, 12 blocked, with a three-way split suggestion. The template was not run again.

Not fixed: the example is not a re-run. Its sheet was written to follow the changed template, not produced by a fresh run, so it has not been shown that an assistant given the changed instructions produces it.
