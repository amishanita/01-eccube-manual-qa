# Requirements Traceability Matrix (要件トレーサビリティマトリクス)

**Project:** EC-CUBE Manual QA Testing & Bug Reporting
**Requirements:** 27 | **Scenarios:** 20 | **Test Cases:** 40
**Execution status:** Not started. All coverage is Pending Confirmation.

Coverage is marked **Covered** only after the mapped test cases have been
executed. Designing a test case is not coverage.

| Requirement ID | Requirement Description | Module | Scenario ID | Test Case ID | Test Case Status | Defect ID | Defect Status | Coverage Status | Notes |
|---|---|---|---|---|---|---|---|---|---|
| REQ-001 | Home page loads with title, category navigation and hero area | Navigation | SCN-001 | TC-001 | Not Executed | — | — | Pending Confirmation | — |
| REQ-002 | Header displays category dropdown, keyword field and account links | Navigation | SCN-002 | TC-002, TC-003 | Not Executed | — | — | Pending Confirmation | — |
| REQ-003 | Header cart indicator shows item count and running total | Navigation | SCN-003 | TC-004, TC-019 | Not Executed | — | — | Pending Confirmation | — |
| REQ-004 | Category links open a filtered product listing | Navigation | SCN-004 | TC-005, TC-006 | Not Executed | — | — | Pending Confirmation | — |
| REQ-005 | Listing displays a result count matching products shown | Product | SCN-005 | TC-008 | Not Executed | — | — | Pending Confirmation | — |
| REQ-006 | Listing provides per-page and sort order controls | Product | SCN-005 | TC-009, TC-010 | Not Executed | — | — | Pending Confirmation | TC-010 requires a category with 2+ products |
| REQ-007 | Product detail page displays the product name | Product | SCN-006 | TC-011 | Not Executed | — | — | Pending Confirmation | — |
| REQ-008 | Product detail page displays product images | Product | SCN-006 | TC-012 | Not Executed | — | — | Pending Confirmation | — |
| REQ-009 | Price displayed with a tax-inclusive label | Product | SCN-006 | TC-013 | Not Executed | — | — | Pending Confirmation | — |
| REQ-010 | Product description is displayed | Product | SCN-006 | TC-014 | Not Executed | — | — | Pending Confirmation | — |
| REQ-011 | Related category displayed as a working link | Product | SCN-006 | TC-015, TC-016 | Not Executed | — | — | Pending Confirmation | — |
| REQ-012 | Variation products show selectors and a price range | Product | SCN-007 | TC-017, TC-021 | Not Executed | — | — | Pending Confirmation | TC-021 expectation is judgement-based, not specified |
| REQ-013 | A product can be added to the cart | Cart | SCN-008, SCN-009 | TC-018, TC-020 | Not Executed | — | — | Pending Confirmation | Covers both detail page and listing page |
| REQ-014 | Header cart indicator updates immediately after adding | Cart | SCN-003 | TC-019 | Not Executed | — | — | Pending Confirmation | — |
| REQ-015 | Cart lists name, unit price, quantity and subtotal | Cart | SCN-010 | TC-022 | Not Executed | — | — | Pending Confirmation | — |
| REQ-016 | Cart displays the five-step checkout progress indicator | Cart | SCN-010 | TC-023 | Not Executed | — | — | Pending Confirmation | — |
| REQ-017 | Cart quantity can be increased and decreased | Cart | SCN-011 | TC-024, TC-025 | Not Executed | — | — | Pending Confirmation | — |
| REQ-018 | Subtotal and total recalculate after a quantity change | Cart | SCN-012 | TC-026, TC-027 | Not Executed | — | — | Pending Confirmation | — |
| REQ-019 | Cart holds multiple products with correct combined totals | Cart | SCN-013 | TC-028, TC-029 | Not Executed | — | — | Pending Confirmation | — |
| REQ-020 | Option values displayed and priced correctly in the cart | Cart | SCN-014 | TC-030, TC-031 | Not Executed | — | — | Pending Confirmation | — |
| REQ-021 | Cart persists across navigation and reload | Cart | SCN-015 | TC-032, TC-033 | Not Executed | — | — | Pending Confirmation | TC-033 reload behaviour not yet observed |
| REQ-022 | Registration form displays all fields with required markers | Registration | SCN-016 | TC-034 | Not Executed | — | — | Pending Confirmation | — |
| REQ-023 | Registration rejects submission with empty required fields | Registration | SCN-017 | TC-035, TC-036 | Not Executed | — | — | Pending Confirmation | Behaviour observed during analysis, not yet formally executed |
| REQ-024 | Katakana name fields reject non-katakana input | Registration | SCN-017 | TC-037 | Not Executed | — | — | Pending Confirmation | Highest-value case in the suite. Outcome unknown. See OPEN-03 |
| REQ-025 | Postal code lookup opens the external search service | Registration | SCN-018 | TC-038 | Not Executed | — | — | Pending Confirmation | — |
| REQ-026 | Login page displays credential fields and support links | Account | SCN-019 | TC-039 | Not Executed | — | — | Pending Confirmation | Successful login is Not Applicable in this environment |
| REQ-027 | Invalid URL returns a page-not-found screen with a route back | System | SCN-020 | TC-040 | Not Executed | — | — | Pending Confirmation | — |

## Coverage Summary

| Coverage Status | Count |
|---|---|
| Covered | 0 |
| Partially Covered | 0 |
| Not Covered | 0 |
| Not Applicable | 0 |
| Pending Confirmation | 27 |

Every requirement has at least one designed test case, so there are no orphan
requirements. No requirement is confirmed covered because execution has not begun.

## Requirements Deliberately Not Written

No requirements were written for search, cart item removal, guest checkout,
delivery, payment, order completion, member login, logout, password reset, email
delivery, or the admin screen. Those features are either unobserved or
unavailable in this environment. Writing requirements for them would create
traceability rows that could never be honestly closed.
