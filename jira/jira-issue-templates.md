# Jira Issue Templates

Templates for the EC-CUBE Manual QA Practice Board.

---

## Bug Template

```
Summary: [What fails] [where] [under what condition]

Environment:
  Environment ID: ENV-EC-001
  Application: EC-CUBE 4.2.3 Demo Site
  URL: https://ec-cube.sakura.ne.jp/4-2-demo/
  OS: macOS 15.2
  Browser: Google Chrome [version]

Preconditions:
  [State required before step 1]

Steps to Reproduce:
  1.
  2.
  3.

Test Data:
  [Exact values used. Fictional data only]

Expected Result:
  [What should happen, and why that expectation is justified]

Actual Result:
  [What actually happened]

Reproducibility: Always / Intermittent / Once / Unable to Reproduce
Attempts: [how many times tried, how many times it failed]

Severity: Critical / High / Medium / Low
Priority: High / Medium / Low

Evidence: BUG-00X-reproduction.png
Related Test Case: TC-0XX

Environment check:
  [ ] Repeated at least twice
  [ ] Checked against known limitations
  [ ] Tried in a clean session
  [ ] Not caused by a data reset or another user
```

---

## Test Execution Template

```
Summary: Execute [module] test cases

Test Cases: TC-0XX to TC-0XX
Environment ID: ENV-EC-001
Browser: Google Chrome [version]
Execution Date:

Results:
  Passed:
  Failed:
  Blocked:
  Not Applicable:

Evidence: [filenames]
Defects raised: [Bug IDs, or none]
```

---

## Task Template

```
Summary: [Action] [object]

Description:
  [What needs doing and why]

Acceptance Criteria:
  - [ ]
  - [ ]

Deliverable: [file path in the repository]
```

---

## Documentation Template

```
Summary: [Create or update] [document]

File: docs/XX_name.md

Acceptance Criteria:
  - [ ] Content reflects only confirmed observations
  - [ ] No fabricated results or metrics
  - [ ] Environment details are accurate
  - [ ] Cross-references to other documents are correct
```
