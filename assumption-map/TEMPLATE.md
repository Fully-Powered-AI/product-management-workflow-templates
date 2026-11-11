# Assumption map

Capability template, version 0.1.0.

## Purpose

Help a product owner see what a plan is standing on. The product owner lists the plan's items and the beliefs they depend on, and supplies the evidence that exists. The assistant ties each belief to the plan items that depend on it, marks each belief held, thin, contradicted or none by a fixed rule, ranks the beliefs that are not held, and, for the first few, offers a cheap test suited to the kind of belief. The product owner chooses what to test and sets the learning criteria. The assistant prepares; it never invents evidence, rates a belief, says whether a belief is true, picks a test for the owner, runs a test, forecasts, or sends, posts, contacts or changes anything.

## When to use it and when not to

Use it when a concept has become a plan with a date: before a build is approved or a launch committed, when a plan item changes, and again when a test result comes back.

Do not use it:

- to review the commercial model of a whole business or line; use Business model assumptions review for that;
- to imagine a decision failing before it is made, with a group in a room; use Premortem before a decision;
- to judge the wording of an offer to a buyer; use Offer review;
- for a forecast of demand, revenue, cost or delivery date; this capability makes none;
- for a legal question about a rule or a partner's terms; the map can list it as a belief, and the right adviser answers it;
- to judge a person, including whether to hire someone.

## Roles

- **Product owner:** owns the decision. Writes the brief, confirms every belief, rates what happens if each is false, marks each piece of evidence as supporting or contradicting, chooses what to test and sets the learning criteria.
- **Preparer:** the person who types the lists and runs the assistant. Often the product owner, or a product analyst acting for them.
- **Evidence owners:** whoever holds the records behind an item, such as support, sales, engineering or finance. They confirm the evidence is as typed.

## Inputs

1. **The brief,** from the product owner: the concept; the owner's role; the decision this map serves and its date; the review date; any context worth knowing. If the concept is missing, stop and ask. Anything else missing is printed as "not stated".
2. **The plan,** one item per row. Default columns: `id,plan_item`. Ids are the owner's, such as P01, and are kept as typed.
3. **The beliefs,** one per row. Default columns: `id,belief,type,plan_items,if_false,test_idea`.
   - `type` is one of: **customer** (people have the problem or want the outcome), **behaviour** (they will do the thing: sign up, switch, pay, keep using it), **delivery** (we can build or run it by the date, at the cost), **environment** (something outside our control allows it or holds still: a partner, a platform rule, the market, timing).
   - `plan_items` lists the plan ids that depend on the belief, separated by semicolons.
   - `if_false` is one of: **stops** (the plan cannot go ahead as written), **changes** (it goes ahead with a change to scope, price or date), **small** (a minor change).
   - `test_idea` is optional: a test the owner already has in mind. Ids are the owner's, such as B01.
4. **The evidence,** one item per row. Default columns: `id,evidence,kind,date,beliefs,direction`.
   - `kind` is one of: **behaviour** (people did something, such as paid, signed up, used or switched, as shown by orders or logs), **measured** (counted, timed or tested, from records, a written source or a trial), **said** (someone told us, in an interview, survey or call), **estimate** (our own or someone else's estimate).
   - `date` is the year and month, or the full date, of the observation.
   - `beliefs` lists the belief ids the item bears on, separated by semicolons. Blank means it is tied to none.
   - `direction` is one of: **supports**, **contradicts**, **unclear**. One item has one direction for all the beliefs listed; the owner splits it into two rows where it does not.
   - Ids are the owner's, such as E01.
5. **Settings.** Defaults: [your evidence age limit] is 12 months; [your test count] is 3. If none are given, use the defaults and say so.

If a header in any list does not match these defaults, stop and ask which column is which; do not guess. The assistant works only from what is typed or pasted. It needs no connection to any system, and it never asks for a password or a login code.

## The procedure

1. **Check the inputs.** The concept must be named. Headers must match. Ids must be unique within each list. Every plan id in a belief, and every belief id in an evidence row, must exist. `type`, `if_false`, `kind` and `direction`, where given, must be among the allowed values. A blank `if_false` is allowed (see step 7); a blank `type` or `direction` is not. If anything fails, stop and list the rows. A blank `kind` is allowed: the item is treated as not supporting a held mark and a question is asked.
2. **Tie the lists together.** For each belief, its plan items are the ids it lists; its reach is how many different plan items that is. For each plan item, its beliefs are those that list it. For each belief, sort its evidence into three lists in id order: for (supports), against (contradicts), neither way (unclear).
3. **Mark each belief,** by the first rule that fits:
   - **CONTRADICTED:** at least one item against it has kind behaviour or measured. An undated item against it still counts.
   - **HELD:** at least one item for it has kind behaviour or measured, a date, and a date no more than [your evidence age limit] months before the review date, and the belief is not CONTRADICTED.
   - **THIN:** it has at least one item of any kind or direction, and is neither CONTRADICTED nor HELD.
   - **NONE:** it has no evidence rows.

   Months are whole months: subtract the months and ignore the day; if the review date is not stated, treat every dated item as in date and say the age was not checked. Do not judge whether evidence is good or enough; the rule is the only test. Do not change a mark because the evidence line sounds confident, and do not change a direction the owner gave.
4. **Say what is missing** for every belief that is not HELD, in one line:
   - NONE: "No evidence supplied."
   - CONTRADICTED: "Contradicted by" the item ids with their kinds.
   - THIN: "No supporting behaviour or measured item within [your evidence age limit] months." Add "Latest supporting item: [id], [date], [n] months before the review date." when a supporting behaviour or measured item exists but is out of date. Add "Points against: [ids with kinds]." when any item is against it.
   - For a HELD belief print "Nothing flagged."
5. **Show the plan.** For each plan item, in the order given, its beliefs in id order with their marks, or "No belief written." Count plan items; those resting only on HELD beliefs; those exposed (at least one belief not HELD); those with no belief written.
6. **Count beliefs** by mark. Then list the evidence rows tied to no belief.
7. **Rank the beliefs that are not HELD.** A belief with a blank `if_false` is not ranked; list it as "Not yet rated". Order by: `if_false` (stops, then changes, then small); then mark (CONTRADICTED, then NONE, then THIN); then reach, highest first; then the lower id.
8. **Name a cheap test** for each of the first [your test count] ranked beliefs, in rank order. If the owner gave a `test_idea`, print it as typed; do not improve or replace it. If not, print the suggestion for the belief's type from the list below, labelled "Suggested", with the second choice on a line beginning "If that is not possible:". Print the learning criteria line as "owner to set"; never set it. List the ranked beliefs beyond the first few on a "Beyond the first" line.
9. **The suggested tests,** cheapest first for each type. Customer: (1) count what you already hold, such as tickets, sales notes or requests that raise the problem, over a stated period; (2) ask a few people who met the problem recently to describe the last time it happened and what they did. Behaviour: (1) ask a small number of real customers for a written commitment, such as a pre-order or a place on a sign-up list; (2) show the offer to a small group inside the live product and count who takes the step. Delivery: (1) a time-boxed trial of the exact step in doubt, run by the team that would build or run it, with the result written down; (2) ask that team to say in writing what they expect to go wrong and how they would find out. Environment: (1) read the published rules or terms for the exact point and note the passage; (2) put the question in writing to the person who owns the rule, which a person sends. A result moves a belief toward held only if it is something people did or something measured; what someone says does not.
10. **Open questions for the product owner,** in this order: one per plan item with no belief written, showing the plan item's words as a suggested belief ("It holds that: [plan item as typed]") for the owner to confirm; one per belief not rated; one per belief linked to no plan item; one per evidence row with no kind; one per supporting evidence row with no date; one per THIN belief whose latest supporting behaviour or measured item is out of date; one per item typed behaviour or measured whose line says "we think" or "we expect"; then one asking for the learning criteria of the beliefs given a test. State the facts and ask only what is missing. Recommend nothing. A suggested belief is never added to the list or ranked.
11. **The owner's choice:** one line for each belief given a test, with three empty boxes. Leave them empty.
12. **Return the map** to the preparer for the product owner.

## Exceptions and stop conditions

- **The concept is not named, or a header does not match:** stop and ask.
- **An id repeats, an id does not exist, or a value is outside the allowed ones:** stop and list the rows.
- **A plan item has no belief:** print "No belief written.", count it, and ask. Never write a belief into the lists.
- **Nothing is unheld:** print "None. Every rated belief is held." under the ranking and "None." under the tests and the choice line.
- **No belief has an `if_false`:** produce the plan, the beliefs and the questions, rank nothing, and ask for the ratings.
- **Evidence is tied to no belief:** list it, and ask nothing more about it.
- **An item says "we think" or "we expect" but is typed as behaviour or measured:** keep the owner's kind, and add a question asking whether the line describes something that happened.
- **Asked whether a belief is true, whether the plan will work, which belief matters most, or what to test:** decline; the marks follow the lists and the ranking follows the rule. The owner decides.
- **Asked to add evidence, find evidence, guess a rating or set the learning criteria:** decline and leave the wording empty.
- **Asked to run a test, contact a customer or partner, send a message, buy anything or change a record:** decline. A person does these once the owner has chosen.
- **Asked for a forecast of demand, revenue, cost or date:** decline.
- **The matter is a legal question, or about hiring or judging a person:** decline that part and say who should take it.
- **The inputs contain passwords, bank details or other private data:** do not repeat them; ask the preparer to remove them.

## Output format

```
ASSUMPTION MAP: [concept, in a few words]

Concept: [as stated].
Product owner: [role]. Decision this serves: [decision / not stated]. Decision date: [weekday date / not stated].
Context: [from the brief / not stated]
Review date: [weekday date / not stated]. Prepared from the plan, the beliefs list and the evidence list[; default settings]. No evidence has been added.

THE PLAN AND WHAT IT RESTS ON
[P id] [plan item as typed]
  Rests on: [B id and mark, one after another / No belief written.]
[one block per plan item, in the order given]
Plan items: [n]. Resting only on held beliefs: [n]. Exposed: [n]. With no belief written: [n].

BELIEFS, EVIDENCE HELD AND MISSING
[B id] [type]. [MARK]. [belief as typed]
  Plan items: [P ids / none]. If false: [Stops the plan / Changes the plan / Small change / not stated].
  For: [E id kind, date: evidence as typed; one per line / none].
  Against: [same / none].
  Neither way: [same / none].
  Missing: [the line from step 4 / Nothing flagged.]
[one block per belief, in id order]
Beliefs: [n]. Held [n], thin [n], contradicted [n], none [n].

EVIDENCE NOT TIED TO A BELIEF
[E id kind, date: evidence as typed / None.]

RANKED BELIEFS NOT YET HELD
Order: what happens if false, then the mark, then reach, then the id.
[rank]. [B id] [type]. [MARK]. [If false, as above]. Reaches [n] plan item[s]. [belief as typed]
[None. Every rated belief is held.]
Not yet rated: [B ids / none].

SUGGESTED CHEAP TESTS FOR THE FIRST [n]
[rank]. [B id] [belief as typed]
  Test: [the owner's test as typed / Suggested: the first choice for the type].
  [If that is not possible: the second choice. For a suggestion only.]
  Learning criteria: owner to set.
Beyond the first [n]: [B ids / none].
A behaviour or measured result moves a belief toward held.
What someone says does not.

OPEN QUESTIONS FOR THE [PRODUCT OWNER ROLE]
[n]. [P, B or E id, or "Learning criteria"]: [the facts]. [The question.]
[None.]

OWNER'S CHOICE
[B id] [ ] Test now  [ ] Later  [ ] Accept the risk
[None.]

Prepared for the [product owner role]'s decision. Nothing has been decided, tested, sent or changed. No evidence has been added.
```

## Reviewer checklist

1. Every plan item, belief and evidence row typed appears once, as typed. (Preparer)
2. Every mark follows the rule in step 3 from the evidence lists, and every month count is right. (Preparer)
3. No belief, rating, direction or evidence has been added or changed; suggested beliefs appear only in the questions. (Product owner)
4. The plan counts and the belief counts add up to the lists. (Preparer)
5. The ranking follows the stated order, and a belief with no `if_false` is not ranked. (Preparer)
6. Every test is the owner's, as typed, or labelled Suggested for the belief's type; no learning criteria is filled. (Product owner)
7. The choice boxes are empty, and only beliefs given a test have one. (Product owner)
8. Each piece of evidence is as it stands in the records behind it. (Evidence owners)

## Acceptance tests

Proposed tests. None has been run.

1. **Ordinary plan.** Six plan items, seven beliefs, eight evidence rows. Expected: all sections filled; marks, counts and ranking match a hand count.
2. **Said is not evidence.** A belief whose only support is two interviews. Expected: THIN, with the missing line.
3. **Contradicted by a measurement.** A contradicting measured item and a supporting behaviour item. Expected: CONTRADICTED.
4. **Estimate against.** A contradicting estimate and nothing else. Expected: THIN, with "Points against" and the estimate's id.
5. **Old support.** A supporting behaviour item fourteen months before the review date. Expected: THIN, the latest supporting item and its age printed, and one question.
6. **Undated support.** A supporting measured item with no date. Expected: not HELD, and one question.
7. **Plan item with no belief.** Expected: "No belief written.", counted, and one question showing the suggested wording; the suggestion is not ranked.
8. **Tie on rating and mark.** Two THIN beliefs that would stop the plan, with different reach. Expected: the one with more plan items first.
9. **Belief with no `if_false`.** Expected: not ranked, listed as not yet rated, one question.
10. **Unknown id.** An evidence row names a belief not in the list. Expected: stops and lists the row.
11. **Headers changed.** Beliefs headed `statement,kind`. Expected: stops and asks which column is which.
12. **Owner's own test.** A belief with a `test_idea`. Expected: printed as typed, not labelled Suggested, no second choice.
13. **Asked whether the belief is true.** Expected: declines and points to the mark and the evidence.
14. **Asked to add evidence.** "Assume customers like it." Expected: declines; the mark does not change.

## Instructions for the AI assistant

Paste this block as custom instructions, followed by the output format above.

```
You prepare an assumption map for a product owner. You tie each belief
the plan depends on to the plan items that depend on it, mark it held,
thin, contradicted or none by a fixed rule from the evidence supplied,
rank the beliefs that are not held, and offer a cheap test for the first
few. You never invent or search for evidence, rate a belief, say whether a
belief is true or the plan will work, choose a test for the owner, set the
learning criteria, forecast, run a test, or send, post, contact, buy or
change anything. The product owner decides; a person acts on the choices.

INPUTS. The brief (concept, owner's role, decision and date, review date,
context); the plan with columns id,plan_item; the beliefs with columns
id,belief,type,plan_items,if_false,test_idea; the evidence with columns
id,evidence,kind,date,beliefs,direction. If a header differs, stop and ask
which column is which. If the concept is missing, or a type or direction
is blank, stop and ask. type:
customer, behaviour, delivery, environment. if_false: stops, changes,
small (may be blank). kind: behaviour, measured, said, estimate (may be
blank). direction: supports, contradicts, unclear. plan_items and beliefs
hold ids separated by semicolons. If an id repeats, an id does not exist
or a value is outside these, stop and list the rows. Never ask for
passwords or login codes.

STEPS.
1. Reach of a belief = the number of different plan items it lists. Sort
   each belief's evidence, in id order, into for (supports), against
   (contradicts) and neither way (unclear).
2. Mark each belief by the first rule that fits. CONTRADICTED: an item
   against it has kind behaviour or measured (an undated one counts).
   HELD: an item for it has kind behaviour or measured, has a date, and
   is dated no more than 12 months before the review date (or the owner's
   [your evidence age limit]), and the belief is not CONTRADICTED. THIN:
   it has any evidence row and is neither. NONE: no evidence rows. Count
   whole months, ignoring the day. If the review date is missing, treat
   dated items as in date and say age was not checked. Never judge how
   good the evidence is, and never change a mark because it sounds sure.
3. Missing line for every belief that is not HELD. NONE: "No evidence
   supplied." CONTRADICTED: "Contradicted by" the ids with kinds. THIN:
   "No supporting behaviour or measured item within 12 months." plus
   "Latest supporting item: id, date, n months before the review date." if
   one exists but is out of date, plus "Points against: ids with kinds."
   if any item is against it. HELD: "Nothing flagged."
4. Show each plan item with its beliefs and marks, or "No belief written."
   Count plan items, those resting only on held beliefs, those exposed (at
   least one belief not held) and those with no belief written. Count
   beliefs by mark. List evidence tied to no belief.
5. Rank the beliefs that are not held: if_false (stops, changes, small),
   then mark (contradicted, none, thin), then reach, highest first, then
   lower id. A belief with a blank if_false is not ranked; list it under
   "Not yet rated".
6. For each of the first 3 ranked beliefs (or the owner's [your test
   count]), print the owner's test_idea as typed, or else the suggestion
   for its type, labelled Suggested, with the second choice on a line beginning
   "If that is not possible:". Customer: (1) count what you already
   hold, such as tickets, sales notes or requests that raise the
   problem, over a stated period; (2) ask a few people who
   met the problem recently to describe the last time and what they did.
   Behaviour: (1) ask a small number of real customers for a written
   commitment, such as a pre-order or a place on a sign-up list; (2) show
   the offer to a small group in the live product and count who takes the
   step. Delivery: (1) a time-boxed trial of the exact step in doubt, run
   by the team that would build or run it, result written down; (2) ask
   that team to say in writing what they expect to go wrong and how they
   would find out. Environment: (1) read the published rules or terms for
   the exact point and note the passage; (2) put the question in writing
   to the person who owns the rule, which a person sends. Print "Learning
   criteria: owner to set." and never fill it. List the remaining ranked
   beliefs on the "Beyond the first" line.
7. Open questions, in this order: each plan item with no belief (show
   "It holds that:" and the plan item as typed, as a suggestion only);
   each belief not rated; each belief linked to no plan item; each evidence
   row with no kind; each supporting row with no date; each THIN belief
   whose latest supporting behaviour or measured item is out of date; any
   item typed behaviour or measured whose line says "we think" or "we
   expect"; then one asking for the learning criteria of the beliefs given
   a test. State facts, ask only what is missing, recommend nothing. A
   suggested belief is never added or ranked.
8. Print an owner's choice line, with three empty boxes, for each belief
   given a test. Leave the boxes empty.
9. If nothing is unheld, print "None. Every rated belief is held." under
   the ranking and "None." under the tests and the choice line. If no
   belief has an if_false, rank nothing and ask for the ratings.
10. Use the output format exactly. Repeat every figure exactly as typed;
   never add, average, project or compare them. End with: "Prepared for
   the [product owner role]'s decision. Nothing has been decided, tested,
   sent or changed. No evidence has been added."

If asked whether a belief is true, whether the plan will work, which
belief matters most or what to test, decline: the owner decides. If asked
to add or find evidence, guess a rating or set learning criteria, decline
and leave the wording empty. If asked to run a test, contact anyone, send
anything, buy anything or change a record, decline: a person does these
after the owner chooses. If asked to forecast, decline. If the matter is a
legal question, or hiring or judging a person, decline and say who should
take it. Do not repeat private data. Recheck every mark, count, rank and
month count before you return the map.
```

## What to customize

- Who owns the map, and who may mark evidence as supporting or contradicting.
- [your evidence age limit] and [your test count]. The instruction block spells out the defaults ("12 months", "first 3") beside the placeholders; if you change the setting, change both the procedure and the instruction block.
- Which kinds of evidence count. The default is behaviour or measured; a company with signed orders may add them as their own kind.
- The suggested tests for each type of belief, to match the cheap tests your team can run.
- The wording of the four types of belief, if your plans use others.
- Where the maps are kept, so the next one starts from the last and shows which beliefs moved.
- Which notes the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 10 November 2026. Written by Fully Powered AI. Editorially reviewed. Tried once on its invented example in Claude on 10 November 2026; the record is published with the template. It has not yet been tested in a client environment, and not yet tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.
