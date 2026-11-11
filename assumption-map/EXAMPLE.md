# Assumption map: an invented example

*Illustrative example with invented data.* The company, its customers, its people and every date and figure below are invented. "Company A" is an invented software company whose invoicing app is used by small trades businesses, and its product owner is planning a paid add-on that lets a customer attach job photos to an invoice. People appear by role only. First come the four inputs the product owner supplies (the brief, the plan, the beliefs and the evidence), then the map.

## The inputs

### 1. The brief (written by the product owner)

```
Concept: Job photo reports, a paid add-on to Company A's invoicing app
Product owner: Product owner
Decision this serves: Whether to start building in December 2026 for a March 2027 launch
Decision date: Friday 20 November 2026
Review date: Tuesday 10 November 2026
Context: Company A has 1,400 paying accounts. 9 customers were interviewed in September 2026.
Settings: defaults
```

### 2. The plan (typed by the product owner)

```
id,plan_item
P01,"Add photos to any invoice from the phone app, up to 10 photos per invoice."
P02,"Sell it as a $9 a month add-on to existing accounts from March 2027."
P03,"Announce it to existing customers by email and in the app, with no paid advertising."
P04,"One engineer and one designer build it from December 2026 to February 2027."
P05,"Store the photos with the cloud storage supplier Company A already uses."
P06,"Answer customer questions through the existing help desk with no new hires."
```

### 3. The beliefs (typed by the product owner)

```
id,belief,type,plan_items,if_false,test_idea
B01,"Tradespeople want proof of finished work to send with the invoice.",customer,P01;P02,stops,
B02,"Enough existing customers will pay $9 a month for it.",behaviour,P02,stops,"Ask 10 active accounts for a written pre-order at $9 a month"
B03,"Customers will open the announcement and turn the add-on on.",behaviour,P03,changes,
B04,"One engineer and one designer can finish it by the end of February 2027.",delivery,P02;P04,changes,
B05,"Photos upload reliably from a phone on a job site with a weak signal.",delivery,P01,changes,
B06,"Photos at up to 10 per invoice stay inside the current monthly storage budget.",delivery,P05,small,
B07,"The phone app stores allow us to bill the add-on through our own checkout.",environment,P02,changes,
```

### 4. The evidence (typed by the product owner)

```
id,evidence,kind,date,beliefs,direction
E01,"31 of the last 120 support tickets asked how to show a customer a photo of the finished job.",measured,2026-10,B01,supports
E02,"4 of the 9 customers interviewed said they would pay for it.",said,2026-09,B02,supports
E03,"Three competing apps charge between $6 and $15 a month for photo features.",measured,2026-08,B02,unclear
E04,"The 2025 reminders add-on was turned on by 11% of accounts in its first 3 months.",behaviour,2025-09,B03,supports
E05,"A test upload of a 4 MB photo over a slowed connection failed 3 times out of 5 on a spare phone.",measured,2026-10,B05,contradicts
E06,"Engineering's estimate for one engineer and one designer is 14 weeks.",estimate,2026-10,B04,contradicts
E07,"The October 2026 storage bill is 38% of the monthly storage budget.",measured,2026-10,B06,supports
E08,"6 of the 9 customers interviewed said they send job photos by text message today.",said,2026-09,B01,supports
```

## The map

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
2. B03: the latest supporting item, E04, is dated 2025-09, 14 months before the review date; the limit is 12 months. Is there a more recent item to add to the evidence list?
3. Learning criteria: for B02, B05 and B07, what result would count as the belief holding, and what as failing, before any test starts?

OWNER'S CHOICE
B02 [ ] Test now  [ ] Later  [ ] Accept the risk
B05 [ ] Test now  [ ] Later  [ ] Accept the risk
B07 [ ] Test now  [ ] Later  [ ] Accept the risk

Prepared for the Product owner's decision. Nothing has been decided, tested, sent or changed. No evidence has been added.
```

The product owner reads the map, answers the three questions and ticks one box for each belief shown. The map only prepared it.
