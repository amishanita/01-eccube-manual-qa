# 05. Test Execution Guide (テスト実施ガイド)

How to execute the 40 designed test cases and record results honestly.

---

## Before Each Session

1. Note the start time in JST
2. Confirm your Chrome version at `chrome://version` and record it
3. Load the home page and confirm products exist
4. Run the smoke set: TC-001, TC-018, TC-022
5. If any smoke case fails, stop and investigate the environment first

---

## Executing a Case

1. Read the preconditions. Set them up before starting
2. Follow the steps exactly as written. Do not improvise
3. Observe the result before deciding what it means
4. Write the actual result in your own words, describing what you saw, not whether it passed
5. Capture a screenshot at the moment of observation
6. Only then assign a status

Writing "as expected" in the actual result column is not acceptable. Describe the
observation.

---

## Status Rules

| Status | When to use |
|---|---|
| Passed | The actual result matches the expected result |
| Failed | The actual result does not match the expected result, confirmed by repeating twice |
| Blocked | Execution could not continue because of a data reset, missing product, or restriction |
| Not Applicable | The feature does not apply in this environment |
| Not Executed | The case has not been run |

**Never mark Failed on a single observation.** Repeat it twice first.

---

## Before Recording a Failure

Work through this list:

1. Did you repeat the steps at least twice with the same outcome?
2. Is the behaviour on the known limitations list? If yes, it is not a defect
3. Could a data reset or another user explain it?
4. Is the expected result actually justified, or was it an assumption?
5. Do you have a screenshot showing the failure?

If any answer is no, the status is not Failed yet.

---

## Managing the Hourly Reset

Demo data resets roughly hourly. Plan around it:

- Work in blocks shorter than one hour
- Record the product name and price used in every case
- If a product disappears mid-case, mark it Blocked and restart from step 1
- Never continue a case from the middle after a reset

---

## Evidence

| Rule | Detail |
|---|---|
| Naming | `TC-0XX-short-description.png` |
| Timing | Capture at the moment of observation |
| Content | The screenshot must actually show what the actual result describes |
| Index | Add a row to `evidence/evidence-index.csv` for every file |
| Privacy | Run the pre-commit checklist before committing |

---

## Recording Results

Update `excel/03_test_execution.xlsx` as you go, one row per case. Then update
the matching row in `excel/02_test_cases.xlsx`.

Do not update `excel/06_test_summary.xlsx` by hand. Its figures are formulas that
read the execution sheet. Typing over them defeats the purpose.

---

## Suggested Order and Timing

| Block | Cases | Approx. time |
|---|---|---|
| Smoke | TC-001, TC-018, TC-022 | 20 min |
| Navigation | TC-002 to TC-007 | 50 min |
| Product | TC-008 to TC-017 | 90 min |
| Cart | TC-019 to TC-033 | 150 min |
| Registration and Account | TC-034 to TC-039 | 60 min |
| System | TC-040 | 10 min |

Roughly 6 to 7 hours total including evidence capture.
