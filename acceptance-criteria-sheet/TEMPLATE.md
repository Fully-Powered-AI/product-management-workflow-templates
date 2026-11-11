# Acceptance criteria sheet

Capability template, version 0.1.0.

## Purpose

Turn one story into a sheet of testable criteria: what must happen, what must happen when something goes wrong, and what must happen at the edges. Each criterion names the rule or design state it answers, so a developer can build from it and a tester can check it. Words that cannot be tested as written, and questions only the product owner can answer, are listed instead of guessed at. The assistant prepares the sheet. It writes no code or tests, and the product owner confirms every line.

## When to use it and when not to

Use it when one story is ready for refinement or about to be handed to a developer or an agency, and the rules and design for it exist.

Do not use it for a whole feature at once; split it into stories first. Do not use it to prepare an operations pilot (see pilot acceptance-test preparation), to check a finished project before handover (see project handover readiness check), or to judge a change to agreed scope (see scope change impact review). Do not use it to invent the business rules: if there are none and the story depends on them, the sheet says so.

## Roles

- **Runs it and confirms the criteria:** the product owner.
- **Answers feasibility questions and agrees the sheet:** engineering, whether in-house or the agency.
- **Agrees how each criterion will be checked:** the test owner, who may be a tester, the owner or the developer's reviewer.
- **Supplies design states and wording:** the designer, or the owner where there is none.

## Inputs

Ask for them under these labels. If they arrive mixed together, ask which is which before starting.

1. **Story:** who wants what, and why. If the person, the action or the purpose is missing, stop.
2. **Business rules:** a numbered list, one rule per line. Default labels R1, R2 and so on; keep the owner's own numbers if they have them. If none are supplied, continue and print "Not supplied: business rules" on the sheet.
3. **Design states:** the screens or steps the user sees, one per line, with any message wording. Default labels S1, S2. If none are supplied, continue and say so; every expected result is then marked "wording not supplied".
4. **Known failure conditions:** what is known to go wrong or be unavailable, one per line. Default labels F1, F2. If none are supplied, continue and say so.
5. **Optional:** a list of words your team has agreed are vague, a glossary, and the maximum number of criteria for one story.

These are free text, not an export. There are no column headers to match; the labels above are the only thing to check for. If a rule, state or failure carries no label, number it in the order given and show the numbering back on the sheet.

## The procedure

1. **Restate the story** in one line: who, does what, to get what. If it holds two separate outcomes, say so, and offer to split it. Continue only with the part the owner picks.
2. **Number the inputs.** Keep the owner's labels. Count rules, states and failures for the "Inputs read" line.
3. **Expected behaviour.** Write one criterion for each result the story promises, and at least one for every rule that shapes a result. Each criterion has a starting point (Given), one action (when) and one result a person could see or measure (then). Use real figures from the inputs in the results, and work every figure out. The inputs often give no example amounts (a basket, a balance, a quantity, a date inside a window). You may choose a plain amount so that a rule can be shown working. Mark every amount or date you chose with an asterisk (*) and list them all on the "Scenario amounts chosen" line; figures worked out from a chosen amount follow it and need no mark. You may choose scenario amounts only. Never choose a rule, a limit, a message, an outcome or which of two things wins; if a rule needs a figure that was not given, do not invent it, make it a question. If a criterion is only partly unclear, write the part the inputs settle, put the open part in a question and mark the whole criterion blocked.
4. **Error cases.** For each known failure, and for each way the user's input could be wrong that the story allows (nothing entered, not recognized, out of range, not allowed, repeated), write a criterion. State what the user sees, quoting the design's wording where it has some, and what must not happen: no charge, no lost entry, no change to what was already saved. If the design has no wording or state for a case, write the criterion, mark it blocked, and ask.
5. **Edge cases.** Go through these categories and write a criterion for each that applies: exactly at a limit, one step either side of it, none, one, many, the same thing twice, two people at once, time and time zone, a different kind of user, interrupted halfway. Treat every stated limit, including both ends of a date range, as its own limit. If a criterion depends on a date or time at or next to a limit and the inputs do not say whose clock or time zone decides, mark it blocked and ask. If the story has no collection, read none, one and many as the thing the rules count (for example codes per order) and say which you used. Any category that does not apply goes on the "considered and not relevant" line with a reason taken from the inputs.
6. **Vague words.** Search the story, rules, design wording and known failures for words that cannot be tested as written. Defaults: fast, quickly, easy, intuitive, simple, clear, secure, appropriate, reasonable, soon, recent, large, small, user-friendly, "and so on", "as needed", plus the team's own list. A failure condition with no limit stated, such as "does not answer", "is slow" or "is unavailable", is also on the list. List each with a question that would make it testable (a number, a limit or a named condition). Never choose the number. A criterion that depends on the word is marked blocked.
7. **Conflicts.** If two inputs disagree (a rule against a design state, or two rules together), list both and the ids. Do not decide which wins.
8. **Coverage.** For every rule, state and failure, list the criteria that answer it. Anything with none is printed under "No criterion".
9. **Questions.** Gather everything only the owner can settle, one question each, numbered. Each blocked criterion points to its question.
10. **Count and close.** Count the criteria, how many are ready to confirm and how many are blocked. If there are more than [your maximum criteria per story, default 15], add a split suggestion that names which criteria would go to which part; if the story cannot sensibly be split, say so instead.
11. **Print.** Use the output format exactly. Print "None." in any empty section. Leave the confirmation block empty.

## Exceptions and stop conditions

- **The story has no user, no action or no purpose:** stop and say which is missing.
- **The story is really several stories:** say so and wait for the owner to pick one.
- **A criterion cannot be written without making up a figure, message or rule:** write it as blocked with a question; never fill the gap.
- **Two inputs conflict:** list the conflict; do not resolve it.
- **A vague word cannot be made testable from the inputs:** list it under "Terms that need a number".
- **Asked to write code, test scripts or automated tests, to mark a criterion confirmed, to decide an open question, or to send the sheet to a developer:** decline. The owner confirms and sends.
- **Asked to cover legal, contract or employment terms in the story:** decline that part and mark it for the owner.
- **No example amounts in the inputs:** choose plain ones, mark each with an asterisk and list it; never choose a rule, limit, message or outcome.

## Output format

```
ACCEPTANCE CRITERIA SHEET: [story name]

Story: [who] [does what] [to get what].

Inputs read: [n] rules (R1 to Rn), [n] design states (S1 to Sn), [n] known failures (F1 to Fn). Not supplied: [list, or "nothing"].

Scenario amounts chosen (marked *): [each amount or date you picked, or "None."] These are examples picked to show the rules working, not taken from the inputs; the owner may replace them.

Expected behaviour:
[AC-n] [rule and state ids]. Given [starting point]; when [action]; then [observable result]. [Blocked by Q or T id, if it is.]

Error cases:
[ERR-n] [ids]. Given [...]; when [...]; then [what the user sees and what must not happen]. [Blocked by ...]

Edge cases:
[E-n] [ids]. Given [...]; when [...]; then [...]. [Blocked by ...]

Edge categories considered and not relevant: [category: reason, or "None."]

Terms that need a number:
[T-n]. [Word], in [where it appears]. Question: [what condition would make it testable]. [Or "None."]

Conflicts between inputs: [R/S/F ids that disagree and how, or "None."]

Coverage:
[each R, S and F id followed by the criteria that answer it]
No criterion: [ids with none, or "None."]

Questions for the owner:
[Q-n]. [Question only the owner can settle.] [Or "None."]

Counts: [n] criteria. [n] ready to confirm. [n] blocked ([ids]).
[Only if the count is above the maximum: Split suggestion: [how the story could divide and which criteria go to which part, or why it cannot sensibly be split].]

Confirmation: Proposed by the assistant, not yet agreed.
Product owner: ______  Engineering: ______  Test owner: ______  Date: ______

This sheet writes no code or tests and changes no records.
Every criterion is a proposal until the product owner confirms it.
```

## Reviewer checklist

1. Every criterion has a starting point, one action and one visible or measurable result. (Test owner)
2. Every figure in the sheet is correct and traces to a rule or an input, or is marked * as a scenario amount chosen. (Product owner)
3. Every rule, design state and failure appears in Coverage, or is named under "No criterion". (Product owner)
4. No criterion was written from a rule, limit, message or outcome that the inputs do not contain; only scenario amounts are chosen, and each is marked *. (Product owner)
5. Each blocked criterion points to a question or term, and each question needs the owner. (Product owner)
6. The edge categories that do apply are all present, including both ends of any date range, and the ones left out have a reason. A count above the maximum has a split suggestion. (Engineering)
7. Nothing says how the feature should be built. (Engineering)
8. The confirmation block is blank until the three people have agreed. (Product owner)

## Acceptance tests

Proposed tests. Test 1 was run once, by an assistant, on an earlier form of this template; that record is in `public/trial.md`, and the template has changed since and has not been run again. Tests 2 to 9 have not been run.

1. **Worked example.** Use the invented example in this folder. Expected: criteria with the same figures ($6.00 and $54.00 on a $60.00* basket; a $25.00 cap on $400.00*; $4.00 at exactly $40.00), amounts picked by the assistant marked * and listed, the twelve blocked criteria the example lists, a criterion at each end of the SAVE10 date range and one step above the $40.00 and $250.00 limits, a split suggestion because 21 is above 15, and a coverage line with no gaps.
2. **Missing rule figure.** Remove R4's $40.00 from the example. Expected: no minimum is invented; the minimum criteria are blocked with a question.
3. **Vague word.** Add "an intuitive Remove link" to S2. Expected: a term that needs a number, and a blocked criterion.
4. **Conflict.** Change R5 to a 15% discount while a design state reads "−$6.00" on $60.00. Expected: a conflict naming both; neither chosen.
5. **No failures supplied.** Remove F1 and F2. Expected: the sheet says so and still covers the input errors the story allows.
6. **Two stories in one.** Add "and email me a receipt". Expected: the sheet says there are two outcomes and waits for the owner.
7. **Asked for code.** Ask for the test scripts. Expected: declines.
8. **Asked to confirm.** Ask the assistant to fill in the confirmation block. Expected: declines; the block stays blank.
9. **No example amounts.** Supply rules with no basket sizes. Expected: any amount used is chosen plainly, marked * and listed; no rule, limit or message is chosen.

## Instructions for the AI assistant

```
You prepare an acceptance criteria sheet for one story, for the product
owner. You do not write code or test scripts. You never mark a criterion
confirmed, decide an open question, change any record, or send the sheet
to anyone. The product owner confirms every line and sends the sheet.

The user will supply: the story; the business rules, numbered; the design
states, numbered, with any message wording; the known failure conditions,
numbered. If they arrive unlabelled, ask which is which. If the story has no
user, action or purpose, stop and say which is missing. If rules, states or
failures are missing, say so on the sheet and continue.

1. Restate the story in one line: who, does what, to get what. If it holds
   several outcomes, say so and wait for the owner to choose one.
2. Keep the owner's labels (R, S, F); number anything unlabelled in order
   and show the numbering. Count each kind.
3. Expected behaviour: one criterion per promised result, and at least
   one for every rule that shapes a result. Each has Given, when, then,
   with one result a person could see or measure. Use figures from the
   inputs and work each one out. If the inputs give no example amounts,
   you may choose plain amounts or dates, mark each with * and list them on the
   "Scenario amounts chosen" line. Never choose a rule, limit, message or
   outcome, and never invent one. If a criterion is only partly unclear,
   write the part the inputs settle, put the rest in a question and mark
   it blocked. If a figure is needed that was not given, ask.
4. Error cases: one for each known failure and each way the user's input
   could be wrong that the story allows. State what the user sees (quote
   the design wording if there is some) and what must not happen. No
   wording or state in the design: write it, mark it blocked, ask.
5. Edge cases: at a limit, either side of it, none, one, many, the same
   thing twice, two people at once, time and time zone, a different kind
   of user, interrupted halfway. Both ends of a date range are limits. If
   a criterion depends on a date or time at or next to a limit and the
   inputs do not say whose clock decides, mark it blocked and ask. With no collection, read none,
   one and many as what the rules count. List any category that does not
   apply with a reason from the inputs.
6. Vague words: search for words that cannot be tested (fast, quickly,
   easy, intuitive, simple, clear, secure, appropriate, reasonable, soon,
   recent, large, small, user-friendly, "and so on", "as needed", plus the
   team's own), and for failure conditions with no limit stated, such as
   "does not answer". List each with a question that would make it
   testable. Never pick the number. Mark dependent criteria blocked.
7. If two inputs conflict, list both with their ids. Do not decide.
8. Coverage: for every rule, state and failure, the criteria that answer
   it. Print any with none under "No criterion".
9. Gather what only the owner can settle into numbered questions. Each
   blocked criterion names its question or term.
10. Count the criteria, those ready to confirm and those blocked. If there
    are more than [your maximum criteria per story, default 15], add a
    split suggestion saying which criteria go to which part, or say the
    story cannot sensibly be split.
11. Use the output format exactly. Print "None." in any empty section.
    Leave the confirmation block empty.

Decline requests to write code or tests, to confirm a criterion, or to
answer an open question for the owner. Decline legal, contract or
employment terms in the story and mark that part for the owner.
```

## What to customize

- How stories are written, and how criteria and questions are numbered.
- The team's own list of vague words.
- [your maximum criteria per story, default 15], in the instructions and in step 10.
- Who counts as engineering and test owner on each team.
- Whether the sheet quotes the design's wording or links to it.
- Where the confirmed sheet is kept, and who sends it to the developer or agency.
- Which files the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 10 November 2026. Written by Fully Powered AI. Tried once on its invented example; changed after an independent review the same day and not run again (see `public/trial.md`). Not yet tested in a client environment.
