# Jira Workflow Simulation (Jiraワークフロー)

**Board name:** EC-CUBE Manual QA Practice Board
**Type:** Practice simulation only

---

## Important

This is a **simulated Jira board created for practice**. It is not a real company
Jira project, not client work, and not evidence of professional Jira
administration. It demonstrates understanding of issue types, workflow states,
labelling, and how QA work is tracked.

The backlog is provided as `jira/jira-backlog.csv`, which can be imported into a
personal Jira Cloud site using the CSV import function.

---

## Workflow States

```
Backlog → To Do → In Progress → Ready for Test → Testing → Done
```

Additional terminal state: **Unable to Reproduce**

| State | Meaning |
|---|---|
| Backlog | Identified but not scheduled |
| To Do | Scheduled, not started |
| In Progress | Being worked on |
| Ready for Test | Work complete, awaiting verification |
| Testing | Verification in progress |
| Done | Verified and closed |
| Unable to Reproduce | A reported issue could not be repeated after investigation |

---

## Issue Types Used

| Type | Used for |
|---|---|
| Task | Preparation and setup work |
| Test | Test execution work |
| Bug | A reproduced defect. **None exist yet** |
| Documentation | Written deliverables |
| Improvement | Suggested enhancements. None raised |

---

## Current Board State

| Status | Count | Issues |
|---|---|---|
| Done | 8 | QA-1 to QA-7, QA-22 |
| In Progress | 1 | QA-21 |
| To Do | 8 | QA-8 to QA-13, QA-19, QA-20 |
| Backlog | 5 | QA-14 to QA-18 |
| **Total** | **22** | |

**Bug tickets: 0.** No defect has been reproduced, so no Bug issue exists.

---

## Note on QA-22

QA-22 is worth reading if you are reviewing this project.

During mobile observation, the header icons rendered as empty boxes. The obvious
move was to raise it as a defect. Instead the issue was re-tested in a standard
mobile browser, where the icons rendered correctly. The original observation had
been made inside an application's built-in browser, which was the actual cause.

The ticket was closed with resolution **Not a defect**.

This is recorded deliberately. Separating a genuine application defect from an
environment or tooling artefact is a core part of the job, and a defect report
raised without that check wastes developer time and damages the reporter's
credibility.

---

## Labels Used

`manual-testing`, `smoke-testing`, `negative-testing`, `test-case-design`,
`bug-reporting`, `test-evidence`, `documentation`, `excel`, `cart`, `navigation`,
`search`, `checkout`, `responsive`, `environment-limitation`, `portfolio-project`

---

## How to Import

1. Create a free personal Jira Cloud site
2. Create a project named **EC-CUBE Manual QA Practice Board**
3. Project settings → Import → CSV
4. Upload `jira/jira-backlog.csv`
5. Map the columns when prompted
6. Screenshot the resulting board and save it as `evidence/screenshots/jira-board.png`

Until that screenshot exists, this document describes a design, not a board that
has been built.
