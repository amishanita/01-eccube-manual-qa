# 03. Test Plan (テスト計画書)

**Project:** EC-CUBE Manual QA Testing & Bug Reporting
**Project type:** Personal QA Portfolio Project
**Phase:** 3 of 15

---

## 1. Document Control

| Item | Value |
|---|---|
| Document | Test Plan |
| Version | 0.1 |
| Date | 2026-09-01 |
| Author | Personal portfolio project author |
| Status | Draft — approved for test design |
| Based on | `docs/01_application-analysis.md`, `docs/02_scope-and-requirements.md` |

---

## 2. Project Overview

This plan covers a manual test of the browsing and shopping cart path of the
EC-CUBE 4.2 public demo storefront. It is a personal portfolio project. There is
no client, no release, and no production system involved.

The plan is deliberately narrow. The environment restricts member accounts,
email, and the admin screen, and only a limited set of features has been
confirmed by direct observation. Testing something that has not been seen would
produce documentation without substance, so scope is limited to what was
actually verified.

---

## 3. Objective

1. Verify that the confirmed browsing and cart features behave consistently with
   standard e-commerce expectations.
2. Identify and document any reproducible defects.
3. Produce a complete and traceable set of QA artifacts.
4. Keep a clear separation between application defects and environment
   restrictions.

---

## 4. Application Under Test

| Item | Value |
|---|---|
| Application | EC-CUBE 4.2 Demo Site |
| URL | https://ec-cube.sakura.ne.jp/4-2-demo/ |
| Environment type | Public shared demo |
| Language | Japanese |

---

## 5. Environment

| Item | Value |
|---|---|
| Environment ID | ENV-EC-001 |
| Operating system | macOS 15.2 (build 24C101) |
| Device | MacBook Pro |
| Display | 3024 x 1964 Retina |
| Browser | Google Chrome (version not recorded) |
| Viewport | To be recorded |
| Tester role | Guest, not logged in |

---

## 6. Scope

13 confirmed features across four modules, mapped to 15 functional requirements.
See `docs/02_scope-and-requirements.md` section 4 and section 6.

Modules in scope: Navigation, Product, Cart, System error handling.

---

## 7. Out of Scope

Search, category result pages, product listing, cart item removal, checkout,
member accounts, email, admin, payment, responsive layout, performance,
security, accessibility, cross-browser, automation.

Full list with reasons: `docs/02_scope-and-requirements.md` section 5.

---

## 8. Test Approach

Testing is manual and exploratory-informed. The approach is:

1. **Design first.** Write scenarios and test cases before execution, so results
   are compared against a stated expectation rather than judged after the fact.
2. **Execute one case at a time.** Record the actual result immediately, in the
   tester's own words, before moving on.
3. **Capture evidence at the point of observation.** A screenshot taken later is
   not evidence of what happened earlier.
4. **Confirm before reporting.** Any unexpected result is repeated at least twice
   and checked against the known limitations list before it is treated as a
   defect.
5. **Record blockers honestly.** If a test cannot run because a product has
   disappeared in a data reset, the status is Blocked, not Failed.

### Note on expected results

No official EC-CUBE specification was available for this environment. Expected
results are therefore based on two things: behaviour actually observed during
the analysis session, and standard e-commerce conventions. This is a real
limitation of the project and is stated openly rather than hidden. Where an
expectation is a judgement call rather than a confirmed rule, the test case says
so in its notes.

---

## 9. Test Types (テストの種類)

| Type | Applied to |
|---|---|
| Functional Testing (機能テスト) | All in-scope features |
| Smoke Testing (スモークテスト) | Home page load, product page load, add to cart, cart page load. Run first in each session to confirm the environment is usable |
| Negative Testing (異常系テスト) | Invalid URL handling, quantity decrease at the lower boundary |
| Boundary Value Testing (境界値テスト) | Cart quantity at its minimum value |
| UI Testing (UIテスト) | Label consistency, currency formatting, presence of required page elements |
| Exploratory Testing (探索的テスト) | A short timeboxed session after scripted execution, to look for issues the test cases do not cover |

Regression testing (回帰テスト) is **not** included in this plan. There is no
build cycle and no code change to regress against. It will be added only if a
defect is fixed and requires re-verification, which is unlikely on a demo site
outside the tester's control. Listing it without cause would be padding.

---

## 10. Test Design Techniques (テスト設計技法)

| Technique | Use |
|---|---|
| Equivalence Partitioning (同値分割) | Valid URL versus invalid URL for error page testing |
| Boundary Value Analysis (境界値分析) | Cart quantity minimum, decrease below 1 |
| State Transition (状態遷移) | Cart state across empty, one item, two items, and after navigation |
| Checklist-based | Presence of required elements on the product detail page and cart page |
| Error Guessing | Exploratory session at the end of execution |

---

## 11. Test Data Strategy

Only fictional data is used. The full policy, approved values, and pre-commit
checklist are in `test-data/test-data-guide.md`.

Because no form is currently in scope, no customer data is required for this
round of execution. Product data is taken from whatever products exist in the
store at execution time. The specific product name and price used must be
recorded in each execution record, because data resets hourly and the product may
differ between sessions.

---

## 12. Entry Criteria

See `docs/02_scope-and-requirements.md` section 11.

---

## 13. Exit Criteria

See `docs/02_scope-and-requirements.md` section 12.

---

## 14. Suspension Criteria (中断基準)

Testing is suspended if any of the following occurs:

1. The demo site becomes unreachable or returns server errors on the home page.
2. The store contains no purchasable products.
3. A data reset occurs mid-execution and invalidates the current test case.
4. Behaviour suggests another user is actively modifying shared data in a way that
   makes results unreliable.
5. Real personal data is entered by mistake and requires cleanup before continuing.

---

## 15. Resumption Criteria (再開基準)

Testing resumes when:

1. The site loads normally and at least one product is available.
2. The environment state has been re-confirmed with a smoke test.
3. Any test case interrupted by a reset is restarted from step 1, not continued
   from the middle.
4. Any privacy issue has been resolved.

---

## 16. Deliverables

See `docs/02_scope-and-requirements.md` section 13.

---

## 17. Risks

See `docs/02_scope-and-requirements.md` section 9. The two with the most impact
on execution:

- **RSK-01, hourly data reset.** Expect at least one test case to be interrupted.
  Plan execution in blocks shorter than one hour.
- **RSK-02, shared environment.** Any single odd observation is not trustworthy.
  Repeat before recording.

---

## 18. Assumptions

See `docs/02_scope-and-requirements.md` section 8.

---

## 19. Known Limitations

See `docs/02_scope-and-requirements.md` section 10.

Additional limitation specific to this plan: the first observation session lasted
approximately four minutes and covered the primary path only. The confirmed
feature set is therefore small, and the test suite is correspondingly small. A
second observation session is required to expand scope to search, checkout, and
cart item removal.

---

## 20. Defect Management Process (不具合管理プロセス)

### Before raising a defect

1. Repeat the steps at least twice.
2. Check the known limitations list. If the behaviour is a documented restriction,
   it is not a defect.
3. Consider whether another user or a data reset could explain it.
4. Confirm the expected result is actually justified, not just assumed.

### Defect record contents

Bug ID, title, module, environment, preconditions, exact steps to reproduce, test
data, expected result, actual result, reproducibility, severity, priority, status,
evidence filename, related test case, reported date, retest result, notes.

### Workflow

```
Backlog → To Do → In Progress → Ready for Test → Testing → Done
```

Additional terminal status: **Unable to Reproduce**.

### Severity (重要度)

| Level | Meaning |
|---|---|
| Critical | Core purchase path is blocked, or data is lost or incorrect |
| High | A major function does not work, with no workaround |
| Medium | A function works incorrectly but a workaround exists |
| Low | Cosmetic or minor wording issue with no functional impact |

### Priority (優先度)

| Level | Meaning |
|---|---|
| High | Should be fixed before release |
| Medium | Should be fixed in a normal cycle |
| Low | Fix when convenient |

### Reproducibility

Always / Intermittent / Once / Unable to Reproduce.

---

## 21. Test Evidence Process

| Rule | Detail |
|---|---|
| Naming | `ENV-`, `FEAT-`, `TC-`, `BUG-`, `RESP-` prefixes with a sequence number and short description |
| Capture timing | At the moment of observation |
| Indexing | Every file recorded in `evidence/evidence-index.csv` with capture time, environment ID, related IDs, and purpose |
| Privacy | Every file checked against the pre-commit checklist before committing |
| Video | Used only for multi-step flows or defect reproduction, not for single screens |
| Prohibited | Fabricated, edited, or re-created evidence |

---

## 22. Review Record

| Item | Status |
|---|---|
| Scope reviewed against confirmed features only | Yes |
| Out-of-scope items justified with a reason | Yes |
| Environment restrictions separated from defects | Yes |
| Test types limited to those actually applied | Yes |
| Test data policy in place before execution | Yes |
| Peer review | Not applicable. This is a solo portfolio project and no second reviewer exists |

---

## 23. Document Control History

| Version | Date | Change |
|---|---|---|
| 0.1 | 2026-09-01 | Initial test plan for the confirmed browsing and cart scope |
