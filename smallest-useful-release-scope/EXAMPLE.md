# Smallest useful release scope: an invented example

*Illustrative example with invented data.* The product, the founder, the features, the efforts and the limit below are all invented. Brindle Rota is an invented rota app for small cafés. First come the inputs the founder supplied, in full, then the page the workflow template returned.

## The inputs

### 1. The brief

```
Product: Brindle Rota
Owner: the founder
Outcome: A café manager can publish next week's rota to the team and see
  who has confirmed their shifts.
Measure: The share of published rotas that at least 80% of the staff on
  them confirm within 48 hours. Counting it needs the time of each publish
  and of each confirmation.
Path:
  1. The manager signs in and opens the week.
  2. The manager places staff in shifts.
  3. The manager publishes the rota.
  4. Staff see their shifts and confirm.
  5. The manager sees who has confirmed.
Capacity: 40 person-days
Limits: Engineering says texting staff needs the text provider's sender
  registration, which takes about a week to be approved.
Review date: 10 November 2026
```

### 2. The feature list (exported from the founder's planning sheet)

```
id,feature,step,kind,effort,depends_on,outward,workaround
F01,Manager email sign-in,1,access,3,,,
F02,Weekly rota grid,1;2,core,8,,,
F03,Staff list: add and edit people,2,core,4,,,
F04,Drag shifts between days,2,usability,5,F02,,Pick the day from a menu
F05,Publish the rota and text every person on it,3,core,6,F02;F03;F16,yes,
F06,Staff sign-in link: one per person,4,access,4,F03,,
F07,Staff view of own shifts with a confirm button,4,core,5,F05;F06,,
F08,Manager panel showing who has confirmed,5,core,3,F07,,
F09,Correct and republish a rota after it is published,,recovery,3,F05,,
F10,Shift swap requests between staff,,other,9,F07,,Staff message the manager who edits the rota
F11,Payroll hours export,,other,7,F05,,Manager copies hours into the payroll sheet
F12,Staff availability preferences,2,other,8,F03,,Staff tell the manager in the group chat
F13,Several cafés under one account,,other,12,F01;F03,,One account per café
F14,Dark mode,,usability,2,,,
F15,Record the time of each publish and each confirmation,,learning,2,F07,,
F16,Connect the text provider,,other,4,,,
```

## The output

**SMALLEST USEFUL RELEASE SCOPE: Brindle Rota**

- **For:** The founder. Prepared 10 November 2026 from 16 features and the owner's brief. Capacity: 40 person-days.
- **The outcome:** A café manager can publish next week's rota to the team and see who has confirmed their shifts.
- **The measure:** The share of published rotas that at least 80% of the staff on them confirm within 48 hours. Counting it needs the time of each publish and of each confirmation.
- **The path:** 1. The manager signs in and opens the week. 2. The manager places staff in shifts. 3. The manager publishes the rota. 4. Staff see their shifts and confirm. 5. The manager sees who has confirmed.

**In scope: 10 features, 42 person-days.**

- F01 Manager email sign-in. Why in: access, needed to reach step 1. Step: 1. Effort: 3.
- F02 Weekly rota grid. Why in: on the path, steps 1 and 2. Step: 1; 2. Effort: 8.
- F03 Staff list: add and edit people. Why in: on the path, step 2. Step: 2. Effort: 4.
- F05 Publish the rota and text every person on it. Why in: on the path, step 3. Step: 3. Effort: 6.
- F06 Staff sign-in link: one per person. Why in: access, needed to reach step 4. Step: 4. Effort: 4.
- F07 Staff view of own shifts with a confirm button. Why in: on the path, step 4. Step: 4. Effort: 5.
- F08 Manager panel showing who has confirmed. Why in: on the path, step 5. Step: 5. Effort: 3.
- F09 Correct and republish a rota after it is published. Why in: recovery for F05, which reaches people outside the team. Step: none. Effort: 3.
- F15 Record the time of each publish and each confirmation. Why in: needed to count the measure. Step: none. Effort: 2.
- F16 Connect the text provider. Why in: pulled in by F05. Step: none. Effort: 4.

**Deferred: 6 features, 43 person-days.**

- F04 Drag shifts between days. Why deferred: makes step 2 easier or richer; the workaround is supplied. Until then: pick the day from a menu. Effort: 5.
- F10 Shift swap requests between staff. Why deferred: serves no step on the path. Until then: staff message the manager, who edits the rota. Effort: 9.
- F11 Payroll hours export. Why deferred: serves no step on the path. Until then: the manager copies hours into the payroll sheet. Effort: 7.
- F12 Staff availability preferences. Why deferred: makes step 2 easier or richer; the workaround is supplied. Until then: staff tell the manager in the group chat. Effort: 8.
- F13 Several cafés under one account. Why deferred: serves no step on the path. Until then: one account per café. Effort: 12.
- F14 Dark mode. Why deferred: serves no step on the path. Until then: none supplied. Effort: 2.

**Capacity check:** 42 person-days in scope against 40: over by 2.

Removable, serving no path step and not pulled in: F09 (3 person-days; without it the release has no way to correct and republish a rota after it is published) and F15 (2 person-days; without it the release has no record of publish and confirmation times for the measure). Removing F15 alone closes the gap exactly (42 − 2 = 40). Removing F09 alone closes it with 1 person-day to spare (42 − 3 = 39). The owner may also narrow a path step.

**Needs the owner: 1.**

- F16: it serves no step on the path and is in only because F05 depends on it. If the founder would rather deliver the rota another way, F05 changes; say which.

**Engineering to confirm:** the text provider's sender registration, about a week to be approved as the founder typed it, touches F05 and F16. The effort figures are the ones supplied and were not checked here.

**Flags:** F14 is deferred and no workaround was supplied.

**Decision for the owner:** Scope approved / changed / declined: ______  Any removal chosen: ______

Draft for the founder's decision. Effort figures are the ones supplied; none was estimated. Nothing has been changed, sent, scheduled or assigned.
