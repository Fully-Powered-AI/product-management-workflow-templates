# Roadmap tradeoff review: an invented example

*Illustrative example with invented data.* An invented 30-person software company, Company X, is asked for single sign-on in the middle of its first quarter. Every name, item and figure below is made up. Effort is in person-weeks (pw).

## What the product owner supplies

**The request, as typed by the product owner**

- Request: Single sign-on for business accounts. Asked by: Head of Sales. Serves goal: G2. Date the asker stated: none.
- Estimates: Platform team 6 pw; Web team 3 pw. Estimates from the Platform lead and the Web lead.

**Dependencies the request brings** (`Dependency, Owner, Effort (pw), Needed By Team`)

```
Security review of login changes,,,Platform
Identity provider test account,IT lead,0.5,Platform
```

**Goals** (`Goal, Rank, Statement`)

```
G1,1,Keep existing customers
G2,2,Win larger accounts
G3,3,Make first use easier
G4,4,Grow through referrals
```

**Capacity for window Q1** (`Team, Window, Capacity (pw)`)

```
Platform,Q1,45
Web,Q1,22
```

**Roadmap export** (`ID, Item, Team, Status, Window, Effort Remaining (pw), Depends On, Goal, Committed To, Owner`)

```
R1,Billing export v2,Platform,Planned,Q1,14,,G1,Customer A pilot,Platform lead
R2,Audit log,Platform,In progress,Q1,8,,G2,,Platform lead
R3,Referral API,Platform,Planned,Q1,9,,G4,,Platform lead
R4,Mobile onboarding refresh,Web,Planned,Q1,10,,G3,,Web lead
R5,Referral dashboard,Web,Planned,Q2,8,R3,G4,,Web lead
R6,Referral landing page,Web,Planned,Q1,4,,G4,,Web lead
R7,Team invite flow,Web,In progress,Q1,5,,G3,,Web lead
R8,Data retention settings,Platform,Planned,Q1,7,,G1,Customer B renewal,Platform lead
R9,Webhook retries,Platform,Planned,Q1,5,,G3,,Platform lead
R11,Public status page,Platform,Idea,Q1,6,,G3,,Platform lead
```

**Settings:** Product owner; goals ranking owned by the Head of Product; window Q1; date of the run 2 November 2026; roadmap export dated 2 November 2026; committed items may not be offered; started items may not be offered; margin to keep free: 0 pw.

## What comes out

```
ROADMAP TRADEOFF REVIEW: Single sign-on for business accounts

For: Product owner. Window: Q1. Prepared 2 November 2026 from the roadmap export of 2 November 2026.

The request: Single sign-on for business accounts, asked by Head of Sales, serves G2 (Win larger accounts, rank 2). Effort by team: Platform 6 pw, Web 3 pw. Date the asker stated: none supplied. Left out of the figures: security review of login changes (effort not supplied); identity provider test account, 0.5 pw (IT lead, no capacity row).

Capacity by team (pw):
- Platform: capacity 45, committed 43 (R1 14, R2 8, R3 9, R8 7, R9 5), free 2, request 6, gap 4.
- Web: capacity 22, committed 19 (R4 10, R6 4, R7 5), free 3, request 3, gap 0. No margin left.

Proposed revision:
- Platform: displace R3 Referral API (9 pw, goal G4, rank 4). Covers the gap of 4 and frees 5 pw more. No new date is assigned; it needs its own decision.
- Web: none needed.

Alternatives that also cover the gap: Platform: R9 Webhook retries (5 pw, goal G3, rank 3), leaving 1 pw to spare.

Not offered (teams with a gap only): R1 (commitment: Customer A pilot); R8 (commitment: Customer B renewal); R2 (in progress). Not counted (Idea, Done, Cancelled or other window): R11 (status Idea); R5 (window Q2).

After the change (pw): Platform committed 40 of 45, free 5. Web committed 22 of 22, free 0. With the alternative instead: Platform committed 44 of 45, free 1.

Commitments touched: None. R3 and R9 carry no Committed To entry.

Dependencies unresolved:
- R5 Referral dashboard (Web, Q2, 8 pw, Web lead) depends on R3, which the proposal displaces. The alternative leaves R5 intact.
- Security review of login changes (needed by team: Platform): no owner and no effort supplied.
- Identity provider test account (IT lead, 0.5 pw): the IT lead has no capacity row.

Goal check: The request serves G2 (rank 2); the proposed displaced item serves G4 (rank 4). G4 still has R6 in Q1. Goals left with no item in the window: None.

Not known:
1. Who owns the security review of login changes, and how many pw it takes. Who can answer: Product owner.
2. Whether the IT lead can give 0.5 pw to the test account in Q1. Who can answer: IT lead.
3. Whether R5 keeps its Q2 window if R3 moves. Who can answer: Web lead.

Decision for Product owner: choose the proposal, an alternative, neither, or a smaller request, and set any new date for displaced work. Teams confirm their own estimates. Nothing is changed in the tracker, promised to anyone or sent.
```

How each figure comes from the inputs: Platform committed is 14 + 8 + 9 + 7 + 5 = 43 (R11 is an idea and R5 is in Q2, so neither counts and both are listed under Not counted); free is 45 − 43 = 2; the gap is 6 − 2 = 4. Web committed is 10 + 4 + 5 = 19; free is 22 − 19 = 3; the gap is 3 − 3 = 0, with free exactly equal to the request, so no margin is left. After the proposal Platform is 43 − 9 + 6 = 40. With the alternative it is 43 − 5 + 6 = 44. Web after is 19 + 3 = 22.
