# Product pricing options

Workflow template, version 0.1.0.

## Purpose

Prepare one options brief for a product owner who is weighing how to price or package a product. The brief shows what each customer group uses, so the choice of what a price should scale with rests on data; holds the willingness-to-pay evidence, with what customers said kept apart from what they did; bills every account under each option the owner supplies and sets that against what it pays today; works out gross margin where finance has approved the costs; and ends with the uncertainties, proposed tests and questions. Every figure traces to an input and every calculation is written out. The assistant prepares; it recommends no price and no option, makes no claim to any customer, and never changes a package, a price or a billing record.

## When to use it and when not to

Use it when a price or package comes up for review: a first price, a new plan, a change to what is included, or a question about what the price should scale with.

Do not use it:

- to check what a change to a price already in the market does to margin and sales. That is price change review;
- to look at how a packaged offer reads to a buyer, its promises and its protections. That is offer review;
- to decide whether one customer gets a price below list. That is discount request review;
- to profile a competitor's prices. That is competitor profile from public pages; this template uses a competitor price only if the person puts it in the research log with a date;
- to set a price, forecast churn, or estimate how demand responds to price from data that holds no observed purchases. The brief shows what is known and what is not;
- to write customer messages, announce a price, or change billing.

## Roles

- **Runs it and brings it to the pricing conversation:** the product owner.
- **Approves the cost inputs:** [your finance approver], named on each cost row.
- **Approves prices and terms:** [your commercial authority]. The brief goes to them only if the product owner sends it.
- **Runs the proposed tests and contacts customers:** a person named by the product owner, never the assistant.

## Inputs

The assistant works only from the files and notes the person supplies. It needs no connection to billing, the product or the research tool, and never asks for a password or a login code.

1. **Package definitions.** One row per package. Default column headers: `package`, `price`, `billing_period`, `included_seats`, `included_units`. `price` is the list price. Every `billing_period` must be `month`; for an annual price the owner restates the row as a monthly price before the run.
2. **Usage export.** One row per customer account. Default column headers: `account_id`, `segment`, `package`, `seats`, `units_per_month`. `units_per_month` is the unit the product is used in, such as documents, orders or projects; the settings name it. Other measures the owner wants compared go in extra numeric columns named in the settings. Identify accounts by an id only; names and contact details are not needed.
3. **Cost inputs.** One row per cost. Default column headers: `cost_item`, `basis`, `amount`, `approved_by`. `basis` is `per account per month` or `per unit`. A row with a blank `approved_by` is not used.
4. **Customer research log.** One row per piece of evidence. Default column headers: `ref`, `date`, `segment`, `kind`, `low`, `high`, `note`. `kind` is `stated` (what a customer or prospect said or answered) or `observed` (what a customer was seen to do, such as buying, upgrading or turning down a quote). For a stated row, `low` and `high` are the range the customer gave; for an observed row, both hold the price involved and the note begins `accepted:` or `declined:`. Dates are YYYY-MM-DD.
5. **Settings,** typed: the product name; the owner; today's date; the currency; the unit's name; the evidence age limit in months [your evidence age limit]; the minimum rows for a range [your minimum rows]; the minimum accounts for a segment figure [your minimum accounts]; [your margin floor]; and the options.
   - Defaults when not given: age limit 12 months; minimum rows for a range 3; minimum accounts for a segment figure 5; margin floor not set. The Settings line names, after "Defaults used", each setting that came from a default.
   - Each option is written as four numbers and a name: `base`, `per_seat`, `included_units`, `per_extra_unit`. Bill = base + per_seat x seats + per_extra_unit x the units above included_units (nothing when units are at or below it). A price per unit on all units is included_units 0.
6. **Notes** (optional): anything the owner wants held in mind. If none, write "no notes supplied".

**Column check.** Before any arithmetic, compare each file's headers with the defaults, or with [your column headers] if the business has set its own. If a required header is missing or named differently, stop. List the headers expected and found for that file, ask which column is which, and prepare nothing else. Never guess a column.

## The procedure

1. **Check the inputs.** Run the column check. Every `billing_period` must be `month`. Every package named in the usage export must be in the package definitions. A duplicate `account_id`, a non-numeric seats or units value, a `kind` that is not `stated` or `observed`, a date that is not valid, or an observed row whose note does not begin `accepted:` or `declined:`: stop and ask. A research row with a segment that has no accounts is kept, is not set against any bill, and is listed under Checks as having no usage data. Write every date as YYYY-MM-DD, except the weekday date in the heading, written like Tuesday 10 November 2026. Rounding is the same everywhere (money to the cent, ratios and percentages to one decimal place): halves round away from zero, so 3.25 becomes 3.3 and -9.45 becomes -9.5.
2. **Packages today.** List each package with its price, what it includes and the number of accounts on it. Today's bill for an account is its package price. Discounts are not known: say so. Today's total is the sum of the bills.
3. **Value measures.** For each measure (seats, units and any named extra column) and each segment with at least [your minimum accounts] accounts: lowest, median and highest, and highest divided by lowest, to one decimal place (shown as "3.0 times"). A median of an even count is the mean of the middle two. With exactly two segments, also give the ratio of their medians. A segment below the minimum gets its accounts listed and no figures. Then list the accounts above their package's included units and the accounts exactly at, or above, their included seats. State no conclusion about what the price should scale with.
4. **Costs.** Use only rows with an `approved_by`. Cost at today's usage = the per-account rows x the number of accounts + the per-unit rows x total units. List every row left out and why, once under Checks, and name it again on the cost and margin lines, saying that margins are before it. With no approved rows, work out no margin and ask.
5. **Evidence.** Set aside every research row dated before today minus the age limit, and list it. Count stated and observed rows for each segment separately. Rows in use are counted in the summary; rows set aside are counted separately. When a segment has at least [your minimum rows] stated rows, print one stated range: the lowest `low` to the highest `high`. Observed rows are never given one range across accepted and declined: give the number accepted and the number declined, with each row's price and ref, and print an accepted range (lowest to highest accepted price) or a declined range only when that outcome has at least [your minimum rows] rows in the segment. Never print a range from fewer rows, and never combine stated and observed rows. Otherwise list the rows one by one with their refs.
6. **Options.** Restate each option as its formula. An option with no price numbers is listed as "price not supplied", worked out no further, and becomes a question. An option that cannot be written with the four numbers: stop and ask the owner to split it or to give the bill for each account. Never propose a price or an option.
7. **Bills by account.** For each account: today's bill and each option's bill, rounded to the cent, with the working for any option bill that has an extra-units part, and the change in money. Totals for each segment and for all accounts, and for each option the change in money and as a percentage of today's total, to one decimal place: a segment's percentage is of that segment's own total today, and the all-account percentage is of the all-account total. Count the accounts that pay more, the same and less. State that the totals assume no account changes plan, changes usage or leaves.
8. **Margin.** At today's usage: gross margin = (bills - cost) / bills, to one decimal place, for today and for each option. Mark any below [your margin floor]. If the floor is not set, say so.
9. **Against the evidence.** For today and each option, and for each segment that has accounts, give the median bill (the mean of the middle two for an even count, to the cent) and the highest bill. Place each against each research row of that segment that is still in use: for a stated row, "below", "inside" or "above" the range (a bill equal to either end of the range is inside); for an observed accepted row, "at or below" or "above" the accepted price; for an observed declined row, "below" or "at or above" the declined price. These are positions, not predictions; add no sentence saying what customers will do.
10. **Uncertainties.** Always cover: how thin the evidence is, stated against observed, who is missing from the usage export, that today's bill is the list price, and any cost left out. Add the specific effects that stand out in this data, such as an option that raises most bills or an allowance many accounts are over.
11. **Proposed tests.** Each tied to a stated uncertainty and describing what would be logged and how. The owner sets the numbers and the criteria; leave them blank. The assistant contacts no one.
12. **Questions.** Numbered, for the owner, facts then the question. Cover whether an option applies to existing accounts, any unapproved cost, any account above an allowance, and anything the checks raised. None recommends a price or an option.
13. **Return the brief** to the product owner only.

## Exceptions and stop conditions

- **A column header is missing or named differently:** stop; list expected and found headers; ask.
- **A billing period other than month, a package missing from the definitions, a duplicate account id, a bad value, a kind that is not stated or observed, or an observed note without accepted or declined:** stop and ask.
- **An option that cannot be written with the four numbers:** stop and ask.
- **An option with no price:** list it, work out nothing for it, and ask.
- **Fewer accounts in a segment than the minimum:** list the accounts; print no figures for that segment.
- **Fewer stated rows in a segment than the minimum, or fewer observed rows of one outcome (accepted or declined) than the minimum:** list the rows; print no range for it.
- **Asked to recommend a price or an option, name the best price, or say what customers will pay:** decline; point to the facts in the brief. The product owner recommends; the commercial authority approves.
- **Asked to estimate churn, price sensitivity or demand from stated rows alone:** decline; say what observed rows would be needed and propose the test.
- **Asked to write or send anything to a customer, announce a price, or change a package, price or billing record:** decline; name the role that does it.
- **The inputs hold customer names, contact details, card numbers, a password or a login code:** do not repeat them; tell the person to remove them from the source.

## Output format

```
PRODUCT PRICING OPTIONS BRIEF: [product], prepared [weekday date]

For: [owner]. Prepared from: package definitions ([n] packages), usage export ([n] accounts), cost inputs ([n] rows), customer research log ([n] rows), settings, [notes / no notes supplied].
Column check: all headers matched. / Stopped: [file]: expected [headers]; found [headers].
Settings: currency [currency]; unit [name]; evidence age limit [n] months (rows dated before [YYYY-MM-DD] set aside); minimum rows for a range [n]; minimum accounts for a segment figure [n]; margin floor [n]% / not set. Defaults used: [settings / none].
Summary: Today [n] accounts bill [amount]. [Option]: [amount] ([change, %]): [n] accounts pay more, [n] the same, [n] less. [One line for each option.] Evidence: [n] stated rows and [n] observed rows in use, [n] set aside. [Ranges printed for: segments / No range is printed for any segment.] These are arithmetic on today's usage, not forecasts.

Checks
[Finding; what was done.] / No problems found.

Packages today
[Package]: [price] a month; includes [n] seats and [n] [unit]. [n] accounts.
Today's bill is the package price; discounts are not known. Today's total: [working] = [amount].

Value measures
[Measure]: [segment] ([n] accounts) lowest [n], median [n], highest [n]; [n] times. [Same for each segment.] [With two segments: The [segment]'s median is [n] times the [segment]'s.]
[Segment below the minimum: accounts listed, no figures.]
Above today's allowance: [accounts, with figures]. At their seat allowance: [accounts]. [None is above a seat allowance. / Above a seat allowance: [accounts].] / None above any allowance.

Willingness-to-pay evidence held
[Segment]: stated [n] rows ([ref] [low] to [high]); observed [n] rows, [n] accepted and [n] declined ([ref] [declined / accepted] at [price]). [Stated range: [low] to [high] from [n] rows. / Fewer than [n] stated rows: no stated range printed.] [Observed: accepted range [low] to [high] from [n] rows; declined range [low] to [high] from [n] rows. / Fewer than [n] observed rows of an outcome: no observed range printed.]
Set aside as too old: [ref, kind, segment, what, date]. / Set aside as too old: none.
Stated and observed rows are not combined.

Options
[Option name]: bill = [formula]. / [Option name]: price not supplied; nothing worked out, see question [n].

Bills by account
[Account] [segment], [n] seats, [n] [unit]: today [amount]; [Option] [amount] ([change]); [Option] [amount] ([change]).
[A working in brackets for any bill with an extra-units part.]

Option totals
Today: [segment] [amount]; [segment] [amount]; all [amount].
[Option]: [segment] [amount] ([change, %]); all [amount] ([change, %]). More [n], the same [n], less [n].
Cost at today's usage, approved rows only: [working]; total [amount]; [left-out rows named]. / Cost: no approved rows; no margin worked out, see question [n].
Gross margin [before the unapproved rows]: today [working] = [n]%. [Option] [working] = [n]%. Margin floor [n]%, [options below it / none below] / not set.
These totals assume no account changes plan, changes usage or leaves.

Against the evidence
Each line gives the median bill in the segment, then the highest bill,
and where each sits against each research row.
[Today / Option], [segment] (median [amount]; highest [amount]): [ref] [kind, range or price]: [position], [position]. [Each row.]

Uncertainties
[n]. [Uncertainty, with the figures.]

Proposed tests
Each is for the [owner] to run; this brief contacts no one and sets no numbers.
[n]. [Test: what is logged, and which uncertainty it answers. The owner sets the criteria.]

Questions for [owner]
[n]. [The facts. The question.] / None.

Draft for [owner]'s decision. No price is recommended, nothing has been said or promised to any customer, and no package, price or billing record has been changed.
```

## Reviewer checklist

1. Every export header matched, or the brief stopped. (Product owner)
2. Every bill recomputes from the option's formula, with rounding to the cent. (Finance lead)
3. Totals, counts of more, the same and less, and percentages recompute. (Finance lead)
4. Only cost rows with an approver are used, and every row left out is listed. (Finance lead)
5. Stale research rows are set aside, and no range is printed from fewer rows than the minimum. (Product owner)
6. Stated and observed rows are never combined. (Product owner)
7. Every position in the evidence section is correct against its row. (Product owner)
8. No price, option, prediction or customer claim appears anywhere. (Commercial authority)
9. The tests have no numbers filled in, and every question can be answered by a person. (Product owner)

## Acceptance tests

Proposed tests. None has been run. The first uses the inputs of the invented example.

1. **Normal run.** The invented example's inputs. Expected: the brief in the example, figure for figure: Option 1 at $552.00, Option 2 at $374.00, margins of 71.1%, 79.1% and 69.1%, R6 set aside and the payment fees row left out.
2. **Renamed column.** The usage export has `plan` instead of `package`. Expected: stops; lists expected and found headers; prepares nothing.
3. **Annual prices.** A package row has `billing_period` year. Expected: stops and asks the owner to restate the row as a monthly price.
4. **Unapproved cost.** Every cost row has a blank approver. Expected: no margin worked out; question raised.
5. **Stale research.** All stated rows are older than the age limit. Expected: all set aside, listed; no stated evidence held.
6. **Enough rows for a range.** Three stated freelancer rows of 25 to 30, 20 to 35 and 22 to 28. Expected: one stated range, 20 to 35, from 3 rows; observed rows not folded in.
7. **Observed rows, mixed outcomes.** Three observed agency rows: accepted at 55, accepted at 60, declined at 85. Expected: 2 accepted and 1 declined with their prices; no single range across them; no accepted or declined range, since neither outcome has 3 rows.
8. **Bad kind.** A row with kind `likely`. Expected: stops and asks.
9. **Observed note.** An observed row whose note does not begin accepted or declined. Expected: stops and asks.
10. **Small segment.** A segment of 4 accounts with the minimum at 5. Expected: accounts listed, no median or ratio.
11. **Option outside the formula.** An option with three price bands. Expected: stops and asks the owner to split it or give each account's bill.
12. **Option with no price.** Expected: listed as price not supplied, not worked out, with a question.
13. **Even count.** A segment of six accounts. Expected: the median is the mean of the middle two.
14. **Best price.** "Which option should we choose, and at what price?" Expected: declines; points to the facts; recommends nothing.
15. **Demand estimate.** "Estimate how many agencies we would lose at Option 1." Expected: declines; names the observed rows and tests that would be needed.
16. **Customer message.** "Write the email announcing the new price." Expected: declines; names the role that does it.

## Instructions for the AI assistant

Paste this block as custom instructions, followed by the output format above.

```
You prepare a product pricing options brief for a product owner from the
files and notes the user supplies. You prepare; people decide. You
recommend no price and no option, and you make no claim to any customer.
You never write to or contact a customer, never announce anything, and
never change a package, a price or a billing record; a person approves
anything of that kind and does it. You need no access to any system and
never ask for a password or a login code.

Inputs: package definitions (package, price, billing_period,
included_seats, included_units; billing_period must be month); usage
export (account_id, segment, package, seats, units_per_month, plus any
extra numeric measure named in the settings); cost inputs (cost_item,
basis - per account per month or per unit, amount, approved_by); customer
research log (ref, date, segment, kind - stated or observed, low, high,
note - an observed note begins accepted: or declined:); settings
(product, owner, today, currency, unit name, evidence age limit default
12 months, minimum rows for a range default 3, minimum accounts for a
segment figure default 5, margin floor default not set, and the options);
optional notes. Each option is a name and base, per_seat,
included_units, per_extra_unit; bill = base + per_seat x seats +
per_extra_unit x units above included_units. Name every setting taken
from a default after "Defaults used".

1. Column check: compare every header with the list above, or with the
   business's own headers if given. If one is missing or named
   differently, stop, list expected and found headers for that file, ask,
   and prepare nothing else. Also stop and ask on a billing period other
   than month, a package missing from the definitions, a duplicate
   account id, a non-numeric value, a kind that is not stated or
   observed, an invalid date, or an observed note not beginning accepted
   or declined. A research row whose segment has no accounts is kept,
   set against no bill, and listed under Checks as having no usage data.
   Put every finding, every cost row left out and every row set aside
   under Checks. Write dates as YYYY-MM-DD, except the weekday date in
   the heading, written like Tuesday 10 November 2026. Halves round away
   from zero everywhere (money to the cent; ratios and percentages to one
   decimal place), so -9.45 becomes -9.5.
2. Today's bill is the package price; say discounts are not known.
3. Value measures: per segment with at least the minimum accounts, give
   lowest, median, highest and highest/lowest to one decimal place for
   seats, units and any extra measure (the median of an even count is the
   mean of the middle two); with two segments give the ratio of medians.
   Below the minimum, list the accounts and give no figures.
   List accounts above included units and at or above included seats.
   Draw no conclusion about what the price should scale with.
4. Costs: use only rows with an approver; list rows left out under
   Checks, name them again on the cost line and say margins are before
   them. With none, work out no margin and ask.
5. Evidence: set aside rows older than the age limit and list them;
   count rows in use in the summary and rows set aside separately.
   Count stated and observed separately. Print a stated range (lowest
   low to highest high) only when a segment has at least the minimum
   stated rows; otherwise list the rows. Never put accepted and declined
   observed rows in one range: give the number accepted and declined
   with each price, and print an accepted or declined range only when
   that outcome has at least the minimum rows in the segment. Never
   combine stated and observed.
6. Bill every account under each option, to the cent, with the working
   for extra-units parts. Totals by segment and overall, change in money
   and in percent to one decimal place (a segment's percent is of its
   own total today, the overall percent of the overall total), and counts
   of accounts paying more, the same and less. An option with no price is
   listed as "price not supplied", worked out no further, and asked
   about. An option the formula cannot express: stop and ask. Never
   propose a price.
7. Gross margin = (bills - cost) / bills to one decimal place for today
   and each option, at today's usage; mark any below the floor.
8. Against the evidence: median (the mean of the middle two for an even
   count, to the cent) and highest bill per segment for today and each
   option, placed against each research row in use (stated:
   below, inside, above, where a bill equal to either end of the range
   is inside; accepted: at or below, above; declined: below, at or
   above). Positions only; no prediction.
9. Uncertainties: always cover how thin the evidence is, stated against
   observed, who is missing from the usage export, that today's bill is
   the list price, and any cost left out; add the specific effects that
   stand out in this data. Proposed tests: each tied to a stated
   uncertainty, with no numbers or criteria (the owner sets them; you
   contact no one). Numbered questions for the owner, facts then the
   question, covering whether an option applies to existing accounts,
   any unapproved cost, any account above an allowance and anything the
   checks raised; none recommends a price or an option. Return the brief
   to the product owner only.
10. Use the output format exactly, with every working shown. Write "None."
    or the format's alternative under an empty section. End with the
    closing line exactly as the format gives it.

If asked to recommend a price or option, name a best price, or say what
customers will pay, decline and point to the facts. If asked to estimate
churn or price sensitivity from stated rows, decline and name the
observed rows or test needed. If asked to write or send anything to a
customer, announce a price or change a record, decline and name the role
that does it. If the inputs hold customer names, contact details, card
numbers, a password or a login code, do not repeat them; tell the user
to remove them. Recheck every figure before returning the brief.
```

## What to customize

- [your column headers]: your own export headers, so the check passes without a question.
- The unit your customers use and the customer groups you track.
- [your evidence age limit], [your minimum rows] and [your minimum accounts].
- [your finance approver] for cost inputs, [your commercial authority] for prices and terms, and [your margin floor].
- Your options, written as the four numbers; extra measures you want compared, such as projects or locations.
- Which files the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 10 November 2026. Written by Fully Powered AI. Editorially reviewed. Tried once on its invented example in Claude on 10 November 2026, by a model that did not write it; the record of that run is published with it. The run was not fully blind: part of the example's output had been seen before the brief was written. After that run the template was changed and not run again: observed willingness-to-pay rows are no longer given one range across accepted and declined; the template now settles that a bill equal to the end of a stated range is inside it, how a segment's percentage is taken, that the summary counts rows in use, where a left-out cost row is written and the date style; the instruction block now says where Checks findings go and how a research row for a segment with no accounts is handled; and the example's uncertainties and tests were corrected. After a second review, also not run again: the instruction block now carries the rules the procedure already held (even-count medians, rounding, "price not supplied", what uncertainties and questions must cover, returning the brief to the product owner only); rounding of halves is settled as away from zero for every figure; an annual price is restated by the owner as a monthly price; the acceptance tests are renumbered; and the example's summary line, evidence sentence and tests were made to match the format, each test naming the uncertainty it answers. Not yet tested in a client environment, and not yet tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.
