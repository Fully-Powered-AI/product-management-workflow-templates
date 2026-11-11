# Smallest useful release scope

Capability template, version 0.1.0.

## Purpose

Help a product owner or founder cut a long feature list down to the first release that lets one kind of user reach one stated outcome. The assistant writes the path the user takes, places every feature against that path by fixed, ordered rules, gives a reason for each feature kept and each deferred, pulls in anything an in-scope feature depends on, and compares the total of the supplied effort figures with the supplied capacity. It estimates no effort, recommends no cut and makes no decision: the owner approves the scope after engineering confirms what can be built.

## When to use it and when not to

Use it when the features wanted exceed the capacity available and a first release, or the next release, has to be agreed around one outcome. Run it again when the list, the capacity or an engineering limit changes.

Do not use it:

- to record an agreed scope for a project with deliverables and acceptance criteria; use Project scope baseline;
- to judge new work arriving after scope is agreed; use Scope change impact review;
- to test whether the product idea itself is sound; use Business model assumptions review;
- to estimate effort, set dates or promise delivery; those figures come from engineering;
- when the brief states more than one outcome; the owner picks one first.

## Roles

- **Owner:** the product owner or founder. Writes the brief, states the outcome and the capacity, supplies the list, answers the questions and approves the scope.
- **Preparer:** whoever types the brief and the list and runs the assistant. Often the owner.
- **Engineering lead:** supplies the effort figures and the dependencies, states limits, and confirms what is feasible before the owner approves.

## Inputs

1. **The brief,** from the owner:
   - the product and the owner's name;
   - **the outcome,** one sentence of the form "a [kind of user] can [do one thing]". If there is more than one outcome, stop and ask which one this release serves;
   - **the measure:** how the owner will know the outcome happened. If not stated, print "not stated" and mark every learning feature "unsure";
   - **the path:** the numbered steps the user takes from the start to the outcome. If not supplied, stop and ask; the assistant does not invent steps;
   - **the capacity,** one amount in one unit, such as person-days;
   - **limits** engineering has stated, in the owner's words (optional);
   - the review date, which is the date printed after "Prepared".
2. **The feature list,** one row per feature. Default columns: `id,feature,step,kind,effort,depends_on,outward,workaround`. If the headers do not match, stop and ask which column is which; do not guess.
   - `id` is unique. `feature` is a short name.
   - `step` is the path step or steps the feature serves, separated by semicolons. Blank means it serves none.
   - `kind` is one of: **core** (the user does the step with it), **access** (letting the right person in), **recovery** (undoing or correcting), **usability** (making a step easier or clearer), **learning** (recording what is needed to count the measure), **other**. Blank counts as other.
   - `effort` is one number in the brief's unit, as supplied by engineering. Blank means not supplied.
   - `depends_on` lists ids, separated by semicolons, that must exist for this feature to work. For a recovery feature, it names the feature it protects.
   - `outward` is "yes" when the feature sends, publishes or charges something that people outside the product team receive; otherwise blank. It describes the row's own feature. Rule C reads the protected feature's `outward`, never the recovery row's.
   - `workaround` is what the user or team would do without the feature for now. Blank means none supplied.

The assistant works only from what is typed or pasted. It needs no connection to any system, and it never asks for a password or a login code.

## The procedure

**Before step 1: check the inputs.** Confirm one outcome, a path, a capacity, unique ids, and that every id named in `depends_on` exists. Stop and ask on any failure. A dependency that loops back on itself is a stop: name the ids.

1. **Write the page's head.** The outcome, the measure and the path, copied from the brief.
2. **Place each feature, by kind.** Take each feature once and apply the first rule that fits. Rule C waits: apply it only after step 3 is done, because it depends on what is IN by then. Rules A, B, D, E and F come first.
   - **Rule A, core.** Kind core with a step: IN, "on the path, step N".
   - **Rule B, access.** Kind access with a step: IN, "access: needed to reach step N". Kind access with no step: UNSURE.
   - **Rule C, recovery (applied after step 3).** If the feature it protects is IN and the protected feature's outward is yes: IN, "recovery for [id], which reaches people outside the team". If the protected feature is IN and the protected feature's outward is blank, or the protected feature is UNSURE, or the row names no feature in `depends_on`: UNSURE. If the protected feature is DEFERRED: DEFERRED, "protects a feature that is not in this release".
   - **Rule D, learning.** If the feature records what the measure needs: IN, "needed to count the measure". If the measure is not stated or the feature's link to it is unclear: UNSURE.
   - **Rule E, usability or other, with a step.** With a workaround supplied: DEFERRED, "makes step N easier or richer; the workaround is supplied". With no workaround supplied: UNSURE.
   - **Rule F, usability or other with no step.** Not depended on by anything IN: DEFERRED, "serves no step on the path". If a workaround is supplied, print it under "Until then". If something IN depends on it, leave it for step 3.
3. **Pull in dependencies.** For every IN feature, any feature in its `depends_on` that is not IN becomes IN, "pulled in by [id]", and the check repeats until nothing changes. A pulled-in feature of kind usability or other goes on the owner's list of questions, because the owner may prefer to change the feature that needed it.
4. **Add up.** Add the supplied efforts of the IN features and of the DEFERRED features. A feature with no effort supplied counts as "not supplied" and adds nothing; say "at least" before any total with such a feature in it and list them. Never put in a figure. UNSURE features are in neither total: list their supplied efforts and their sum on their own line, so the page shows how far the in-scope total could rise.
5. **Capacity check.** Compare the IN total with the capacity.
   - At or under: say by how much.
   - If the IN total is an "at least" total: say "over by at least" when it already exceeds the capacity, and "under by at most" when it does not, and add that the missing figures may change this. Never say "under by" without "at most".
   - Over: say by how much. List every IN feature that serves no path step and was not pulled in, with its effort and, in one sentence built only from the feature's name and the brief, what the release loses without it. Say which single removals close the gap and which do not. Add that narrowing a path step is also open to the owner. Recommend nothing.
6. **Needs the owner.** Every UNSURE feature as a question, and every pulled-in feature of kind usability or other. Also any core feature with a workaround supplied: ask whether the owner would do that step by hand in this release.
7. **Engineering to confirm.** List each stated limit with the features it touches. Say that the effort figures are the ones supplied and were not checked.
8. **Flags.** Deferred features with no workaround supplied; IN features with no effort; anything UNSURE left open. If none, print "None."
9. **Decision line.** Leave the owner's choice blank. Return the page to the preparer only.

## Exceptions and stop conditions

- **Headers do not match, a duplicate id, a missing id in `depends_on`, a loop in dependencies, no path, no capacity, no outcome or more than one:** stop and ask.
- **Mixed units in the effort column:** stop and ask which unit is meant.
- **Asked to estimate a missing effort, to recommend what to cut, to change a placement so the total fits, or to shrink the outcome:** decline; the owner decides.
- **A feature that cannot be placed by a rule:** UNSURE, never a guess.
- **Asked to schedule, assign, send the page, change a tracker or record the scope as agreed:** decline; a person does that after approving.

## Output format

```
SMALLEST USEFUL RELEASE SCOPE: [product]

For: [owner]. Prepared [review date] from [n] features and the owner's brief. Capacity: [amount] [unit].

The outcome: [sentence].
The measure: [sentence, or "not stated"].
The path: 1. [step]. 2. [step]. [and so on]

In scope: [n] features, [total] [unit].
- [id] [feature]. Why in: [rule reason]. Step: [n, or "none"]. Effort: [amount, or "not supplied"].

Deferred: [n] features, [total] [unit].
- [id] [feature]. Why deferred: [reason]. Until then: [workaround, or "none supplied"]. Effort: [amount, or "not supplied"].

Capacity check: [in-scope total] against [capacity]: [under by / over by / exactly at capacity].
[If any feature is UNSURE: Not counted, placement open: [id, effort]. The in-scope total could rise by up to [sum] if the owner puts them in.]
[If over: Removable, serving no path step: [id, effort, what is lost]. [Which single removals close the gap]. The owner may also narrow a path step.]

Needs the owner: [n].
- [id]: [question].

Engineering to confirm: [limit, with the ids it touches]. The effort figures are the ones supplied and were not checked here.

Flags: [flag, or "None."]

Decision for the owner: Scope approved / changed / declined: ______  Any removal chosen: ______

Draft for [owner]'s decision. Effort figures are the ones supplied; none was estimated. Nothing has been changed, sent, scheduled or assigned.
```

For an empty section, print the heading and "None." The In scope and Deferred lines print their features in id order.

## Reviewer checklist

1. The outcome is one sentence and matches the brief. (Owner)
2. Every feature on the list appears in scope or deferred, and every UNSURE feature appears under Needs the owner. A pulled-in usability or other feature, and a core feature with a workaround, appears in scope and under Needs the owner. (Preparer)
3. Each reason matches the rule that was applied. (Owner)
4. The totals add up from the supplied figures only, with "at least" where one is missing. (Engineering lead)
5. Anything an in-scope feature depends on is in scope. (Engineering lead)
6. No recommendation, estimate or schedule appears. (Owner)
7. Every deferred feature says what happens meanwhile, or says none was supplied. (Owner)

## Acceptance tests

Proposed tests. None has been run.

1. **Fits.** Ten features, in-scope total 30, capacity 40. Expected: "under by 10", no removable list.
2. **Over capacity.** In-scope total 42, capacity 40, with one learning feature of 2 and a recovery feature of 3. Expected: "over by 2"; the 2 closes the gap exactly; the 3 closes it with 1 to spare; nothing recommended.
3. **Dependency.** An in-scope feature depends on a deferred one. Expected: the deferred one moves in as "pulled in by" and its effort joins the total.
4. **No effort.** One in-scope feature has blank effort. Expected: "not supplied", "at least" on the total, and a flag.
5. **Two outcomes.** The brief names two. Expected: stops and asks which.
6. **Header mismatch.** The column named `size` appears in place of `effort`. Expected: stops and asks.
7. **Recovery, outward blank.** A recovery feature protects an in-scope feature whose outward is blank. Expected: UNSURE, with a question.
8. **Asked to estimate.** The user asks for the effort of a feature with none. Expected: declines, leaves it "not supplied".

## Instructions for the AI assistant

Paste this block as custom instructions, followed by the output format above.

```
You prepare a smallest-useful-release scope page for a product owner. You
never estimate effort, recommend what to cut, change a record, send the
page or decide anything on it. The owner approves the scope after
engineering confirms what can be built.

The user will supply a brief (product, owner, one outcome, the measure, the
numbered path, one capacity amount in one unit, any engineering limits, the
date) and a feature list with columns id,feature,step,kind,effort,
depends_on,outward,workaround. If the headers do not match, stop and ask.
Kinds: core (the user does the step with it), access (letting the right
person in), recovery (undoing or correcting), usability (making a step
easier or clearer), learning (recording what is needed to count the
measure), other; blank counts as other. Outward is "yes" when people
outside the product team receive what the feature sends, publishes or
charges. Depends_on names ids; for a recovery row it names the feature
it protects.
Stop and ask if there is more than one outcome, no path, no capacity, a
duplicate id, a depends_on id that does not exist, a dependency loop, or
mixed units. Never ask for a password or a login code.

1. Write the outcome, the measure and the path from the brief.
2. Place each feature by the first rule that fits, leaving rule C until
   step 3 is done.
   A. kind core with a step: IN, "on the path, step N".
   B. kind access with a step: IN, "access: needed to reach step N";
      with no step: UNSURE.
   C. kind recovery: IN if the feature it protects is IN and the protected
      feature's outward is yes; UNSURE if the protected feature is IN and
      its outward is blank, or is UNSURE, or the row names no feature in
      depends_on; DEFERRED if the protected feature is DEFERRED. Never read
      the recovery row's own outward.
   D. kind learning: IN if it records what the measure needs, "needed to
      count the measure"; UNSURE if the measure is not stated or the link
      is unclear.
   E. kind usability or other, with a step: DEFERRED, "makes step N easier
      or richer; the workaround is supplied", if a workaround is supplied;
      UNSURE if not.
   F. kind usability or other, with no step: DEFERRED, "serves no step on
      the path"; if something IN depends on it, leave it for step 3.
3. Pull in dependencies: anything an IN feature depends on becomes IN,
   "pulled in by [id]". Repeat until nothing changes.
4. Add the supplied efforts for IN and for DEFERRED. A blank effort is
   "not supplied" and adds nothing; say "at least" on such totals. Never
   supply a figure. List UNSURE features and their efforts on their own
   line; they are in neither total. If the IN total is "at least", say
   "over by at least" or "under by at most", never a bare "under by".
5. Compare the IN total with the capacity. If over, say by how much, list
   each IN feature that serves no path step and was not pulled in with its
   effort and what the release loses without it (built only from the
   feature's name and the brief), say which single removals
   close the gap, and say the owner may also narrow a path step. Recommend
   nothing.
6. List every UNSURE feature, every pulled-in usability or other feature,
   and every core feature with a workaround as a question for the owner.
7. List engineering's stated limits with the ids they touch, and say the
   effort figures were not checked.
8. Flag deferred features with no workaround, IN features with no effort,
   and open UNSURE items. If none, print "None."
9. Use the output format exactly. "Prepared" takes the brief's review date. Leave the decision line blank. End with:
   "Draft for [owner]'s decision. Effort figures are the ones supplied;
   none was estimated. Nothing has been changed, sent, scheduled or
   assigned."

Never move a feature to make the total fit. If asked to, decline.
```

## What to customize

- Your unit of effort, and who supplies it.
- Your six kinds of feature, and any that are always in or never in for your product.
- How the measure is stated.
- The limits your team always carries into a release.
- Who is the owner and who in engineering confirms.
- Which exports the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 10 November 2026. Written by Fully Powered AI. Tried once on its invented example on 10 November 2026 in Claude; the record is published with it. Edits made to the pasted instructions, the output format and the reviewer checklist after that run have not been run again; the trial record lists them. Not yet tested in a client environment, and not yet tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.
