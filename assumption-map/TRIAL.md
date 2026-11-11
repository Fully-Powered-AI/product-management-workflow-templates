# Assumption map: tried once on its invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-10

The inputs are the invented example in `public/example.md` (the brief, the plan of six items, the seven beliefs and the eight evidence rows). No client data was used. The run was done once by a model that had not written the template. It read the template and only the inputs of the example, followed the instruction block and the output format, and only then read the example's published output and the reviewer checklist.

## What came out

The map came out in every section of the output format, with nothing stopped for and nothing declined. The marks, counts and ranking were worked out from the rules in the template, not copied.

- **Plan:** six items. One rests only on held beliefs (P05), four are exposed (P01 to P04), and one has no belief written (P06).
- **Beliefs:** seven. Held 2 (B01, B06), thin 3 (B02, B03, B04), contradicted 1 (B05), none 1 (B07).
- **Why the less obvious marks came out as they did:** B02 is thin because its support is two interview counts and a competitor price check marked unclear. B03 is thin because its only support, a behaviour item dated 2025-09, is 14 months before the review date. B04 is thin, not contradicted, because the only item against it is an estimate. B05 is contradicted because the item against it is measured.
- **Ranking:** 1. B02 (stops, thin), 2. B05 (changes, contradicted), 3. B07 (changes, none), 4. B04 (changes, thin, reaches 2 plan items), 5. B03 (changes, thin, reaches 1). Not yet rated: none. Evidence not tied to a belief: none.
- **Tests for the first three:** B02 the owner's own test as typed; B05 the suggested time-boxed trial, with the written-expectations option second; B07 the suggested reading of the published terms, with the written question second. Learning criteria left as "owner to set" for all three.
- **Open questions:** three. P06 has no belief written, with its words offered as a suggestion only; B03's latest supporting item is out of date; and the learning criteria for B02, B05 and B07.
- **Owner's choice:** three lines, B02, B05 and B07, with empty boxes.

The full output, in the format the template gives, was:

```
ASSUMPTION MAP: Job photo reports, a paid add-on to Company A's invoicing app

Concept: Job photo reports, a paid add-on to Company A's invoicing app.
Product owner: Product owner. Decision this serves: Whether to start building in December 2026 for a March 2027 launch. Decision date: Friday 20 November 2026.
Context: Company A has 1,400 paying accounts. 9 customers were interviewed in September 2026.
Review date: Tuesday 10 November 2026. Prepared from the plan, the beliefs list and the evidence list; default settings. No evidence has been added.

THE PLAN AND WHAT IT RESTS ON
P01 Add photos to any invoice from the phone app, up to 10 photos per invoice.
  Rests on: B01 HELD; B05 CONTRADICTED.
P02 Sell it as a $9 a month add-on to existing accounts from March 2027.
  Rests on: B01 HELD; B02 THIN; B04 THIN; B07 NONE.
P03 Announce it to existing customers by email and in the app, with no paid advertising.
  Rests on: B03 THIN.
P04 One engineer and one designer build it from December 2026 to February 2027.
  Rests on: B04 THIN.
P05 Store the photos with the cloud storage supplier Company A already uses.
  Rests on: B06 HELD.
P06 Answer customer questions through the existing help desk with no new hires.
  Rests on: No belief written.
Plan items: 6. Resting only on held beliefs: 1. Exposed: 4. With no belief written: 1.

BELIEFS, EVIDENCE HELD AND MISSING
B01 customer. HELD. Tradespeople want proof of finished work to send with the invoice.
  Plan items: P01, P02. If false: Stops the plan.
  For:
    E01 measured, 2026-10: 31 of the last 120 support tickets asked how to show a customer a photo of the finished job.
    E08 said, 2026-09: 6 of the 9 customers interviewed said they send job photos by text message today.
  Against: none.
  Neither way: none.
  Missing: Nothing flagged.
B02 behaviour. THIN. Enough existing customers will pay $9 a month for it.
  Plan items: P02. If false: Stops the plan.
  For:
    E02 said, 2026-09: 4 of the 9 customers interviewed said they would pay for it.
  Against: none.
  Neither way:
    E03 measured, 2026-08: Three competing apps charge between $6 and $15 a month for photo features.
  Missing: No supporting behaviour or measured item within 12 months.
B03 behaviour. THIN. Customers will open the announcement and turn the add-on on.
  Plan items: P03. If false: Changes the plan.
  For:
    E04 behaviour, 2025-09: The 2025 reminders add-on was turned on by 11% of accounts in its first 3 months.
  Against: none.
  Neither way: none.
  Missing: No supporting behaviour or measured item within 12 months. Latest supporting item: E04, 2025-09, 14 months before the review date.
B04 delivery. THIN. One engineer and one designer can finish it by the end of February 2027.
  Plan items: P02, P04. If false: Changes the plan.
  For: none.
  Against:
    E06 estimate, 2026-10: Engineering's estimate for one engineer and one designer is 14 weeks.
  Neither way: none.
  Missing: No supporting behaviour or measured item within 12 months. Points against: E06 (estimate).
B05 delivery. CONTRADICTED. Photos upload reliably from a phone on a job site with a weak signal.
  Plan items: P01. If false: Changes the plan.
  For: none.
  Against:
    E05 measured, 2026-10: A test upload of a 4 MB photo over a slowed connection failed 3 times out of 5 on a spare phone.
  Neither way: none.
  Missing: Contradicted by E05 (measured).
B06 delivery. HELD. Photos at up to 10 per invoice stay inside the current monthly storage budget.
  Plan items: P05. If false: Small change.
  For:
    E07 measured, 2026-10: The October 2026 storage bill is 38% of the monthly storage budget.
  Against: none.
  Neither way: none.
  Missing: Nothing flagged.
B07 environment. NONE. The phone app stores allow us to bill the add-on through our own checkout.
  Plan items: P02. If false: Changes the plan.
  For: none.
  Against: none.
  Neither way: none.
  Missing: No evidence supplied.
Beliefs: 7. Held 2, thin 3, contradicted 1, none 1.

EVIDENCE NOT TIED TO A BELIEF
None.

RANKED BELIEFS NOT YET HELD
Order: what happens if false, then the mark, then reach, then the id.
1. B02 behaviour. THIN. Stops the plan. Reaches 1 plan item. Enough existing customers will pay $9 a month for it.
2. B05 delivery. CONTRADICTED. Changes the plan. Reaches 1 plan item. Photos upload reliably from a phone on a job site with a weak signal.
3. B07 environment. NONE. Changes the plan. Reaches 1 plan item. The phone app stores allow us to bill the add-on through our own checkout.
4. B04 delivery. THIN. Changes the plan. Reaches 2 plan items. One engineer and one designer can finish it by the end of February 2027.
5. B03 behaviour. THIN. Changes the plan. Reaches 1 plan item. Customers will open the announcement and turn the add-on on.
Not yet rated: none.

SUGGESTED CHEAP TESTS FOR THE FIRST 3
1. B02 Enough existing customers will pay $9 a month for it.
  Test: Ask 10 active accounts for a written pre-order at $9 a month
  Learning criteria: owner to set.
2. B05 Photos upload reliably from a phone on a job site with a weak signal.
  Test: Suggested: a time-boxed trial of the exact step in doubt, run by the team that would build or run it, with the result written down.
  If that is not possible: ask that team to say in writing what they expect to go wrong and how they would find out.
  Learning criteria: owner to set.
3. B07 The phone app stores allow us to bill the add-on through our own checkout.
  Test: Suggested: read the published rules or terms for the exact point and note the passage.
  If that is not possible: put the question in writing to the person who owns the rule, which a person sends.
  Learning criteria: owner to set.
Beyond the first 3: B04, B03.
A behaviour or measured result moves a belief toward held.
What someone says does not.

OPEN QUESTIONS FOR THE PRODUCT OWNER
1. P06: no belief is written for this plan item. It holds that: Answer customer questions through the existing help desk with no new hires. Is that a belief the plan stands on, to be written into the beliefs list?
2. B03: the latest supporting behaviour item, E04, is dated 2025-09, 14 months before the review date; the limit is 12 months. Is there a more recent item to add to the evidence list?
3. Learning criteria: for B02, B05 and B07, what result will the product owner count as the belief holding, and what as failing?

OWNER'S CHOICE
B02 [ ] Test now  [ ] Later  [ ] Accept the risk
B05 [ ] Test now  [ ] Later  [ ] Accept the risk
B07 [ ] Test now  [ ] Later  [ ] Accept the risk

Prepared for the Product owner's decision. Nothing has been decided, tested, sent or changed. No evidence has been added.
```

## What was observed

- Every required part was produced. The marks, the plan counts, the belief counts, the month count (14 months for E04) and the ranking all match a hand count, and they match the published example. The tie-break by reach was needed once (B04 before B03) and was clear.
- Nothing in the inputs triggered a stop. The brief's "Settings: defaults" was enough to print "default settings".
- The published example and this run differ in three places only, all in wording. The two open questions are worded differently (the example asks "Is it still true, or does it need a fresh look?" for B03 and "Does it rest on a belief such as..." for P06; this run asked whether there is a newer item to add and whether the plan item is a belief to be written in). The owner's own test for B02 is printed in the example with a full stop and in this run without. The learning-criteria question is phrased a little differently. The structure, marks, counts, ranking and tests are identical.
- Where the instructions left room: the exact wording of the questions is not fixed, so two runs will differ there. The question about an out-of-date item is open to being read as asking whether the belief is still true, which the template says the assistant must not judge; this run chose to ask for a newer item instead, and the published example's "Is it still true" wording is a little closer to the line than it should be. The pattern for the "Suggested" label and the second choice is given only by example in the format, not by a rule, so it was copied from the format text. The instruction block says "12 months" while the full template says "[your evidence age limit]"; they agree on the default, and the run used 12.
- Small points: the output format says "Product owner: [role]" and the brief's role is itself "Product owner", which reads a little doubled in the output. A belief with only a contradicting estimate (B04) is marked THIN and so has no "Latest supporting item"; the template is consistent about this, but a reader may find it odd that an engineering estimate that argues against the plan leaves the belief merely thin. That follows the rule on purpose: an estimate is not behaviour or measured.
- Facts not in the inputs: none in this run's output or the published example. Every figure, date and id was repeated as typed. The weekday names (Tuesday 10 November 2026, Friday 20 November 2026) come from the brief.
- This is one run by one model on one invented example. It shows the template can be followed to a complete and correct map on that example. It does not show how it behaves on a client's real lists, or in other products.

## Changed after the run, and not run again

The output and observations above are as recorded and describe the template and the example as they stood at the run. After an independent review on 10 November 2026 they were changed as listed below, and the template was not run again. Nothing in the recorded output or observations was altered.

- **Example questions and test.** The example's two open questions were reworded to ask only what is missing (for B03, whether there is a more recent item to add to the evidence list; for P06, whether it is a belief the plan stands on, to be written into the beliefs list), and the full stop was removed from the B02 test so it prints as typed. The observation above about three differences describes the files as they stood at the run; the wording of the questions and the B02 test now agree with this run's output.
- **Suggested tests rule.** The "Suggested" label and the second choice on a line beginning "If that is not possible:" are now stated as a rule in procedure step 8 and in the instruction block, not given only by example in the format.
- **Instruction block.** The block now also says that a blank type or direction stops the run, and carries the fixed wording for when nothing is unheld or no belief has an if_false. Its text was rewrapped. What to customize now says that "12 months" and "first 3" appear in both the procedure and the block.
- **Correction to a recorded line.** In "Why the less obvious marks came out as they did", B02 is thin because its support is one interview count (E02) and a competitor price check marked unclear (E03), not two interview counts. The second interview count (E08) bears on B01. The mark and the rest of the run are unaffected.
- **Credits.** The entry now credits the third-party source of its evidence bar, as the Business model assumptions review does.
