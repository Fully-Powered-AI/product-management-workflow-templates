# Product pricing options: an invented example

*Illustrative example with invented data.* Company A is an invented software business. Product X is its invented tool that turns client briefs into formatted documents. Every account, price and note below is made up to show the shape of the result. Prices and bills are per month, in dollars.

## What the product owner supplies

**Package definitions** (`packages.csv`)

```
package,price,billing_period,included_seats,included_units
Starter,20.00,month,3,100
Team,60.00,month,10,500
```

**Usage export** (`usage.csv`), one row per account; `units_per_month` is documents a month

```
account_id,segment,package,seats,units_per_month
A1,freelancers,Starter,1,40
A2,freelancers,Starter,2,85
A3,freelancers,Starter,3,120
A4,freelancers,Starter,1,30
A5,freelancers,Starter,2,60
B1,agencies,Team,6,300
B2,agencies,Team,9,650
B3,agencies,Team,4,180
B4,agencies,Team,10,420
B5,agencies,Team,8,380
```

**Cost inputs** (`costs.csv`)

```
cost_item,basis,amount,approved_by
hosting and support,per account per month,2.50,Finance lead
document processing,per unit,0.04,Finance lead
payment fees,per account per month,1.20,
```

**Customer research log** (`research.csv`)

```
ref,date,segment,kind,low,high,note
R1,2026-03-12,freelancers,stated,25,30,Interview: would pay 25 to 30 a month for the product as it is
R2,2026-03-19,freelancers,stated,20,35,Interview: 20 to 35 a month
R3,2026-04-08,agencies,stated,50,90,Survey answer: 50 to 90 a month for a shared workspace
R4,2026-04-08,agencies,stated,60,80,Survey answer: 60 to 80 a month
R5,2026-05-21,agencies,observed,85,85,declined: quote of 85 a month for a Team-sized workspace; the buyer chose another tool
R6,2025-08-14,freelancers,observed,15,15,accepted: promotional price at launch
R7,2026-06-30,agencies,observed,60,60,accepted: upgrade from Starter to Team at 60
R8,2026-07-15,freelancers,observed,29,29,declined: asked for 29 a month after the trial; the trial ended without a purchase
```

**Settings and options, typed.** Product X. Owner: the product owner. Today: Tuesday 10 November 2026. Currency: dollars. Unit: documents. Nothing else set, so the defaults apply. Bill = base + per_seat x seats + per_extra_unit x the documents above included_units (nothing when below).
- Option 1, per seat: base 0.00, per_seat 12.00, included_units 0, per_extra_unit 0.00.
- Option 2, base plus extra documents: base 20.00, per_seat 0.00, included_units 100, per_extra_unit 0.12.

No notes supplied.

## What comes out

```
PRODUCT PRICING OPTIONS BRIEF: Product X, prepared Tuesday 10 November 2026

For: the product owner. Prepared from: package definitions (2 packages), usage export (10 accounts), cost inputs (3 rows), customer research log (8 rows), settings, no notes supplied.
Column check: all headers matched.
Settings: currency dollars; unit documents; evidence age limit 12 months (rows dated before 2025-11-10 set aside); minimum rows for a range 3; minimum accounts for a segment figure 5; margin floor not set. Defaults used: evidence age limit, minimum rows for a range, minimum accounts for a segment figure, margin floor.
Summary: Today 10 accounts bill $400.00. Option 1: $552.00 (+$152.00, +38.0%): 7 accounts pay more, 0 the same, 3 less. Option 2: $374.00 (-$26.00, -6.5%): 2 accounts pay more, 4 the same, 4 less. Evidence: 4 stated rows and 3 observed rows in use, 1 set aside. No range is printed for any segment. These are arithmetic on today's usage, not forecasts.

Checks
Cost row "payment fees" has no approver and is not used; margins below are before payment fees.
Research row R6 is dated 2025-08-14, before the cutoff of 2025-11-10, and is set aside.

Packages today
Starter: $20.00 a month; includes 3 seats and 100 documents. 5 accounts.
Team: $60.00 a month; includes 10 seats and 500 documents. 5 accounts.
Today's bill is the package price; discounts are not known. Today's total: 5 x $20.00 + 5 x $60.00 = $400.00.

Value measures
Seats: freelancers (5 accounts) lowest 1, median 2, highest 3; the highest is 3.0 times the lowest. Agencies (5 accounts) lowest 4, median 8, highest 10; 2.5 times. The agencies' median is 4.0 times the freelancers'.
Documents a month: freelancers lowest 30, median 60, highest 120; 4.0 times. Agencies lowest 180, median 380, highest 650; 3.6 times. The agencies' median is 6.3 times the freelancers'.
Above today's allowance: A3 (120 documents; Starter includes 100) and B2 (650; Team includes 500). At their seat allowance: A3 (3 of 3) and B4 (10 of 10). None is above a seat allowance.

Willingness-to-pay evidence held
Freelancers: stated 2 rows (R1 25 to 30; R2 20 to 35); observed 1 row, 0 accepted and 1 declined (R8 declined at 29). Fewer than 3 stated rows: no stated range printed. Fewer than 3 observed rows of an outcome: no observed range printed.
Agencies: stated 2 rows (R3 50 to 90; R4 60 to 80); observed 2 rows, 1 accepted and 1 declined (R5 declined at 85; R7 accepted at 60). Fewer than 3 stated rows: no stated range printed. Fewer than 3 observed rows of an outcome: no observed range printed.
Set aside as too old: R6 (observed, freelancers, accepted at 15, dated 2025-08-14).
Stated and observed rows are not combined.

Options
Option 1, per seat: bill = 0.00 + 12.00 x seats.
Option 2, base plus extra documents: bill = 20.00 + 0.12 x (documents - 100, when above 100).

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
Cost at today's usage, approved rows only: 10 accounts x $2.50 = $25.00; 2,265 documents x $0.04 = $90.60; total $115.60; payment fees left out (no approver).
Gross margin before payment fees: today ($400.00 - $115.60) / $400.00 = 71.1%. Option 1 ($552.00 - $115.60) / $552.00 = 79.1%. Option 2 ($374.00 - $115.60) / $374.00 = 69.1%. Margin floor not set.
These totals assume no account changes plan, changes usage or leaves.

Against the evidence
Each line gives the median bill in the segment, then the highest bill,
and where each sits against each research row.
Today, freelancers (median $20.00; highest $20.00): R1 stated 25 to 30: below, below. R2 stated 20 to 35: inside, inside. R8 observed declined at 29: below, below.
Option 1, freelancers ($24.00; $36.00): R1: below, above. R2: inside, above. R8: below, at or above.
Option 2, freelancers ($20.00; $22.40): R1: below, below. R2: inside, inside. R8: below, below.
Today, agencies ($60.00; $60.00): R3 stated 50 to 90: inside, inside. R4 stated 60 to 80: inside, inside. R5 observed declined at 85: below, below. R7 observed accepted at 60: at or below, at or below.
Option 1, agencies ($96.00; $120.00): R3: above, above. R4: above, above. R5: at or above, at or above. R7: above, above.
Option 2, agencies ($53.60; $86.00): R3: inside, inside. R4: below, above. R5: below, at or above. R7: at or below, above.

Uncertainties
1. Thin evidence. Each segment holds fewer than 3 rows of each kind, and each observed row is a single event, so no range is printed.
2. Stated is not observed. The only observed rows in use are one acceptance (agencies at 60) and two declines (agencies at 85, freelancers at 29); no accepted row in use is at any other price.
3. Who is missing. The usage export holds 10 accounts; anyone not in it is not counted in these totals.
4. Response unknown. Option 1 raises 7 of 10 bills, and the agencies' total by 48.0%; no row shows how accounts would respond. Under Option 2, A3 and B2 pay more than today; the inputs do not show whether their use is limited by their plan.
5. Small groups. Each segment has 5 accounts, so one account moves a median, and today each account is a fifth of its segment's total ($20.00 of $100.00; $60.00 of $300.00).
6. Today's bill is the list price; discounts paid are not known. Margins leave out payment fees, which nobody has approved.

Proposed tests
Each is for the product owner to run; this brief contacts no one and sets no numbers.
1. For uncertainties 1 and 2: for each quote the owner chooses to give to an agency that asks about Team, add an observed row to the research log for whichever option is quoted: accepted or declined, with the price. The owner sets before starting which option is quoted, how many quotes make a result and what would count as one.
2. For uncertainty 4: in the next research round, ask each agency for its seat count, show it the bill under an option the owner chooses for that count, and ask what it would do; log the answers as stated, not observed. The owner sets which option, who is asked and the criteria.
3. For uncertainty 4: record documents a month for A3 and B2, the two accounts above their allowance, to see whether their use is limited by the plan. The owner sets the period and the criteria.

Questions for the product owner
1. Would an option apply to existing accounts or only to new ones? Option 1 raises 7 of 10 current bills.
2. The payment fees row has no approver. Who approves it, and should margins include it?
3. A3 and B2 are above their allowance (120 of 100; 650 of 500). Is their use known to be limited by the plan, or not?

Draft for the product owner's decision. No price is recommended, nothing has been said or promised to any customer, and no package, price or billing record has been changed.
```
