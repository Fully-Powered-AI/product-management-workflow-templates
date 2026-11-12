# Roadmap tradeoff review

Workflow template, version 0.1.0.

## Purpose

When a new priority would add work to a planning window that is already full, prepare the page the product owner needs before answering yes: the request's effort by team, each team's capacity position, how short the plan falls, a proposed set of planned items that could make room under written rules, and what moves with them (commitments, later items that depend on them, and dependencies of the request that nobody owns). Every figure is counted from the supplied exports. The assistant prepares; it never changes the tracker, gives any date to anyone, sends anything or decides. It assigns no new date to displaced work.

## When to use it and when not to

Use it when a request, a customer need or a new dependency arrives for a window that is already planned, and before anyone is told yes.

Do not use it for a milestone that has already slipped (use Schedule recovery options), to check whether team goals line up with company goals (use Goal alignment review), or to record the decision afterwards (use Decision log). Do not use it to score a new initiative against committed work and capacity by role and month for a portfolio owner (use Project intake and capacity review), or to price a change to the agreed scope of a running project (use Scope change impact review). This one works by team and window, ranks by goal, uses no scores, and covers commitments and dependencies. Do not use it when no team has estimated the request, when capacity is not known for a team the request needs, or to judge people or teams.

## Roles

- **Runs it:** the product owner.
- **Supplies estimates:** the lead of each team the request touches.
- **Owns the goals ranking:** the person named in the settings.
- **Owns each item and each commitment:** the role in the Owner and Committed To columns.
- **Decides:** the product owner.
- **Records the decision:** the product owner.

## Inputs

1. **The request:** name, who asked, the goal it serves, the date the asker stated (or "none"), and each team's effort estimate in person-weeks. If no estimate is supplied for a team, write "estimate not supplied" for that team and compute nothing for it. If the request is missing, stop.
2. **The roadmap export,** one row per item, with these default headers: `ID, Item, Team, Status, Window, Effort Remaining (pw), Depends On, Goal, Committed To, Owner`. Statuses are Idea, Planned, In progress, Done, Cancelled. Depends On holds IDs separated by semicolons. If a header does not match, stop and ask which supplied column to use. Do not guess.
3. **Capacity,** default headers: `Team, Window, Capacity (pw)`. A team with no row is stop-and-ask for that team.
4. **Goals,** default headers: `Goal, Rank, Statement`. Rank 1 is the highest. If missing, the assistant proposes no order; it lists the allowed candidates and the gap and the product owner chooses.
5. **The request's dependencies,** default headers: `Dependency, Owner, Effort (pw), Needed By Team`. Needed By Team is the team that needs the dependency done for the request to go ahead; it is a team name, not a date. If missing, say that its dependencies were not checked.
6. **Settings:** product owner, the person who owns the goals ranking, the window under review, the date of the run, the export date, whether committed items may be offered (default no), whether started items may be offered (default no), the margin each team keeps free in person-weeks (default 0).

## The procedure

1. **Check the inputs.** Match every header. Check that every ID named in Depends On exists. Check each estimate and each effort is a number or blank. If anything fails, stop and list what to fix.
2. **Count what is committed.** For each team the request touches, add the Effort Remaining of every item in the window under review whose Status is Planned or In progress. Items that are Idea, Done or Cancelled, and items in other windows, are not counted; list each of them for those teams under Not counted with its reason. An item with a blank effort is listed as "effort not supplied" and left out of the sum, and the page says so.
3. **Find the gap.** Free = capacity − committed. Gap = request estimate + margin − free, and 0 if that is negative. Report "no margin left" for a team whose gap is 0 and whose free equals the request estimate + margin exactly. If a margin is set and free is above the request estimate but below the request estimate + margin, the gap is above 0 and is shown as it is; "no margin left" is not printed for it.
4. **List who may be offered.** For a team with a gap, a candidate is an item of that team in the window with Status Planned, a blank Committed To, and an effort supplied. An item with a Committed To entry is offered only if the settings allow it; an In progress item only if the settings allow it. Every other item of that team in the window is listed under Not offered with its reason. A team with no gap has no candidates and nothing under Not offered.
5. **Order the candidates.** Highest Rank number first (the lowest priority goal). Items whose goal is blank or not in the goals list come last. Ties go to the larger effort. With no goals supplied, do not order; list the candidates.
6. **Propose the displacement.** Take candidates in order until their efforts together reach the gap. That set is the proposal; when it holds more than one item, print the displace line once per item and compute "covers the gap" and "frees" on their combined effort. Do not assign the displaced items a new window or date. If all candidates together do not reach the gap, say by how much the plan stays short and what would unlock more: a committed item the owner may offer, a smaller request, or more capacity. Do not invent any.
7. **Find alternatives.** List every other candidate that on its own covers the gap, with its goal, rank and the capacity it would leave free. Show at most three, smallest left-over first.
8. **Recompute the position.** For every team the request touches, including a team with no gap, and for the proposal and for each alternative: committed after = committed − displaced efforts + the request estimate; free after = capacity − committed after.
9. **Commitments touched.** For each displaced item with a Committed To entry, name the commitment and the Owner who would have to be asked. If none, write "None".
10. **Dependencies unresolved.**
    - Every item anywhere in the export whose Depends On names a displaced item: its ID, team, window and owner.
    - Each dependency of the request with no owner, no effort, or an owner with no capacity row.
    - A dependency's effort is never added to the figures and never assumed to be zero: each is listed, with what is missing, and the page says its effort is left out of the figures.
11. **Goal check.** State the request's goal and rank and the goal and rank of each displaced item. If the request serves a goal ranked below one it displaces, say so as a fact. Name any goal left with no item in the window after the move.
12. **Not known.** List every question that would change a figure or a choice, each with who can answer it. Take the answerer from a role in the inputs; if none, it is the product owner.
13. **Close.** Name the window and export date. Return the draft to the product owner only.

## Exceptions and stop conditions

- **A header does not match, or an ID in Depends On is missing:** stop; list the problem.
- **No capacity row for a team the request touches:** stop for that team; ask.
- **The request has no estimate for any team:** stop.
- **A displaced item's dependents sit in a team with no capacity row or window:** report them as unresolved; do not infer a date.
- **Asked to give or imply a date to the asker or a team, to rank the request above other work, to choose between the proposal and an alternative, or to write the message to the teams:** decline; the product owner decides and decides what is said.
- **Asked to adjust an estimate so the request fits:** decline.

## Output format

```
ROADMAP TRADEOFF REVIEW: [request name]

For: [product owner]. Window: [window]. Prepared [date of the run] from the roadmap export of [date].

The request: [name], asked by [role], serves [goal, rank, statement, or "none stated"]. Effort by team: [team n pw, ...]. Date the asker stated: [date or "none supplied"]. Left out of the figures: [items with no estimate or no capacity, or "None"].

Capacity by team (pw):
- [Team]: capacity [n], committed [n] ([IDs and efforts]), free [n], request [n], gap [n]. [No margin left, if so.]

Proposed revision:
- [Team]: displace [ID item] ([n] pw, goal [G], rank [n]) [and each further item in the same form]. [Covers the gap of n and frees n pw more.] No new date is assigned; it needs its own decision.
- [Team with no gap]: none needed.

Alternatives that also cover the gap: [Team: ID item (n pw, goal, rank), leaving n pw to spare; or "None"].

Not offered (teams with a gap only): [ID (reason)]. Not counted (Idea, Done, Cancelled or other window): [ID (reason)].

After the change (pw): [Team] committed [n] of [capacity], free [n]. With the alternative instead: [Team] committed [n] of [capacity], free [n].

Commitments touched: [displaced ID, commitment, who must be asked; or "None"].

Dependencies unresolved:
- [ID item (team, window, effort, owner) depends on a displaced item; or the request's dependency with what is missing; or "None"].

Goal check: [request goal and rank against each displaced item's goal and rank]. Goals left with no item in the window: [goals or "None"].

Not known:
1. [Question. Who can answer: role.] (or "None")

Decision for [product owner]: choose the proposal, an alternative, neither, or a smaller request, and set any new date for displaced work. Teams confirm their own estimates. Nothing is changed in the tracker, promised to anyone or sent.
```

## Reviewer checklist

1. Each team's committed figure matches the roadmap export for the window, and no Idea, Done, Cancelled or other-window item is counted. (Product owner)
2. Free, gap and after-the-change figures are arithmetically correct. (Product owner)
3. No committed or started item is proposed unless the settings allow it. (Product owner)
4. The displaced set follows the stated order and stops when the gap is covered. (Product owner)
5. Every item that depends on a displaced item is listed. (Team lead who owns it)
6. Every dependency of the request is owned and estimated, or listed as open. (Product owner)
7. No date is given or implied, and displaced work has none. (Product owner)
8. Every empty section says "None". (Product owner)
9. The Goal check states the request's goal and rank against each displaced item's, and the Not known list names who can answer each question. (Product owner)

## Acceptance tests

Proposed tests. The trial run exercised tests 1 to 6 in effect; tests 7 to 10 have not been run. They use the worked example's inputs.

1. **Normal request.** Platform capacity 45, committed 43, request 6. Expected: free 2, gap 4; R3 proposed; R9 listed as an alternative; Platform after 40 of 45.
2. **Counting rule.** R11 has status Idea and R5 sits in Q2. Expected: neither is counted; Platform committed is 43 and Web committed is 19.
3. **Zero margin.** Web free 3, request 3. Expected: gap 0, "No margin left", no displacement for Web.
4. **Offered only where allowed.** R1 and R8 carry commitments; R2 is in progress. Expected: all three under Not offered with their reasons.
5. **Dependent item.** R5 depends on R3. Expected: listed under unresolved dependencies when R3 is proposed, and absent from the alternative.
6. **Unowned dependency.** The security review has no owner or effort. Expected: listed as open and left out of the figures, which the page states.
7. **Header mismatch.** The roadmap's "Effort Remaining (pw)" column is called "Estimate". Expected: stops and asks.
8. **Shortfall.** Remove R3 and R9 from the candidates. Expected: says the plan stays short by 4 pw and names what would unlock more.
9. **Asked for a date.** The product owner asks what date R3 will now ship. Expected: declines; displaced work has no date.
10. **No goals supplied.** Expected: candidates listed with no order; the product owner chooses.

## Instructions for the AI assistant

```
You prepare a "Roadmap tradeoff review" for a product owner when a new
priority would add work to a planning window that is already full. You
never change the tracker, give or imply a date to anyone, send anything
or decide. The product owner decides. You assign no new date to
displaced work.

The user supplies: the request (name, who asked, the goal it serves, the
date the asker stated, each team's estimate in person-weeks); the
roadmap export with headers ID, Item, Team, Status, Window, Effort
Remaining (pw), Depends On, Goal, Committed To, Owner; capacity (Team,
Window, Capacity (pw)); goals (Goal, Rank, Statement), rank 1 highest;
the request's dependencies (Dependency, Owner, Effort (pw), Needed By
Team, a team name, not a date); and settings (product owner, who owns
the goals ranking, window, date of the run, export date, whether
committed items and started items may be offered, default no, and the
margin to keep free, default 0). If the request is missing, it has no
estimate for any team, a header does not match, an ID in Depends On is
missing, an estimate or an effort is neither a number nor blank, or
there is no capacity row for a team the request touches, stop and say
what to fix. Never guess a column. Blank is unknown, never zero.

1. Committed per team: add Effort Remaining for items in the window with
   status Planned or In progress. Leave out Idea, Done, Cancelled and
   other windows; list those items under Not counted with the reason.
   List any item with no effort as "effort not supplied".
2. Free = capacity - committed. Gap = request + margin - free, never
   below 0. Say "no margin left" for a team whose gap is 0 and whose
   free equals request + margin exactly. If free is above the request
   but below request + margin, the gap is above 0: show it, and do not
   say "no margin left".
3. Candidates for a team with a gap: Planned items of that team in the
   window with no Committed To and an effort. Offer committed or In
   progress items only if the settings allow. List every other item of
   a team with a gap, in the window, under Not offered with its reason.
   A team with no gap has no candidates and nothing under Not offered.
4. Order candidates by highest Rank number first; items whose goal is
   blank or not in the goals list last; ties to the larger effort. With
   no goals, do not order.
5. Propose candidates in order until they reach the gap. With more than
   one item, print the displace line once per item and compute the
   cover and the freed figures on their combined effort. Give displaced
   items no date. If they cannot reach the gap, state the shortfall and
   what would unlock more. List up to three single candidates that also
   cover the gap alone, smallest left-over first.
6. For the proposal and each alternative, for every team the request
   touches, including a team with no gap: committed after = committed -
   displaced + request; free after = capacity - committed after.
7. List commitments on displaced items and who must be asked. List
   every item whose Depends On names a displaced item, and every
   dependency of the request with no owner, no effort or an owner with
   no capacity row. Never add a dependency's effort to the figures and
   never treat it as zero: list it and say it is left out. State the goal
   and rank of the request and of each displaced item; flag as a fact if
   the request ranks below one it displaces; name any goal left with no
   item in the window.
8. List what is not known, each with who can answer.
9. Use the output format that follows this block exactly, word for
   word, and print "None" for an empty section.

Decline requests for a date, to choose among options, to adjust an
estimate so the request fits, or to write the message to the teams.
```

Paste this block as custom instructions, followed by the output format above.

## What to customize

- Your window and your unit of effort.
- Who may see the page before the product owner has decided.
- Whether committed items and started items may ever be offered, and who approves it.
- The margin each team keeps free.
- Who owns the goals ranking, and how often it is updated.
- Your tracker's column names against the defaults here.
- How many alternatives to show.
- Which exports the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 10 November 2026. Written by Fully Powered AI. Tried once on its invented example in Claude on 10 November 2026; the record is published with it. Not yet tested in a client environment.
