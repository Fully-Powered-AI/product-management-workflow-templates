# Product pricing options: trial on the invented example

- **Product:** Claude, run in Claude Code

Model: Claude Sonnet 5.5 (model ID `claude-sonnet-5-5`). Date: 2026-11-10.

The inputs were the invented example's: Company A and Product X, ten made-up accounts, three made-up cost rows and eight made-up research rows. No client data was used. The inputs are the ones under "What the product owner supplies" in [the example](example.md): the package definitions, usage export, cost inputs, research log, the two options and the settings (nothing set, so every default applied). The instructions followed were the fenced block in the template and its output format. The model that ran the trial did not write the template.

## What came out

The full brief, as produced before it was compared with the example:

```
PRODUCT PRICING OPTIONS BRIEF: Product X, prepared Tuesday 2026-11-10

For: the product owner. Prepared from: package definitions (2 packages), usage export (10 accounts), cost inputs (3 rows), customer research log (8 rows), settings, no notes supplied.
Column check: all headers matched.
Settings: currency dollars; unit documents; evidence age limit 12 months (rows dated before 2025-11-10 set aside); minimum rows for a range 3; minimum accounts for a segment figure 5; margin floor not set. Defaults used: evidence age limit, minimum rows for a range, minimum accounts for a segment figure, margin floor.
Summary: Today 10 accounts bill $400.00. Option 1 (per seat): $552.00 (+$152.00, +38.0%): 7 accounts pay more, 0 the same, 3 less. Option 2 (base plus extra documents): $374.00 (-$26.00, -6.5%): 2 pay more, 4 the same, 4 less. Evidence: 4 stated rows, 3 observed rows, 1 set aside. No range is printed for any segment. These are arithmetic on today's usage, not forecasts.

Checks
Cost row "payment fees" has no approver and is not used; margins are before it.
Research row R6 (2025-08-14) is older than the age limit and is set aside.
Every billing period is month; every package in the usage export is defined; no duplicate account ids; all values numeric; all kinds valid.

Packages today
Starter: $20.00 a month; includes 3 seats and 100 documents. 5 accounts.
Team: $60.00 a month; includes 10 seats and 500 documents. 5 accounts.
Today's bill is the package price; discounts are not known. Today's total: 5 x $20.00 + 5 x $60.00 = $400.00.

Value measures
Seats: freelancers (5 accounts) lowest 1, median 2, highest 3; 3.0 times. Agencies (5 accounts) lowest 4, median 8, highest 10; 2.5 times. The agencies' median is 4.0 times the freelancers'.
Documents a month: freelancers (5 accounts) lowest 30, median 60, highest 120; 4.0 times. Agencies (5 accounts) lowest 180, median 380, highest 650; 3.6 times. The agencies' median is 6.3 times the freelancers'.
Above today's allowance: A3 (120 documents; Starter includes 100) and B2 (650 documents; Team includes 500). At their seat allowance: A3 (3 of 3) and B4 (10 of 10). None is above a seat allowance.

Willingness-to-pay evidence held
Freelancers: stated 2 rows (R1 25 to 30; R2 20 to 35); observed 1 row (R8 declined at 29). Fewer than 3 rows of a kind: no range printed.
Agencies: stated 2 rows (R3 50 to 90; R4 60 to 80); observed 2 rows (R5 declined at 85; R7 accepted at 60). Fewer than 3 rows of a kind: no range printed.
Set aside as too old: R6, observed, freelancers, accepted at 15, dated 2025-08-14.
Stated and observed rows are not combined.

Options
Option 1, per seat: bill = 0.00 + 12.00 x seats.
Option 2, base plus extra documents: bill = 20.00 + 0.12 x (documents above 100).

Bills by account
A1 freelancers, 1 seat, 40 documents: today $20.00; Option 1 $12.00 (-$8.00); Option 2 $20.00 (no change).
A2 freelancers, 2 seats, 85 documents: today $20.00; Option 1 $24.00 (+$4.00); Option 2 $20.00 (no change).
A3 freelancers, 3 seats, 120 documents: today $20.00; Option 1 $36.00 (+$16.00); Option 2 $22.40 (20.00 + 0.12 x 20; +$2.40).
A4 freelancers, 1 seat, 30 documents: today $20.00; Option 1 $12.00 (-$8.00); Option 2 $20.00 (no change).
A5 freelancers, 2 seats, 60 documents: today $20.00; Option 1 $24.00 (+$4.00); Option 2 $20.00 (no change).
B1 agencies, 6 seats, 300 documents: today $60.00; Option 1 $72.00 (+$12.00); Option 2 $44.00 (20.00 + 0.12 x 200; -$16.00).
B2 agencies, 9 seats, 650 documents: today $60.00; Option 1 $108.00 (+$48.00); Option 2 $86.00 (20.00 + 0.12 x 550; +$26.00).
B3 agencies, 4 seats, 180 documents: today $60.00; Option 1 $48.00 (-$12.00); Option 2 $29.60 (20.00 + 0.12 x 80; -$30.40).
B4 agencies, 10 seats, 420 documents: today $60.00; Option 1 $120.00 (+$60.00); Option 2 $58.40 (20.00 + 0.12 x 320; -$1.60).
B5 agencies, 8 seats, 380 documents: today $60.00; Option 1 $96.00 (+$36.00); Option 2 $53.60 (20.00 + 0.12 x 280; -$6.40).

Option totals
Today: freelancers $100.00; agencies $300.00; all $400.00.
Option 1: freelancers $108.00 (+$8.00, +8.0%); agencies $444.00 (+$144.00, +48.0%); all $552.00 (+$152.00, +38.0%). More 7, the same 0, less 3.
Option 2: freelancers $102.40 (+$2.40, +2.4%); agencies $271.60 (-$28.40, -9.5%); all $374.00 (-$26.00, -6.5%). More 2, the same 4, less 4.
Cost at today's usage, approved rows only: 10 accounts x $2.50 = $25.00; 2,265 documents x $0.04 = $90.60; total $115.60.
Gross margin before the unapproved row (payment fees): today ($400.00 - $115.60) / $400.00 = 71.1%. Option 1 ($552.00 - $115.60) / $552.00 = 79.1%. Option 2 ($374.00 - $115.60) / $374.00 = 69.1%. Margin floor not set.
These totals assume no account changes plan, changes usage or leaves.

Against the evidence
Each line gives the median bill in the segment, then the highest bill, and where each sits against each research row (median first, then highest).
Today, freelancers (median $20.00; highest $20.00): R1 stated 25 to 30: below, below. R2 stated 20 to 35: inside, inside. R8 observed declined at 29: below, below.
Option 1, freelancers (median $24.00; highest $36.00): R1 stated 25 to 30: below, above. R2 stated 20 to 35: inside, above. R8 observed declined at 29: below, at or above.
Option 2, freelancers (median $20.00; highest $22.40): R1 stated 25 to 30: below, below. R2 stated 20 to 35: inside, inside. R8 observed declined at 29: below, below.
Today, agencies (median $60.00; highest $60.00): R3 stated 50 to 90: inside, inside. R4 stated 60 to 80: inside, inside. R5 observed declined at 85: below, below. R7 observed accepted at 60: at or below, at or below.
Option 1, agencies (median $96.00; highest $120.00): R3 stated 50 to 90: above, above. R4 stated 60 to 80: above, above. R5 observed declined at 85: at or above, at or above. R7 observed accepted at 60: above, above.
Option 2, agencies (median $53.60; highest $86.00): R3 stated 50 to 90: inside, inside. R4 stated 60 to 80: below, above. R5 observed declined at 85: below, at or above. R7 observed accepted at 60: at or below, above.

Uncertainties
1. The evidence is thin: no segment has three rows of either kind, so no range is printed. Freelancers have 2 stated rows and 1 observed row; agencies have 2 stated and 2 observed.
2. Stated and observed rows point differently for freelancers: the stated ranges begin at 20 and 25, and one observed row shows a refusal at 29. They are not combined.
3. Each segment has 5 accounts, the minimum for a figure, so one account moves a median.
4. The usage export holds 10 accounts. Anyone not in it (lapsed, trial or unexported accounts) is not in these totals.
5. Today's bill is the list price; discounts are not known, so the real change in money may differ.
6. Cost: payment fees ($1.20 per account per month) has no approver and is left out, so every margin is before it.
7. Option 1 raises 7 of 10 bills, and 4 of 5 agency bills by $12.00 to $60.00; B4 and B2 have the largest rises.
8. Option 2 leaves 4 of 5 freelancer bills unchanged and lowers 4 agency bills; the totals fall by $26.00.
9. Two accounts (A3, B2) are over their document allowance; two (A3, B4) sit at their seat allowance.
10. The only agency acceptance (R7) is at today's Team price of 60; no row tests a price above it other than R5, a refusal at 85.

Proposed tests
Each is for the product owner to run; this brief contacts no one and sets no numbers.
1. For uncertainty 1: log each pricing conversation or quote in the research log as an observed row (price shown, accepted or declined, segment, date), until the owner's chosen number of rows per segment is reached. The owner sets the number and the criteria.
2. For uncertainties 1 and 2: show a chosen option to a group of new freelancer sign-ups and log what each did (purchased, declined, price shown). The owner sets the group, the length and the criteria.
3. For uncertainty 7: for agency accounts, log what they do when shown the per-seat bill for their own seat count (renew, ask for changes, decline). The owner sets who is shown it and the criteria.
4. For uncertainty 5: log the actual amount billed per account for one month beside the list price. The owner sets the period and the criteria.

Questions for the product owner
1. Option 1 and Option 2 bill existing accounts differently from today. Does either option apply to existing accounts, or only to new ones?
2. The payment fees cost row has no approver and is left out. Who approves it, and should it be included?
3. A3 uses 120 documents against an allowance of 100, and B2 uses 650 against 500. Is anything different about these two accounts, such as an agreed exception?
4. Are there accounts, discounts or free trials not in the usage export that should be counted?
5. No margin floor was set. Is there one?
6. Do you want a further option, or a change to the allowances, worked out in a second brief?

Draft for the product owner's decision. No price is recommended, nothing has been said or promised to any customer, and no package, price or billing record has been changed.
```

## What was observed

How the trial was run, and one flaw in it. The first command that read the example printed the whole file, so the first part of the example's output (down to the margin line) was visible before the brief below was written. The inputs were read first and the brief was then worked out independently, with every bill, total, percentage and margin recomputed by a small script from the inputs. But the trial is not a fully blind one: the example's output had partly been seen. A cleaner repeat would show the run only the inputs.

Result. Every required part of the format was produced, nothing made the run stop, and no section was empty. Every figure matches the example: the account totals ($400.00, $552.00, $374.00), the counts of accounts paying more, the same and less, the cost of $115.60, the margins of 71.1%, 79.1% and 69.1%, the medians and highest bills, and every position against the research rows. This agrees with acceptance test 1.

Differences from the example, none in a figure:

- The date line reads "Tuesday 2026-11-10" in the trial and "Tuesday 10 November 2026" in the example. The format shows "[weekday date]" without saying how to write it.
- The trial puts the option's name in the summary line and the example does not.
- The trial adds a line to Checks saying the other checks passed; the format allows "No problems found" only when there is nothing else.
- Wording differs in Value measures, the options formula for Option 2 and the section on evidence, where the trial labels each position as median first and highest second.
- The uncertainties, tests and questions differ. The trial has ten uncertainties, four tests and six questions; the example has six, three and three. Both cover the required topics.

Where the instructions were ambiguous and a guess was needed:

1. Percentages by segment. The text asks for the change "as a percentage of today's total". For a segment the trial used that segment's own total today. Taking the percentage of the all-account total is also a reading.
2. Evidence counts in the summary. "Count stated and observed rows for each segment" does not say whether rows set aside count. The trial counted rows in use (4 and 3) and reported the 1 set aside separately.
3. Edges of a range. The text does not say whether a bill equal to the end of a stated range is "inside" it. The trial treated both ends as inside (for example $20.00 against 20 to 35, and $60.00 against 60 to 80).
4. Two positions per line. The format gives the median and the highest bill but does not say how the two positions are labelled. The trial put the median first and said so.
5. Seat allowance wording. The procedure says to list accounts "exactly at, or above" their seats; the format has two alternative sentences for seats ("at" and "above"). The trial used both.
6. Dates. The format says "[weekday date]" and the settings line says "before [date]"; neither fixes a date style.
7. A rounding rule is given for percentages (halves round up) but not for the multiples (3.0 times) or for negative percentages. No case in this example fell on a half.
8. Checks. The procedure does not say where the cost row left out goes in the output; both the trial and the example put it under Checks and again under Cost.

Facts in an output that are not in the inputs.

- In the trial: the uncertainty about people "lapsed, trial or unexported" and the test that uses "new freelancer sign-ups" assume groups that the inputs do not mention. They are suggestions, not facts, but they should not be there. Nothing else in the trial goes beyond the inputs.
- In the example: the uncertainty about "people who left, or never bought" names groups the inputs do not mention. Its fourth uncertainty says an allowance "may change how much A3 and B2 use", which comes close to the prediction the template says the assistant must not make. Its third test says "the next three months", which sets a number that the template says to leave to the owner. Its first test is phrased as quoting Option 2, which comes close to favouring one option. These are small, but they are the cases the template's own checklist (items 8 and 9) is written to catch.

Shortcomings of the template found in this trial:

- The ambiguities listed above.
- The output is long, and the response to each account and each option takes real effort to recompute; the template relies on the checks in the reviewer checklist. A person should recompute at least the totals.
- The fenced instruction block does not contain the exact wording of the output format, and nothing in the block says where "Checks" findings go; the trial followed the format section.
- The template's own acceptance test 1 is only as strong as the example: it was checked here against figures, not against wording.

This is one run, in one product, on one invented example. It is not a test for a client, and it does not show how the template behaves in ChatGPT, Copilot or Gemini.

## Changes made after this run, not run again

Everything above records the run as it happened and is unchanged. After a reviewer's report the template, example and profile were edited, and the template has not been run again on the edited text. The edits:

- The example's uncertainties and tests were corrected for the points noted above under "Facts in an output that are not in the inputs": the unsupported statement about the export's coverage, the forecast about A3 and B2, the number set in the third test and the first test's favouring of one option. Two further wording slips were fixed (a decline is not a purchase; the "fifth or more" remark was true only of today's bills).
- Observed research rows are no longer given one lowest-to-highest range across accepted and declined; the brief gives the number accepted and declined with their prices, and a range only for one outcome with enough rows. No figure in the example changed.
- The template now settles the ambiguities listed above: a bill equal to the end of a stated range is inside it; a segment's percentage is of its own total today; the summary counts rows in use and reports rows set aside separately; a cost row left out is written under Checks and named again on the cost line; dates are YYYY-MM-DD apart from the heading's weekday date.
- The instruction block now says where Checks findings go and how a research row for a segment with no accounts is handled.
- The profile now says the brief returns to the product owner only.

After a second independent review, further edits were made. The template has not been run again on them, and no figure in the example changed:

- The fenced instruction block now carries rules the procedure already held and the run above followed: the mean of the middle two for an even count, "price not supplied", what uncertainties and questions must always cover, each test tied to an uncertainty, and returning the brief to the product owner only.
- Rounding is settled in the template: halves round away from zero for every figure, which answers ambiguity 7 above (multiples and negative percentages). No case in the example falls on a half.
- An annual price is restated by the owner as a monthly price, the "Dates" rule moved to the first procedure step, the acceptance tests were renumbered, and the exception for too few research rows now follows the per-outcome rule for observed rows.
- The example's summary line and evidence sentence were made identical to the output format, its fourth uncertainty now says A3 and B2 "pay more than today", and each of its tests names the uncertainty it answers; the second test no longer assumes the survey respondents' seat counts are held.

The trial above was not blind, and these edits were not re-run, so the evidence is the same single run as before. A blind re-run on the edited template would make it stronger; that has not been done.
