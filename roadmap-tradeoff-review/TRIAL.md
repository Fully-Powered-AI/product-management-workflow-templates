# Trial: Roadmap tradeoff review on its own invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-10

The inputs are the invented example in `public/example.md` (the single sign-on request at "Company X"). No client data was used. This is the second run, made after the template's instruction block, output format and example were revised following a review. It was one pass, by the assistant that made those revisions, so it is not an independent run.

## Inputs used

The request, its two dependencies, the four goals, the two capacity rows, the ten-row roadmap export and the settings, all as given under "What the product owner supplies" in `public/example.md`. Settings: goals ranking owned by the Head of Product, date of the run 2 November 2026, window Q1, committed items not offered, started items not offered, margin 0.

## What came out

All thirteen parts of the output format were produced. The substance:

- Platform: capacity 45, committed 43 (R1 14, R2 8, R3 9, R8 7, R9 5), free 2, request 6, gap 4.
- Web: capacity 22, committed 19 (R4 10, R6 4, R7 5), free 3, request 3, gap 0, no margin left.
- Proposal: displace R3 Referral API (9 pw, G4, rank 4). It covers the gap of 4 and frees 5 pw more. No date assigned.
- Alternative: R9 Webhook retries (5 pw, G3, rank 3), 1 pw to spare.
- Not offered: R1 (commitment), R8 (commitment), R2 (in progress). Not offered covers Platform only, the team with a gap. Not counted: R11 (Idea), R5 (Q2).
- After the change: Platform committed 40 of 45, free 5; Web committed 22 of 22, free 0. With the alternative: Platform committed 44 of 45, free 1.
- Commitments touched: None.
- Unresolved: R5 depends on R3 (Web, Q2, 8 pw, Web lead); the security review has no owner and no effort; the identity provider test account (IT lead, 0.5 pw) has an owner with no capacity row.
- Goal check: request serves G2 (rank 2); R3 serves G4 (rank 4); the request does not rank below what it displaces. G4 keeps R6 in Q1. Goals left with no item in the window: None.
- Not known: owner and effort of the security review (product owner); whether the IT lead can give 0.5 pw (IT lead); whether R5 keeps its Q2 window (Web lead).
- Closing decision line for the product owner, with nothing changed, promised or sent.

## What was observed

Everything required was produced and no stop condition was reached. The figures match the worked arithmetic in the published example, and the template's reviewer checklist items 1 to 9 are satisfied on this output.

Honest limit of this trial: the run was made by the assistant that revised the template, with the published example open. The figures were recomputed from the inputs, but the match with the example is weaker evidence than a blind run by someone else would be.

Differences from the published example: only wording. This run dated "Prepared" with the date of the run, which the revised settings supply and which is the same day as the export. Not offered lists the Platform items only, and Not counted lists R11 and R5, as the revised template says.

Every fact in both outputs is in the inputs. The company description in the example's introduction is framing and does not appear in the output.

Where the instructions were still ambiguous or needed a guess:

1. The identity provider test account has an owner role, not a team, so "an owner whose team has no capacity row" does not strictly apply; this run followed the unresolved-dependencies step and listed it.
2. The "After the change" line is shown for the team with the gap in the format, but the example also shows Web, which has no gap. This run followed the example.
3. Whether "no margin left" should also be said for a team with a gap of 0 when a margin above zero is set and free is larger than the request but smaller than request plus margin. The revised definition covers only the exact-equality case; this run had margin 0 and did not meet it.
4. The acceptance tests are marked as proposed and not run; this trial exercised tests 1 to 6 in effect (the normal request, the counting rule, zero margin, offered only where allowed, the dependent item, the unowned dependency). Tests 7 to 10 were not tried.

## Note added after a later revision (10 November 2026)

After this run, a reviewer's minor points led to small wording changes. The template now says that the "After the change" line covers every team the request touches (ambiguity 2), that an owner with no capacity row is listed (ambiguity 1), and that "no margin left" is printed only when the gap is 0 and free equals the request plus the margin, a free figure below that giving a gap above 0 (ambiguity 3). The "Proposed revision" format line now allows one line per displaced item, and the published example's wording was aligned to the format. The run recorded above was not repeated and its record is unchanged; it is still a single pass by the assistant that revised the template, and a blind re-run by someone else has not been made.
