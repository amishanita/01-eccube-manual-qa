# 04. Test Scenarios (テストシナリオ)

**Project:** EC-CUBE Manual QA Testing & Bug Reporting
**Phase:** 4 of 15
**Environment:** ENV-EC-001, Google Chrome on macOS 15.2
**Based on:** confirmed observations from sessions on 2026-09-01

---

## 1. Purpose

Scenarios group related test cases by user goal. Each scenario below covers a
feature that was confirmed working by direct observation. Features that were not
executed during observation have no scenario and are listed in section 3.

---

## 2. Scenario List

| Scenario ID | Module | Scenario | Objective | Test Type | Priority | Preconditions | Scope Status | Notes |
|---|---|---|---|---|---|---|---|---|
| SCN-001 | Navigation | Home page loads with all primary regions | Confirm the storefront entry point renders header, title, category links, hero carousel, and content sections | Smoke, UI | High | Browser open, no cart contents required | In Scope | Confirmed during observation |
| SCN-002 | Navigation | Header controls are present and correctly labelled | Confirm the category dropdown, keyword field, registration, favourites, login, and cart indicator all render | Functional, UI | High | Home page loaded | In Scope | Confirmed |
| SCN-003 | Navigation | Cart indicator reflects the current cart state | Confirm the header count and total change as items are added and quantities change | Functional | High | At least one purchasable product exists | In Scope | Observed changing 0/¥0 → 1/¥1,100 → 2/¥20,900 |
| SCN-004 | Navigation | Category links filter the product listing | Confirm each header category link opens a filtered product listing | Functional | High | Home page loaded | In Scope | ジェラート confirmed at category_id=1 |
| SCN-005 | Product | Product listing page displays results and controls | Confirm the listing shows a result count, product tiles, and the per-page and sort controls | Functional, UI | Medium | A category has been opened | In Scope | Confirmed: 1件の商品が見つかりました, 20件, 価格が低い順 |
| SCN-006 | Product | Product detail page displays complete product information | Confirm name, image, tax-inclusive price, description, and related category all appear | Functional, UI | High | A product exists in the store | In Scope | Confirmed on ブーケクリアポーチ |
| SCN-007 | Product | Products with options display variation selectors | Confirm a product with variations shows selector controls and a price range | Functional | High | A product with options exists | In Scope | Confirmed on 彩のジェラートCUBE, ¥19,800 〜 ¥121,000 |
| SCN-008 | Cart | A product can be added to the cart from the detail page | Confirm the add action succeeds and a confirmation is shown | Functional, Smoke | High | Product detail page open | In Scope | Confirmation modal カートに追加しました。 observed |
| SCN-009 | Cart | A product can be added to the cart from the listing page | Confirm the listing-page add control works without opening the detail page | Functional | Medium | Product listing page open | In Scope | Confirmed during video session |
| SCN-010 | Cart | The cart page displays items, quantities, and totals | Confirm the cart table and the five-step checkout progress indicator render correctly | Functional, UI | High | At least one item in cart | In Scope | Confirmed |
| SCN-011 | Cart | Cart quantity can be increased and decreased | Confirm the plus and minus controls change the quantity | Functional | High | At least one item in cart | In Scope | Confirmed 1 ⇄ 2 |
| SCN-012 | Cart | Subtotal and total recalculate when quantity changes | Confirm arithmetic is correct after every quantity change | Functional | High | At least one item in cart | In Scope | ¥1,100 → ¥2,200 confirmed |
| SCN-013 | Cart | The cart correctly holds multiple different products | Confirm two distinct products coexist with correct individual and combined totals | Functional | High | Two products available | In Scope | ¥1,100 + ¥19,800 = ¥20,900 confirmed |
| SCN-014 | Cart | Selected variations are displayed in the cart | Confirm option values chosen on the product page appear against the cart line | Functional | Medium | A variation product added | In Scope | フレーバー：チョコ / サイズ：64cm × 64cm confirmed |
| SCN-015 | Cart | Cart contents persist while browsing other pages | Confirm the cart survives navigation within the same session | Functional | High | At least one item in cart | In Scope | Confirmed across cart → login → home |
| SCN-016 | Account | The registration form displays all expected fields | Confirm every field, required marker, and control renders | Functional, UI | Medium | Registration page open | In Scope | Confirmed |
| SCN-017 | Account | Registration rejects submission with all fields empty | Confirm client validation blocks submission and marks every required field | Negative | High | Registration page open | In Scope | 入力されていません。 confirmed on all required fields |
| SCN-018 | Account | The postal code lookup link opens the external service | Confirm the 郵便番号検索 link opens Japan Post in a new tab | Functional | Low | Registration page open | In Scope | Confirmed opening post.japanpost.jp |
| SCN-019 | Account | The login page displays the expected form | Confirm email field, password field, remember checkbox, and the two support links render | Functional, UI | Medium | Login page open | In Scope | Confirmed at /mypage/login |
| SCN-020 | System | An invalid URL returns a usable error page | Confirm the 404 page shows a message and a route back to the top page | Negative | Medium | Browser open | In Scope | Confirmed |

**Total scenarios in scope: 20**

---

## 3. Deferred Scenarios

These are not written as scenarios because the underlying feature has not been
executed and observed. They will be added after a further observation session.

| Feature | Reason deferred |
|---|---|
| Keyword search execution and results | Search has never been run |
| Search empty-state handling | Not executed |
| Search category dropdown filtering | Dropdown value changed but no search submitted |
| Cart item removal via the × control | Control visible, never clicked |
| Guest checkout flow | Never entered beyond the login screen |
| Checkout form validation | Never reached |
| Delivery and payment selection | Never reached |
| Order completion | Never reached |
| Responsive layout behaviour | Only one viewport used |
| Carousel auto-rotation and manual navigation | Not verified |
| Katakana field format validation | Romaji entered but the form was never resubmitted, so the outcome is unknown. See OPEN-03 |

---

## 4. Open Item

### OPEN-03 — Katakana field format validation outcome unknown

During the second observation session, the values `ramu` and `amsu` were entered
into the お名前(カナ) fields, which are labelled for katakana input. The form was
not resubmitted after these values were entered, so it is not known whether the
application accepts or rejects romaji in a katakana field.

**Required action:** enter romaji into both katakana fields, complete the other
required fields with approved fictional data, and submit. Record whether a
validation message appears.

**If romaji is accepted:** this is a potential defect and requires two
reproductions before being raised.
**If romaji is rejected:** this is a passed negative test case.

Until this is executed, no claim is made either way.
