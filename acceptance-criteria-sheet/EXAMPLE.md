# Acceptance criteria sheet: an invented example

*Illustrative example with invented data.* The company, the shop and every figure are made up. A product owner at an invented online garden shop, Larkfield Garden Supplies, is handing one story to an outside developer.

## What the person supplies

**Story:** As a shopper, I want to enter a discount code at checkout so that I see my savings before I pay, and quickly.

**Business rules** (numbered by the owner):

- R1. Codes are not case sensitive.
- R2. One code per order.
- R3. The code SAVE10 is valid from 1 March 2027 to 31 March 2027, both days included.
- R4. The code needs an items subtotal of at least $40.00. Items subtotal means item prices before shipping, with gift cards left out.
- R5. The code takes 10% off the items subtotal, with the discount capped at $25.00. Shipping is never discounted.

**Design states:**

- S1. Checkout with an empty code field and an Apply button.
- S2. Code applied: a line reading "Code SAVE10: −$6.00" with a Remove link, and the new items total.
- S3. Code refused: a message under the field. The design words three messages: "This code has expired." "Spend $40 or more on items to use this code." "That code isn't valid."

**Known failures:**

- F1. A code used after its end date.
- F2. The service that checks codes does not answer.

## The sheet

```
ACCEPTANCE CRITERIA SHEET: Enter a discount code at checkout

Story: A shopper enters a discount code at checkout to see their savings before paying, quickly.

Inputs read: 5 rules (R1 to R5), 3 design states (S1 to S3), 2 known failures (F1 to F2). Not supplied: nothing.

Scenario amounts chosen (marked *): $60.00, $400.00, $30.00, a $25.00 gift card, $44.55 and the date 10 March 2027. These are examples picked to show the rules working, not taken from the inputs; the owner may replace them. Amounts and dates exactly at a limit, or one cent or one day beside it ($40.00, $39.99, $40.01, $250.00, $250.01, 28 February 2027 and 1 April 2027), are worked out from the rules, not chosen, and carry no mark.

Expected behaviour:
AC-1 [R3, R5, S1, S2]. Given the checkout shows an empty code field, items subtotal $60.00* and today is 10 March 2027*; when the shopper enters SAVE10 and taps Apply; then the page shows "Code SAVE10: −$6.00" with a Remove link, the items total is $54.00 and shipping is unchanged.
AC-2 [R5]. Given items subtotal $400.00*; when SAVE10 is applied; then the discount is $25.00, not $40.00, and the items total is $375.00.
AC-3 [R1]. Given the same starting point as AC-1; when the shopper enters "save10" in lower case; then the result is the same as AC-1.
AC-4 [S1, S2]. Given SAVE10 applied to items subtotal $60.00*; when the shopper taps Remove; then the discount line is no longer shown and the items total is $60.00. What the code field and Apply button show afterwards is Q-1. Blocked by Q-1.
AC-5 [story]. Given any valid code; when the shopper taps Apply; then the result appears within [T-1] seconds. Blocked by T-1.

Error cases:
ERR-1 [R3, F1, S3]. Given today is 1 April 2027, the day after the end date, and items subtotal $60.00*; when SAVE10 is entered; then the message "This code has expired." shows and the items total stays $60.00. Whose clock decides that it is already 1 April is Q-6. Blocked by Q-6.
ERR-2 [R4, S3]. Given items of $30.00* and a gift card of $25.00* in the basket; when SAVE10 is entered; then the items subtotal is $30.00, the message "Spend $40 or more on items to use this code." shows and nothing is discounted.
ERR-3 [S3]. Given any basket; when a code that does not exist is entered; then the message "That code isn't valid." shows and the total is unchanged.
ERR-4 [R2]. Given SAVE10 already applied; when the shopper enters a second code; then the order does not carry two codes. What the shopper sees and which code stays is Q-2. Blocked by Q-2.
ERR-5 [F2]. Given the code service does not answer; when the shopper taps Apply; then what the shopper sees and whether they can still pay is Q-3. Blocked by T-2, Q-3.
ERR-6 [R3, S3]. Given today is 28 February 2027, the day before the start date; when SAVE10 is entered; then no discount is applied. The message is Q-4, because the design words only "This code has expired." Whose clock decides that it is still 28 February is Q-6. Blocked by Q-4, Q-6.

Edge cases:
E-1 [R4, R5]. Given items subtotal exactly $40.00; when SAVE10 is applied; then it is accepted, the discount is $4.00 and the items total is $36.00.
E-2 [R4, S3]. Given items subtotal $39.99; when SAVE10 is entered; then it is refused with "Spend $40 or more on items to use this code."
E-3 [R5]. Given items subtotal exactly $250.00; when SAVE10 is applied; then the discount is $25.00 and the items total is $225.00.
E-4 [R5]. Given items subtotal $44.55*; when SAVE10 is applied; then the discount is $4.455 before rounding, so the displayed amount is Q-5. Blocked by Q-5.
E-5 [R3]. Given an order placed late on 31 March 2027, the last day; when SAVE10 is entered; then whether it is accepted depends on Q-6. Blocked by Q-6.
E-6 [R3]. Given an order placed just after midnight at the start of 1 March 2027, the first day; when SAVE10 is entered on a qualifying basket; then whether it is accepted depends on Q-6. Blocked by Q-6.
E-7 [S1]. Given the code field is empty; when the shopper taps Apply; then the result is Q-7. Blocked by Q-7.
E-8 [R2]. Given SAVE10 already applied; when the shopper enters SAVE10 again; then the result is Q-8. Blocked by Q-8.
E-9 [R4, R5]. Given items subtotal $40.01; when SAVE10 is applied; then it is accepted, and the discount shown is Q-5, because 10% is $4.001. Blocked by Q-5.
E-10 [R5]. Given items subtotal $250.01; when SAVE10 is applied; then the discount is $25.00, because 10% is $25.001 and the cap applies, and the items total is $225.01.

Edge categories considered and not relevant: Two people at once: no rule limits how many orders may use a code. A different kind of user: the story and rules name only a shopper. Interrupted halfway: the inputs describe applying a code as one tap on Apply. One or many items: no rule depends on the number of items, only on the subtotal. (None, one and many are read as codes per order: E-7, AC-1, ERR-4.)

Terms that need a number:
T-1. "quickly", in the story. Question: how many seconds from tapping Apply to the result showing, and on what connection?
T-2. "does not answer", in F2. Question: after how many seconds does the shop treat the code service as not answering?

Conflicts between inputs: None.

Coverage:
R1 AC-3. R2 ERR-4, E-8. R3 AC-1, ERR-1, ERR-6, E-5, E-6. R4 ERR-2, E-1, E-2, E-9. R5 AC-1, AC-2, E-1, E-3, E-4, E-9, E-10.
S1 AC-1, AC-4, E-7. S2 AC-1, AC-4. S3 ERR-1, ERR-2, ERR-3, ERR-6, E-2.
F1 ERR-1. F2 ERR-5.
No criterion: None.

Questions for the owner:
Q-1. After Remove, does the page return to the empty code field and Apply button, or show something else? The design does not say.
Q-2. When a second code is entered while one is applied, what does the shopper see, and which code stays?
Q-3. When the code service does not answer, what does the shopper see, and may they pay without the code?
Q-4. What message shows before 1 March 2027? The design words only "This code has expired."
Q-5. How is a half cent rounded when the discount is worked out?
Q-6. Do the SAVE10 dates run on the shop's clock or the shopper's? Which time zone is the shop's? Does 31 March end at midnight, and does 1 March begin at midnight?
Q-7. What happens if Apply is tapped with nothing typed?
Q-8. What happens if SAVE10 is entered again while it is already applied?

Counts: 21 criteria. 9 ready to confirm. 12 blocked (AC-4, AC-5, ERR-1, ERR-4, ERR-5, ERR-6, E-4, E-5, E-6, E-7, E-8, E-9).
Split suggestion: 21 is more than 15. The story could divide into three: applying and removing a valid code (AC-1 to AC-4, E-1, E-3, E-4, E-9 and E-10, 9 criteria); refusing a code or entering one twice (ERR-1 to ERR-4, ERR-6, E-2 and E-5 to E-8, 10 criteria); and what happens when the code service is slow or does not answer (AC-5 and ERR-5, 2 criteria). Each part is within 15.

Confirmation: Proposed by the assistant, not yet agreed.
Product owner: ______  Engineering: ______  Test owner: ______  Date: ______

This sheet writes no code or tests and changes no records.
Every criterion is a proposal until the product owner confirms it.
```

Arithmetic behind the figures: 10% of $60.00 is $6.00, leaving $54.00. 10% of $400.00 is $40.00, above the $25.00 cap, so $25.00 applies and $375.00 remains. 10% of $40.00 is $4.00, leaving $36.00. 10% of $250.00 is $25.00, equal to the cap, leaving $225.00. 10% of $40.01 is $4.001. 10% of $250.01 is $25.001, above the cap, so $25.00 applies and $225.01 remains. 10% of $44.55 is $4.455. The gift card is left out of the basket's $30.00 items subtotal, which is below $40.00. The amounts marked * are chosen for the scenarios; the rest follow from the rules. The sheet has 21 criteria: 5 expected behaviours, 6 error cases and 10 edge cases; 9 are ready and 12 blocked.
