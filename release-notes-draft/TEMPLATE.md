# Release notes draft

Workflow template, version 0.1.0.

## Purpose

Prepare draft release notes for one shipped release, written for the people who use the product. From a short release brief, a sheet of release items, a sheet of known issues and a glossary of the team's internal names, the assistant produces one draft in a fixed order: what users must do, what is new, what has changed, what has been removed, what has been fixed, the known limitations and where to get help. It adds pages for the product owner alone: what was held out and why, checks on the inputs, numbered questions and approval lines. Every statement traces to a supplied sheet. The assistant prepares; it publishes nothing, sends nothing, changes no record, describes no work that was not supplied, and decides nothing the notes say. The product owner confirms accuracy and approves publication.

## When to use it and when not to

Use it when the scope of one release is confirmed and the notes for its users are due: a web or mobile product, a companion app, a firmware or software update for a device, or a change to an online store's tools that customers or the shop's own staff will meet.

Do not use it:

- to plan the launch itself, its dates, owners and announcements. That is the Launch checklist;
- to tell your own people about a change in how the company works. That is the Internal change announcement;
- to write a help article about one resolved problem for a customer. That is a different piece of work;
- to describe work that is planned, in testing or behind a switch. Notes cover what shipped;
- to judge whether the release is ready to ship, or to decide what the release should contain;
- to make promises about dates, fixes or future features.

## Roles

- **Starts it and prepares the inputs:** the product owner, or the person the product owner names.
- **Confirms accuracy, answers the questions, approves publication:** the product owner.
- **Confirms the steps users must take and the limitations:** an engineer who worked on the release.
- **Confirms support can answer questions on the notes:** the support lead.
- **Publishes the approved notes:** the person the product owner names. The assistant never does.

## Inputs

1. **The release brief,** typed or pasted. It must say: the product; the release name or number; the date it shipped; who reads the notes and what they do with the product; where the notes will be published; where users get help; the tone wanted if the company has one. Anything not said is "not supplied". If the product, the release or the ship date is missing, stop and ask.
2. **The release items sheet,** one row per item that was part of the release. Default column headers: `item_code, item, change_type, what_changed_for_users, who_is_affected, where_to_find_it, user_action_needed, user_action_steps, status, claim_evidence`. `change_type` is one of `new`, `changed`, `removed`, `fixed`, `performance`, `security`. `user_action_needed` is `yes` or `no`. `status` is one of `shipped`, `behind_flag`, `partial`, `planned`. `claim_evidence` holds the measurement, test result or statement that supports a claim about speed, security or reliability, and is blank otherwise. If there is no items sheet, stop and ask. If a header does not match, stop, show the expected and the found headers, and ask which column is which. If an `item_code` appears more than once, stop, show the code and the rows that share it, and ask. If a value in `change_type`, `user_action_needed` or `status` is not on its list, stop, show the value and its item code, and ask.
3. **The known issues sheet,** one row per issue. Default column headers: `issue_code, issue, who_is_affected, workaround, status, related_item`. `status` is `open` or `closed`. `related_item` is an item code from the items sheet, or blank. If the sheet is missing, write "known issues sheet not supplied" under Known limitations and in the checks; never write that there are none. If a header does not match, or an `issue_code` appears more than once, stop and ask.
4. **The glossary,** one row per internal name. Default column headers: `internal_term, user_term`. It maps the names the team uses in the sheets to the words users see. If it is missing, use each item's name as supplied and say in the checks that the glossary was not supplied.
5. **The date the draft is prepared.** If missing, ask.
6. **The company's settings,** all optional: the maximum number of items in one set of notes; the change types and statuses if different; words the company never uses in a promise; the order of the sections.

Do not ask for, and do not repeat, customers' personal details, passwords, login codes or access keys. If an input contains them, say so and ask the person to remove them.

## The procedure

1. **Check the inputs before anything else.** Each sheet's headers match; item codes are unique; issue codes are unique; every `related_item` is an item code on the items sheet; every value on a list is on its list; the ship date is a real date. Any failure listed in the Inputs section, and any item code or issue code that appears twice, stops the work: show what was found and ask. Anything else becomes a line under Checks on the inputs, and a question where a person has to answer. Default limit: thirty items. More than that, stop and ask whether to split the notes.
2. **Decide what is in the notes.** An item is in only if its status is `shipped`. Anything `behind_flag`, `partial` or `planned` is held out, with its status as the reason. A shipped item with no text in `what_changed_for_users` is held out: "no change for users was described". A `performance` or `security` item with a blank `claim_evidence` is held out: "a claim about speed with no evidence supplied" or "a claim about security with no evidence supplied", naming the one that applies. A shipped item whose `who_is_affected` is filled in and names none of the reader groups in the brief is held out: "not for these readers". The match is loose: ignore capitals and plurals, and count a group as a reader if the brief's wording includes it ("Managers" matches "shop and cafe managers"). If it is unclear whether a name is one of the reader groups, include the item and ask. A blank `who_is_affected` on an item that is otherwise included is written "not supplied" and raised as a question. When an item fails more than one test, give only the first reason in the order above: status, then no description, then no evidence, then not for these readers. A known issue is in only if its status is `open`; a `closed` issue is held out.
3. **Name each entry in the users' words.** The entry's heading is the item's `user_term` from the glossary. If the glossary has no row for the item, use the item as supplied and raise a question: what do users call this? Never invent a user-facing name.
4. **Write each entry from the sheet.** Say what changed for users using the words in `what_changed_for_users`, tidied for grammar only, with no fact added. Then say who is affected and where to find it, copied from the sheet with its capitals and punctuation as written ("Managers", "Rota page: Download menu"). A blank `where_to_find_it` is written "not supplied" and raised as a question. The sheet's wording wins over any tone in the brief: do not rewrite the entries to fit a tone such as "addressed to you", because that would change the words supplied. If the brief names a tone the entries do not follow, add a line in the checks saying so, and leave the wording to the product owner.
5. **Do not promise more than was supplied.** Words such as faster, better, improved, easier, simpler, safer, more secure, more reliable and seamless are used only where `claim_evidence` supports exactly that claim, and any figure is repeated exactly as supplied. Never explain why a change was made unless the sheet says. Never mention future work, a coming fix or a date that is not in the sheets. Never describe an internal change as a user benefit.
6. **Sort the entries.** Section 1, what you need to do: every included item with `user_action_needed` of `yes`. Its entry holds who, where and the steps, copied as supplied, numbered in the order given. Section 2: `new`. Section 3: `changed`, `performance` and `security`. Section 4: `removed`. Section 5: `fixed`. An item that needs action also appears in its type section, with the line "Action needed: see [heading] under What you need to do." and without repeating the steps. Items keep the order of the sheet inside each section.
7. **Steps are never guessed.** If an included item needs action and `user_action_steps` is blank, list it in section 1 with "Steps: not supplied", count it as a blocker, and raise a question for the engineer. Do not write steps from the description.
8. **Known limitations.** For each open known issue, the heading is the user term of its related item, or the issue code if it has none. Give the issue as supplied, who is affected, and the workaround as supplied, or "No workaround supplied". A limitation whose related item is held out is held out with it: "its feature is not in these notes". Do not say a fix is coming.
9. **Getting help.** The route from the brief, as written. If none, write "Not supplied" and raise a question.
10. **Held out.** One line for each item or issue left out: its code, its name as supplied, and the one reason from step 2, worded as given there and with nothing added. If none, write "none".
11. **Counts.** In the line "In this release", count the included items by type (performance and security items count as changed), how many of them need action, and the included known issues. Count them from the sections; do not estimate.
12. **Blockers.** A blocker is an included item that needs action and has no steps. (A value that cannot be read stops the work before a draft exists, so it is not counted here.) State the number in the heading block. With one or more, add "Not ready to publish" to the status.
13. **Questions,** numbered, in the order of the sections. Each states the facts, then asks. Recommend nothing unless the product owner asks, and do not suggest what the answer might be. Every flag in the checks has a question, except the line about the brief's tone, which leaves the wording to the product owner; so does every item held out for its status (asking whether the status has changed), for a missing description or for missing evidence. A closed issue, an item "not for these readers" and a limitation held out with its item need none.
14. **Approvals.** Close with approval lines for the product owner, an engineer and the support lead. Leave names and dates blank. Nothing is published until a person ticks the first.
15. Use the output format exactly. Write dates in words, such as 10 November 2026. Where a section has nothing in it, print its "none" line.

## Exceptions and stop conditions

- **A header does not match, a value is not on its list, an item code or issue code appears twice, or the items sheet, the release brief, the ship date or the preparation date is missing:** stop; show what was expected and what was found; ask.
- **More items than the limit:** stop and ask whether to split the notes.
- **An item needing user action has no steps:** include it, mark the steps "not supplied", count a blocker, and ask. Never write steps from the description.
- **A shipped item with no description for users, a speed or security claim with no evidence, a flagged, partial or planned item:** hold it out and say why. Never include it quietly or leave it out silently.
- **A person asks for a benefit, a reason, a date or a promised fix that is not in the sheets:** decline; ask for the source.
- **A person asks the assistant to publish, post, send or update the notes anywhere, or to change a record:** decline; a person does that after approval.
- **A person asks for a claim to be strengthened so the release sounds better:** decline.
- **An input holds customers' personal details, a password, a login code or an access key:** do not repeat it; ask the person to remove it.

## Output format

```
RELEASE NOTES DRAFT: [product] [release]

Prepared [date] for the [product owner role]. Readers: [readers]. Shipped [date]. Status: DRAFT, not approved. [Not ready to publish.] Blockers: [n, or none].
In this release: [n] new, [n] changed, [n] removed, [n] fixed; [n] of these need action from the user. Known limitations: [n].
Item codes in square brackets are for the checker. Delete them before [publishing]. Sections 1 to 7 are the notes; sections 8 to 11 are for the [product owner] only.

1. WHAT YOU NEED TO DO
[Heading] [item code]. Who: [who is affected]. Where: [where to find it]. Steps: [numbered steps as supplied, or "not supplied"].
(If none: "Nothing to do in this release.")

2. WHAT IS NEW
[Heading] [item code]. [What changed.] Who: [who]. Where: [where].
(If none: "Nothing new in this release.")

3. WHAT HAS CHANGED
[Heading] [item code]. [What changed.] Who: [who]. Where: [where]. [Action needed: see [heading] under What you need to do.]
(If none: "Nothing changed in this release.")

4. WHAT HAS BEEN REMOVED
[Heading] [item code]. [What changed.] Who: [who]. Where: [where]. [Action needed: see [heading] under What you need to do.]
(If none: "Nothing was removed in this release.")

5. WHAT HAS BEEN FIXED
[Heading] [item code]. [What changed.] Who: [who]. Where: [where].
(If none: "Nothing fixed in this release.")

6. KNOWN LIMITATIONS
[Heading] [issue code]. [The issue.] Affects: [who]. What to do: [workaround, or "No workaround supplied"].
(If none: "No known limitations were supplied.")

7. GETTING HELP
[The route from the brief, or "Not supplied; see question [n]".]

8. HELD OUT
[Code] [name as supplied]: [reason].
(If none: "none")

9. CHECKS ON THE INPUTS
- [Each check made, and each flag, one line each.]

10. QUESTIONS FOR THE PRODUCT OWNER
[n]. [Facts, then the question.]
(If none: "none")

11. APPROVALS
[ ] The [product owner] confirms that every entry in sections 1 to 6 matches what shipped, and approves publication. Name and date: ______
[ ] The [engineer] confirms the steps in section 1 and the limitations in section 6. Name and date: ______
[ ] The [support lead] confirms section 7 and that support can answer questions on sections 1 to 6. Name and date: ______
Nothing is published until a person ticks the first box.

This draft was prepared on [date] from the release brief, the release items, the known issues and the glossary supplied. It publishes nothing and changes no record.
```

## Reviewer checklist

1. Every entry in sections 1 to 6 traces to a row on a supplied sheet, and says nothing that row does not. (Product owner)
2. Every item with status other than `shipped` is held out, and none appears in the notes. (Product owner)
3. Every steps list is copied as supplied, in the order given, and every item needing action has one or is marked "not supplied". (Engineer)
4. No claim about speed, security or reliability appears without the evidence for it, and no figure differs from the sheet. (Engineer)
5. No entry promises a fix, a date or a future feature. (Product owner)
6. Every heading is the users' word from the glossary, or is raised as a question. (Support lead)
7. Every known limitation matches an open issue, with its workaround as supplied. (Support lead)
8. The counts in the heading block match the sections, and the held-out list matches the sheets. (Product owner)
9. Every flag in the checks has a numbered question, except the line about the brief's tone, as does every item held out for its status, a missing description or missing evidence, and every empty section prints its line. (Product owner)
10. Every held-out line gives one reason from the procedure, worded as given there, and adds nothing to it. (Product owner)

## Acceptance tests

Proposed tests. Only test 1 has been run, on the invented example; its record is published with the template.

1. **Normal release.** Eight items and three known issues. Expected: all eleven sections complete; unshipped and unexplained items held out; steps copied unchanged.
2. **Renamed header.** The items sheet has `description` in place of `what_changed_for_users`. Expected: stops, shows expected and found headers, asks.
3. **Value not on its list.** A `change_type` of `improved`. Expected: stops, shows the value and its item code, asks.
4. **Performance claim with no evidence.** Expected: held out with the reason; a question asks for the evidence.
5. **Item behind a flag.** Expected: held out as `behind_flag`; the notes do not mention it.
6. **Planned item.** Expected: held out; no future tense anywhere in the notes.
7. **Action needed, no steps.** Expected: listed in section 1 with "Steps: not supplied"; one blocker; "Not ready to publish"; a question for the engineer.
8. **Internal change.** A shipped item with no description for users. Expected: held out with that reason.
9. **No glossary row.** An included item whose name is not in the glossary. Expected: item name used as supplied; a question asks what users call it.
10. **Limitation on a held-out item.** An open issue whose related item is held out. Expected: held out with it.
11. **Asked to add a promise.** "Say the PDF cut-off is fixed next week." Expected: declined; asks for the source.
12. **Asked to publish.** Expected: declined; approval lines left blank.
13. **Nothing in a section.** No removed items. Expected: "Nothing was removed in this release."
14. **Repeated code.** Two items share the code R3. Expected: stops, shows the code and both rows, asks.
15. **Two reasons.** A shipped item with no description and no audience. Expected: held out once, with "no change for users was described" as the only reason; a question asks what changed.

## Instructions for the AI assistant

```
You prepare draft release notes for the product owner. You never
publish, post or send the notes, change any record, describe work that
was not supplied, or decide anything the notes say. The product owner
confirms accuracy and approves publication.

The user will supply: a release brief (product, release, ship date,
readers, where users get help, and a tone if the company has one); a
release items sheet; a known issues sheet; a glossary of internal names
and the words users see; the date the draft is prepared; and, if they
wish, settings (a maximum number of items, different change types or
statuses, words the company never uses in a promise, the order of the
sections). If the brief's product, release or ship date, the items
sheet or the preparation date is missing, stop and ask.
Expected headers, release items: item_code, item, change_type,
what_changed_for_users, who_is_affected, where_to_find_it,
user_action_needed, user_action_steps, status, claim_evidence. Known
issues: issue_code, issue, who_is_affected, workaround, status,
related_item. Glossary: internal_term, user_term. If a header does not
match, a value in change_type, user_action_needed or status is not on
its list, or an item code or issue code appears twice, stop, show what
was expected and what was found, and ask. Never guess which column was
meant.

1. Check the inputs: headers, unique item and issue codes, every
   related_item on the items sheet, real dates. More than thirty items
   (or the limit set): stop and ask.
2. Include an item only if its status is shipped. Hold out anything
   behind_flag, partial or planned, with its status as the reason; any
   shipped item with no what_changed_for_users ("no change for users
   was described"); any performance or security item with a blank
   claim_evidence ("a claim about speed with no evidence supplied" or
   "a claim about security with no evidence supplied", naming the one
   that applies); any item whose who_is_affected is filled in and names none
   of the reader groups in the brief ("not for these readers"; match
   loosely, ignoring capitals and plurals; if unsure, include and ask).
   If an item fails more than one test, give only the first reason in
   that order. Include a known issue only if open; hold out closed ones,
   and those whose related item is held out ("its feature is not in
   these notes").
3. Head each entry with the glossary's user_term. With no glossary row,
   use the item name as supplied and ask what users call it.
4. Write each entry from the sheet: what changed for users, in the
   sheet's words, tidied for grammar only; then who is affected and where
   to find it, copied with the sheet's capitals and punctuation. Add no
   fact. A blank who or where is "not supplied", with a question. The sheet's
   wording wins over the tone in the brief: do not rewrite entries to
   fit it. If the entries do not follow the tone the brief names, say so
   in the checks.
5. Use a word such as faster, better, safer or more reliable only where
   claim_evidence supports exactly that, and repeat figures exactly. Do
   not explain why a change was made unless the sheet says. Never
   mention future work, a coming fix or a date that is not supplied.
6. Sort: section 1 for every included item needing action, with steps
   copied as supplied and numbered; then new, changed (with performance
   and security), removed, fixed. Keep the sheet's order within each
   section. An item needing action also appears in its type section with
   a pointer to section 1, without the steps again. If the steps are
   blank, write "Steps: not supplied", count a blocker and ask the
   engineer. Never write steps from the description.
7. Known limitations: the heading is the user term of the related item,
   or the issue code if there is none; then the issue, who is affected
   and the workaround as supplied, or "No workaround supplied". Do not
   say a fix is coming.
8. Getting help: the route from the brief, or "Not supplied" with a
   question. If the known issues sheet is missing, write "known issues
   sheet not supplied" under Known limitations and in the checks, never
   "none". If the glossary is missing, use each item's name as supplied
   and say in the checks that the glossary was not supplied.
9. Held out: code, name as supplied and the one reason, worded as above
   and with nothing added, for everything left out. Count the sections
   for the "In this release" line; performance and security items count
   as changed.
10. Blockers are included items that need action and have no steps.
    State the number in the heading block; with one or more, add "Not ready to publish" to the status.
11. Number the questions in section order, each with its facts and then
    the question. Recommend nothing and suggest no answer unless asked.
    Every flag in the checks has a question, except the line about the
    brief's tone, and so does every item held
    out for its status, a missing description or missing evidence.
    End with the approval lines, names and dates blank.
12. Use the output format exactly. Write dates in words, such as
    10 November 2026. Print the "none" line for an empty section. End
    with: "This draft was prepared on [date] from the release brief, the
    release items, the known issues and the glossary supplied. It
    publishes nothing and changes no record."

If asked to publish, post or send the notes, to add a promise, a reason
or a date that is not supplied, or to strengthen a claim, decline. If an
input holds customers' personal details, a password, a login code or an
access key, do not repeat it; ask the person to remove it. Check every
statement against the inputs before you return the draft.
```

Paste this block as custom instructions, followed by the output format above.

## What to customize

- The glossary: your own internal names and the words your users see.
- The readers and the place the notes are published, which set the tone and length.
- Your change types and statuses, if yours differ, and the headers of your sheets.
- The maximum number of items in one set of notes.
- Words your company never uses in a promise.
- The order of the sections, and whether the owner-only pages are kept in the same file.
- Who counts as the engineer and the support lead, so each approval line has a name.
- Where approved notes are kept, and who publishes them.
- Which files the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 10 November 2026. Written by Fully Powered AI. Editorially reviewed. Tried once on its invented example in Claude on 10 November 2026; the record is published with the template. After that run, an independent review led to edits the same day (a rule for repeated codes, a loose match for readers, one reason for each held-out item, a question for every held-out status, the sheet's wording winning over the brief's tone, and a fuller instruction block), and the run was repeated on the revised text. Not yet tested in a client environment, and not yet tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.
