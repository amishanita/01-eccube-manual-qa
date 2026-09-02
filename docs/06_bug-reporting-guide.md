# 06. Bug Reporting Guide (不具合報告ガイド)

---

## What Qualifies as a Defect

A defect is behaviour that differs from a justified expectation, that you have
**reproduced at least twice**, and that is not explained by a documented
environment restriction.

Everything else is an observation, not a defect.

---

## What Is Not a Defect

| Observation | Why not |
|---|---|
| Demo data disappeared | Documented hourly reset |
| Registration cannot be completed | Email delivery disabled by the operator |
| Login fails | No member account can exist in this environment |
| The admin screen is inaccessible | Blocked by the operator |
| Cart contents changed unexpectedly | The environment is shared with other users |
| A rendering problem inside an app's built-in browser | Confirmed as a tooling artefact. See NDF-001 |

Reporting any of these as a defect signals that the reporter did not investigate.

---

## Before You Write a Report

1. Reproduce it. Then reproduce it again
2. Check the known limitations list
3. Try it in a clean session, for example an incognito window
4. Confirm the expected result is justified, not assumed
5. Capture evidence showing the failure

If you cannot reproduce it, that is still a valid record:
Status **Unable to Reproduce**, Reproducibility **Unable to Reproduce**.

---

## Required Fields

Bug ID, Title, Module, Environment, Preconditions, Steps to Reproduce, Test Data,
Expected Result, Actual Result, Reproducibility, Severity, Priority, Status,
Evidence, Related Test Case, Reported Date, Retest Result, Notes.

A report missing steps to reproduce or evidence is not submittable.

---

## Writing the Title

A good title states what fails, where, and under what condition.

Weak: `Cart bug`
Weak: `Search not working`
Better: `Cart total does not update after decreasing quantity to 1 on the cart page`
Better: `Katakana name field accepts romaji input on the registration form`

---

## Writing Steps to Reproduce

Numbered. Specific. Startable by someone who has never seen the application.
Include the exact data used and the exact URL.

Bad:
```
1. Go to cart
2. Change quantity
3. Total is wrong
```

Good:
```
1. Open https://ec-cube.sakura.ne.jp/4-2-demo/
2. Open the product ブーケクリアポーチ (¥1,100)
3. Click カートに入れる
4. Click カートへ進む
5. Click the plus control to set quantity to 2
6. Read the 小計 value on that row
```

---

## Severity and Priority

**Severity** is technical impact. **Priority** is fix urgency. They are not the same.

| Severity | Meaning |
|---|---|
| Critical | Purchase path blocked, or data lost or wrong |
| High | Major function broken with no workaround |
| Medium | Works incorrectly but a workaround exists |
| Low | Cosmetic, no functional impact |

| Priority | Meaning |
|---|---|
| High | Fix before release |
| Medium | Fix in a normal cycle |
| Low | Fix when convenient |

---

## Reproducibility

| Value | Meaning |
|---|---|
| Always | Failed on every attempt |
| Intermittent | Failed on some attempts |
| Once | Seen once, could not repeat |
| Unable to Reproduce | Could not repeat at all |

---

## Workflow

```
Backlog → To Do → In Progress → Ready for Test → Testing → Done
```

Plus terminal state **Unable to Reproduce**.

---

## Current Status

**No defect reports exist.** No issue has been reproduced in this environment.
One suspected issue (NDF-001) was investigated and correctly ruled out.
