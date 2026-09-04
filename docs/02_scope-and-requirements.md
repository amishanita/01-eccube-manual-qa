# 02. Scope and Requirements (テスト範囲と要件)

**Project:** EC-CUBE Manual QA Testing & Bug Reporting
**Project type:** Personal QA Portfolio Project
**Phase:** 2 of 15
**Based on:** `docs/01_application-analysis.md` (first observation session, 2026-09-01)

---

## 1. Project Objective

To design and execute a manual test of the EC-CUBE 4.2 public demo storefront,
covering the product browsing and shopping cart path, and to document the work
using standard QA artifacts: test plan, test scenarios, test cases, execution
records, defect reports, and a traceability matrix.

The purpose is to demonstrate manual QA practice. It is not an assessment of the
EC-CUBE product, and it is not commissioned work.

---

## 2. Application Under Test (対象アプリケーション)

| Item | Value |
|---|---|
| Application | EC-CUBE 4.2 Demo Site |
| Type | Japanese open source e-commerce platform |
| URL | https://ec-cube.sakura.ne.jp/4-2-demo/ |
| Environment type | Public shared demo |
| Storefront language | Japanese |

---

## 3. Test Environment (テスト環境)

| Item | Value |
|---|---|
| Environment ID | ENV-EC-001 |
| Operating system | macOS 15.2 (build 24C101) |
| Device | MacBook Pro |
| Display resolution | 3024 x 1964 (Retina) |
| Browser | Google Chrome (exact version to be recorded before execution) |
| Viewport | To be recorded before execution |
| Time zone | JST |

Results apply only to this environment, browser, and date. They are not general
statements about EC-CUBE.

---

## 4. In Scope (テスト対象)

Only features confirmed by direct observation are in scope.

| Module | Feature | Feature ID |
|---|---|---|
| Navigation | Home page rendering | F-001 |
| Navigation | Header navigation elements | F-002 |
| Navigation | Cart indicator in header | F-003 |
| Product | Product detail page | F-011 |
| Product | Product image display | F-012 |
| Product | Product price display | F-013 |
| Product | Product description display | F-014 |
| Product | Related category link display | F-015 |
| Cart | Add to cart | F-018 |
| Cart | Cart page display | F-019 |
| Cart | Cart quantity update and recalculation | F-020 |
| Cart | Cart persistence across navigation | F-022 |
| System | 404 error page | F-038 |

---

## 5. Out of Scope (テスト対象外)

### 5.1 Excluded because not yet observed

These are visible or unopened but have not been used. They will be added to scope
after a second observation session.

- Footer navigation (F-005)
- Product listing page (F-006)
- Keyword search and search results (F-007, F-008, F-009)
- Category filter dropdown (F-010)
- Category navigation result pages (F-004)
- Product variation / option selection (F-016)
- Quantity field on product detail page (F-017)
- Cart item removal (F-021)
- Guest checkout flow and all checkout steps (F-031 to F-037)
- Favourites (F-030)
- Responsive layout behaviour (F-041)
- Home page carousel behaviour (F-042)

### 5.2 Excluded because restricted or unavailable

These cannot be tested in this environment and will not be added later.

| Feature | Reason |
|---|---|
| Member registration completion | Email verification disabled |
| Member login | No usable account can be created |
| Logout | Requires a logged-in session |
| Password reset | Requires email delivery |
| Order history | Requires a member account |
| Email delivery | Disabled by the demo operator |
| Admin screen | Blocked in the public demo |
| Real payment processing | Must never be attempted |

### 5.3 Excluded by decision

- Performance and load testing. The environment is shared, and generating load
  would affect other users.
- Security testing. Not appropriate against a shared public site.
- Accessibility testing. Not covered by this project.
- Cross-browser testing. Only Google Chrome on macOS is used.
- API testing and automation. This is a manual testing project.

---

## 6. Functional Requirements (機能要件)

Requirements are written from observed behaviour, not from an EC-CUBE
specification document. No official specification was available, so expected
results are based on standard e-commerce behaviour and on what was actually seen.
This is stated openly because it affects how "expected result" should be read.

| Req ID | Module | Requirement | Source Feature |
|---|---|---|---|
| REQ-001 | Navigation | The home page shall load and display the site title, category navigation, and a hero content area | F-001 |
| REQ-002 | Navigation | The header shall display a product category dropdown, a keyword search field, and links for registration, favourites, and login | F-002 |
| REQ-003 | Navigation | The header cart indicator shall display the current item count and running total | F-003 |
| REQ-004 | Product | The product detail page shall display the product name | F-011 |
| REQ-005 | Product | The product detail page shall display at least one product image | F-012 |
| REQ-006 | Product | The product detail page shall display the price with a tax-inclusive label | F-013 |
| REQ-007 | Product | The product detail page shall display the product description | F-014 |
| REQ-008 | Product | The product detail page shall display the related category as a link | F-015 |
| REQ-009 | Cart | Selecting "add to cart" shall add the product and display a confirmation message | F-018 |
| REQ-010 | Cart | The cart page shall list each item with its name, unit price, quantity, and subtotal | F-019 |
| REQ-011 | Cart | The cart page shall display a checkout progress indicator showing the ordering steps | F-019 |
| REQ-012 | Cart | The cart quantity controls shall increase and decrease the quantity of an item | F-020 |
| REQ-013 | Cart | The item subtotal and cart total shall recalculate when quantity changes | F-020 |
| REQ-014 | Cart | Cart contents shall persist while the user navigates to other pages in the same session | F-022 |
| REQ-015 | System | An invalid URL shall display a "page not found" screen with a link back to the top page | F-038 |

**Total: 15 functional requirements.**

---

## 7. Non-Functional Scope

Only two non-functional aspects are in scope, and both are observational rather
than measured.

| Item | Approach |
|---|---|
| UI consistency | Confirm that page titles, labels, and currency formatting are consistent across the pages in scope |
| Visible error handling | Confirm that error states such as the 404 page present clear information and a recovery path |

Performance, load, security, and accessibility are out of scope.

---

## 8. Assumptions (前提条件)

1. The demo site remains publicly reachable during the test period.
2. Product data exists in the store at execution time. Because data resets hourly,
   the specific product used may differ between sessions.
3. The tester is not logged in. All testing is performed as a guest.
4. Standard e-commerce behaviour is a reasonable basis for expected results, since
   no formal specification is available.
5. Only fictional data is entered at any point.

---

## 9. Risks (リスク)

| Risk ID | Risk | Impact | Mitigation |
|---|---|---|---|
| RSK-01 | Data resets approximately hourly, so a product used in a test case may disappear | Test case becomes unrunnable mid-session | Record the product name and price in the execution record. If the product is gone, mark Blocked and re-run with a current product |
| RSK-02 | The environment is shared, so another user may change cart or product data | An observed result may not be caused by the application | Repeat any unexpected result at least twice before recording it as a defect |
| RSK-03 | No official specification is available | Expected results are based on judgement, not documentation | State this openly in the test plan and keep expected results conservative |
| RSK-04 | Only one browser and one viewport are used | Findings may be Chrome-specific | Record browser and viewport on every execution record. Do not generalise results |
| RSK-05 | Real personal data could be entered by mistake | Privacy exposure in a public repository | Follow the test data guide and run the pre-commit checklist before every commit |
| RSK-06 | An environment restriction could be mistaken for a defect | False defect report damages credibility | Check every suspected issue against the known limitations list before raising it |

---

## 10. Known Limitations (既知の制約)

| ID | Limitation |
|---|---|
| LIM-01 | Site data resets automatically approximately every hour |
| LIM-02 | All email delivery is disabled |
| LIM-03 | Member registration cannot be completed, so member login is not possible |
| LIM-04 | The admin screen is not accessible |
| LIM-05 | The environment is shared with other public users |
| LIM-06 | Real personal data must never be entered |

These are documented characteristics of the demo. They are never reported as
defects.

---

## 11. Entry Criteria (開始基準)

Testing may begin when all of the following are true:

1. The application analysis is complete and the scope is agreed.
2. The demo site is reachable and the home page loads.
3. At least one purchasable product is present in the store.
4. Test scenarios and test cases are written and reviewed.
5. Fictional test data is defined.
6. The exact browser version and viewport are recorded.
7. Screenshot capture and the evidence naming convention are ready.

---

## 12. Exit Criteria (終了基準)

Testing is complete when all of the following are true:

1. Every in-scope test case has a status of Passed, Failed, Blocked, or Not Applicable.
2. No test case remains Not Executed without a documented reason.
3. Every Failed test case has a matching defect report with reproduction steps.
4. Every defect has been reproduced at least twice, or is explicitly marked Unable to Reproduce.
5. Every executed test case has evidence recorded in the evidence index.
6. The traceability matrix shows coverage status for all 15 requirements.
7. The test summary report is calculated from actual execution records only.
8. The pre-commit privacy checklist has been completed.

---

## 13. Test Deliverables (成果物)

| Deliverable | Location | Status |
|---|---|---|
| Application analysis | `docs/01_application-analysis.md` | Complete (partial observation) |
| Scope and requirements | `docs/02_scope-and-requirements.md` | Complete |
| Test plan | `docs/03_test-plan.md` | Complete |
| Test scenarios | `docs/04_test-scenarios.md` | Pending |
| Manual test cases | `test-cases/manual-test-cases.md` | Pending |
| Test data guide | `test-data/test-data-guide.md` | Complete |
| Excel workbooks | `excel/` | Pending |
| JSON files | `test-cases/`, `bug-reports/`, `reports/` | Pending |
| Execution records | `reports/test-execution-results.json` | Pending |
| Defect reports | `bug-reports/` | Pending |
| Traceability matrix | `reports/rtm.md` | Pending |
| Test summary report | `reports/test-summary-report.md` | Pending |
| Evidence index | `evidence/evidence-index.csv` | In progress |

---

## 14. Document Control

| Version | Date | Change |
|---|---|---|
| 0.1 | 2026-09-01 | Initial scope based on 13 confirmed features and 15 requirements |
