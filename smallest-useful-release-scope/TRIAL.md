# Smallest useful release scope: a trial on its example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-10

The inputs were the invented Brindle Rota example (the brief and the sixteen-row feature list in `public/example.md`). No client data was used. The assistant was given the complete template and the example's inputs only; it had not seen the example's output when it produced its own. It followed the instruction block and the output format as written. This was one run, by a model that did not write the template.

## What came out

The page the run produced is given below in condensed form: the "Why in:", "Step:", "Why deferred:" and "Until then:" labels are dropped from the feature lines, and the decision and closing lines are summarised after it, not shown. The substance of each line is as the run gave it.

SMALLEST USEFUL RELEASE SCOPE: Brindle Rota

For: the founder. Prepared 10 November 2026 from 16 features and the owner's brief. Capacity: 40 person-days.

The outcome: A café manager can publish next week's rota to the team and see who has confirmed their shifts.
The measure: The share of published rotas that at least 80% of the staff on them confirm within 48 hours.
The path: 1. The manager signs in and opens the week. 2. The manager places staff in shifts. 3. The manager publishes the rota. 4. Staff see their shifts and confirm. 5. The manager sees who has confirmed.

In scope: 10 features, 42 person-days.
- F01 Manager email sign-in. Access, needed to reach step 1. Effort 3.
- F02 Weekly rota grid. On the path, steps 1 and 2. Effort 8.
- F03 Staff list. On the path, step 2. Effort 4.
- F05 Publish the rota and text every person on it. On the path, step 3. Effort 6.
- F06 Staff sign-in link. Access, needed to reach step 4. Effort 4.
- F07 Staff view of own shifts with a confirm button. On the path, step 4. Effort 5.
- F08 Manager panel showing who has confirmed. On the path, step 5. Effort 3.
- F09 Correct and republish a rota. Recovery for F05, which reaches people outside the team. Effort 3.
- F15 Record the time of each publish and each confirmation. Needed to count the measure. Effort 2.
- F16 Connect the text provider. Pulled in by F05. Effort 4.

Deferred: 6 features, 43 person-days.
- F04 Drag shifts between days (5): makes step 2 easier; workaround is picking the day from a menu.
- F10 Shift swap requests (9): serves no step; staff message the manager.
- F11 Payroll hours export (7): serves no step; manager copies hours into the payroll sheet.
- F12 Staff availability preferences (8): makes step 2 easier or richer; staff tell the manager in the group chat.
- F13 Several cafés under one account (12): serves no step; one account per café.
- F14 Dark mode (2): serves no step; none supplied.

Capacity check: 42 against 40: over by 2. Removable, serving no path step and not pulled in: F09 (3; the release loses the ability to correct and republish a rota) and F15 (2; the release loses the times the measure needs). Removing F15 alone closes the gap exactly; removing F09 alone closes it with 1 to spare. The owner may also narrow a path step.

Needs the owner: 1. F16 is in only because F05 depends on it; does the owner want to change F05 instead?

Engineering to confirm: the text provider's sender registration (about a week), touching F05 and F16. The effort figures were not checked.

Flags: F14 is deferred and has no workaround supplied.

Decision for the owner: left blank. The closing line was printed as specified.

## What was observed

- Every required part was produced and every one of the 16 features appears in In scope or Deferred, and F16 also appears under Needs the owner. No question needed to be asked and no stop condition was met. The totals (42 in, 43 deferred) and the over-by-2 result match a hand check.
- The result agrees with the published example on every placement, every total, the removable list, the owner question, the engineering item and the flag.
- Differences from the published example are in wording and layout only. The example writes the page as headed bullets with bold labels; the run followed the plain layout in the template's format block. As the example stood at the run, its For line read "the founder's brief" and its capacity paragraph "The founder may also narrow a path step", where the format prints "the owner's brief" and "The owner may also narrow a path step"; the run printed the format's wording. The example's measure line, as it stood at the run, was the brief's first sentence only, as the run's was. The example added "Removing both gives 37" and "F16 is pulled in by F05 and cannot be removed on its own", which the template does not ask for.
- Facts not in the inputs: the example says a published rota "cannot be corrected after staff have been texted" and the measure "cannot be counted from the product". Both are inferences from feature names, not from the list. The run kept to the feature names and the measure's wording. (The example has since been reworded; see the edits below.)

### Where the instructions were unclear

- **Recovery rule and "outward".** The rule says to look at the protected feature's outward value, but the column description says outward describes the row's own feature (F09's is blank). The run used the protected feature's value (F05, yes), as the rule says, but a reader could take the column the other way and get UNSURE.
- **Order of rule F and pull-in.** Rule F defers a feature "unless something IN depends on it", yet F16 was first placed by that rule and only moved in at the pull-in step. The run treated the pull-in as overriding. The two steps could be stated as one.
- **The numbering differs.** The long procedure has ten steps, with the rule C pass after step 4. The instruction block has nine, with rule C inside the placement step "left until step 3 is done". The run followed the instruction block.
- **"What the release loses", "taken from the list".** Nothing in the list states a loss, so the sentence has to be built from the feature name. That is where an assistant is most likely to add detail it does not have.
- **"At least"** is required when an effort is missing; no row in this example is missing one, so that path, and the stop conditions, were not exercised.
- **The date.** "Prepared [date]" has no stated source. The run used the brief's review date.

Nothing was sent, changed or scheduled. This run shows the template works on its own invented example. It does not show how it performs on a real company's list.

### Edits made after this run

These were made after the run above and have not been run again. The recorded output and observations above are unchanged except for corrections to what the observations said about the run: the "exactly once" count, the description of the founder wording, and, in a later pass, what the example's measure line and For line said at the time of the run, and the description of the page above as condensed.

- The `outward` column now says the recovery rule reads the protected feature's value, in the column description, the rule and the instruction block.
- Rule F now says to leave a feature that something IN depends on for the pull-in step.
- "What the release loses" is now built only from the feature's name and the brief.
- UNSURE features now have a line of their own in the output format, because they are in neither total; an "at least" total now has stated wording ("over by at least", "under by at most").
- "Prepared" is now stated to take the brief's review date.
- The reviewer checklist no longer says every feature appears exactly once.
- The published example's wording was brought into line with the rules (step 2 reason; the measure line now carries the brief's second sentence).
- In a later pass, after independent review: the example's For line now reads "the owner's brief" and its capacity paragraph "The owner may also narrow a path step", as the format prints them; its two "what is lost" sentences were reworded to rest only on the feature names and the brief; and "Removing both gives 37" and the F16 sentence were dropped, because the format does not ask for them.
- In the same pass, the procedure in the template was renumbered to nine steps to match the instruction block (the input check sits before step 1, and rule C waits until step 3 is done in both). Rule C now sends a recovery feature to UNSURE when its protected feature is UNSURE or when the row names no protected feature, and defers it only when the protected feature is deferred. The instruction block gained the line "Paste this block as custom instructions, followed by the output format above", a definition of the six kinds and of outward, and the reason wording for rules A, B, D and E. None of this has been run again.
