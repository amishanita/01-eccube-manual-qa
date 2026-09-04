# Bug Reports (不具合報告)

**Project:** EC-CUBE Manual QA Testing & Bug Reporting
**Application:** EC-CUBE 4.2.3 Demo Site

---

## Current Status: No Defects Recorded

No reproducible defect has been confirmed in the test environment.

This section is empty by design. A defect report is added only after an issue has
been reproduced at least twice, checked against the known environment
limitations, and supported by evidence.

Zero defects is a legitimate test result. It does not mean testing was
insufficient, and it is not a gap to be filled with invented entries.

---

## Verified Non-Defects

Issues that were investigated and correctly ruled out. These are recorded because
distinguishing an application defect from an environment artefact is part of the
work, and the record shows the check was actually performed.

### NDF-001 — Header icons rendered as empty boxes on mobile

| Field | Value |
|---|---|
| Observation ID | NDF-001 |
| First observed | 2026-09-02, approx. 08:33 JST |
| Module | Navigation |
| Initial environment | In-app browser within the Claude iOS application |
| Observation | The four header icons (account, favourites, login, cart) rendered as empty squares with a diagonal cross, the typical appearance of an icon font that has failed to load |
| Initial assessment | Suspected mobile rendering defect |
| Verification steps | 1. Opened https://ec-cube.sakura.ne.jp/4-2-demo/ directly in Google Chrome for iOS<br>2. Observed the header region<br>3. Compared against the initial observation |
| Verification environment | ENV-EC-002, Google Chrome for iOS, iPhone |
| Verification result | All four icons rendered correctly as intended. The mobile layout also displayed a hamburger menu control not present on desktop |
| Conclusion | **Not a defect.** The rendering failure was caused by the in-app browser used for the initial observation, not by the application |
| Evidence | MOB-001-inapp-browser-icons.png, MOB-002-chrome-ios-icons.png |
| Jira reference | QA-22, closed with resolution "Not a defect" |

**Why this is recorded:** the obvious action was to raise a bug. Verifying in a
standard browser first prevented a false report. A defect raised without that
check wastes developer time and damages the reporter's credibility.

---

## Open Items Under Investigation

Items observed but not yet resolved either way. Neither defects nor confirmed
correct behaviour.

### OPEN-02 — 404 page appeared, trigger unknown

A page-not-found screen was captured during the first observation session. The
URL and the preceding action were not recorded, so the cause is unknown.

**Status:** Unable to Verify
**Next step:** identify the exact URL that produced it, then attempt to repeat it twice

### OPEN-03 — Katakana field format validation outcome unknown

Romaji values (`ramu`, `amsu`) were entered into the お名前(カナ) fields, which are
labelled for katakana input. The form was never resubmitted after those values
were entered, so it is unknown whether the application accepts or rejects them.

**Status:** Not Executed
**Related test case:** TC-037
**Next step:** complete the form with approved fictional data, leave romaji in the katakana fields, submit, and record whether validation fires

If romaji is accepted, this becomes a defect candidate requiring two reproductions
before it is raised. If it is rejected, TC-037 simply passes.

---

## Bug ID Allocation

Bug IDs are assigned sequentially from BUG-001 at the point a defect is confirmed.
None has been allocated.
