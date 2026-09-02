# 01. Application Analysis (アプリケーション分析)

**Project:** EC-CUBE Manual QA Testing & Bug Reporting
**Project type:** Personal QA Portfolio Project
**Phase:** 1 of 15 — Application Analysis
**Document status:** Draft — partial observation completed

---

## 1. Purpose

This document records which EC-CUBE features were actually observed in the test
environment. Nothing in this file is assumed. A feature is only marked
"Confirmed Available" when it was used and the result was captured as evidence.

Features that were not opened, or were only seen as a link or button, are marked
accordingly and are excluded from the current test scope.

---

## 2. Test Environment (テスト環境)

| Item | Value |
|---|---|
| Environment ID | ENV-EC-001 |
| Environment type | Public demo environment (shared) |
| Application | EC-CUBE 4.2.3 Demo Site |
| Base URL | https://ec-cube.sakura.ne.jp/4-2-demo/ |
| Operating system | macOS 15.2 (build 24C101) |
| Device | MacBook Pro |
| Display resolution | 3024 x 1964 (Retina) |
| Browser | Google Chrome (version not recorded) |
| Browser viewport | TO BE CONFIRMED |
| Storefront language | Japanese |
| Observation date | 2026-09-01 (令和8年9月1日) |
| Observation time | Approx. 23:23 – 23:27 JST |
| Session duration | Session 1: approx. 4 minutes. Session 2: approx. 4 minutes recorded video plus mobile verification |
| Observer | Personal portfolio project author |

**Note on session duration:** this was a short first pass. It is enough to
confirm the core browsing and cart path only. Several modules remain unobserved
and are excluded from scope until a longer session is completed.

---

## 3. Known Environment Restrictions (環境制約)

These are documented characteristics of the public demo. They are **environment
limitations, not defects**, and must never be reported as bugs.

| ID | Restriction | Source |
|---|---|---|
| LIM-01 | Site data resets automatically approximately every hour | Publicly documented demo notice |
| LIM-02 | All email delivery is disabled | Publicly documented demo notice |
| LIM-03 | Because email is disabled, new member registration cannot be completed, so member login is not achievable | Publicly documented demo notice |
| LIM-04 | The admin screen (`/admin/`) is not accessible | Publicly documented demo notice |
| LIM-05 | The environment is shared with other public users, so product and order data may be changed by others during a session | Publicly documented demo notice |
| LIM-06 | Real personal data must never be entered, as the site is public and shared | Publicly documented demo notice |

**Impact on testing:** member account features (registration completion, login,
logout, password reset, order history, favourites) cannot be tested in this
environment. Purchase testing, if attempted, must use the guest purchase path
only, with fictional data.

---

## 4. Feature Analysis

### Status values used

| Status | Meaning |
|---|---|
| Confirmed Available | Feature was used and behaviour was observed with evidence |
| Visible Only | Element is visible on screen but was not used or its result was not captured |
| Restricted | Feature exists but cannot be completed in this environment |
| Not Available in Test Environment | Feature is blocked or removed in this environment |
| Not Applicable | Feature does not apply to this environment |
| Not Yet Observed | Feature was not opened during the observation session |
| Unable to Verify | Feature could not be checked due to a temporary problem |

### Analysis table

| Feature ID | Module | Feature | Status | Evidence ID | Included in Scope | Notes |
|---|---|---|---|---|---|---|
| F-001 | Navigation | Home page loads | Confirmed Available | ENV-001 | Yes | Page title "EC-CUBE4.2 デモサイト", hero carousel with 3 slide indicators, "CUBE GELATO ICE" content section below |
| F-002 | Navigation | Header navigation | Confirmed Available | ENV-001 | Yes | Contains: 全ての商品 dropdown, keyword search field, 新規会員登録, お気に入り, ログイン, cart icon with item count and running total |
| F-003 | Navigation | Cart total indicator in header | Confirmed Available | FEAT-002, FEAT-003, FEAT-006 | Yes | Observed changing from 0 / ¥0 to 1 / ¥1,100 to 2 / ¥2,200 as cart contents changed |
| F-004 | Navigation | Category navigation links | Confirmed Available | ENV-001, VID-001 | Yes | Four links visible. ジェラート clicked and confirmed opening /products/list?category_id=1 with a filtered result count|
| F-005 | Navigation | Footer navigation | Not Yet Observed | — | No | Page was not scrolled to the footer |
| F-006 | Product | Product listing page | Confirmed Available | VID-001 | Yes | Listing page confirmed with result count text 1件の商品が見つかりました, product tiles, per-page control 20件 and sort control 価格が低い順|
| F-007 | Search | Keyword search field | Visible Only | ENV-001 | No | Field with placeholder キーワードを入力 and a search icon is present in the header. No search was executed |
| F-008 | Search | Search results (matching keyword) | Not Yet Observed | — | No | Not executed |
| F-009 | Search | Search results (no match / empty state) | Not Yet Observed | — | No | Not executed |
| F-010 | Search | Category filter dropdown (全ての商品) | Visible Only | ENV-001 | No | Dropdown control visible next to search field. Options were not opened |
| F-011 | Product | Product detail page | Confirmed Available | FEAT-002 | Yes | Product ブーケクリアポーチ opened successfully |
| F-012 | Product | Product image | Confirmed Available | FEAT-002 | Yes | Main image plus one thumbnail below. Thumbnail switching was not tested |
| F-013 | Product | Product price | Confirmed Available | FEAT-002 | Yes | Displayed as ￥1,100 with 税込 (tax included) label |
| F-014 | Product | Product description | Confirmed Available | FEAT-002 | Yes | Japanese description text displayed under the action buttons |
| F-015 | Product | Related category link | Confirmed Available | FEAT-002 | Yes | 関連カテゴリ section shows link 新入荷. Link was not clicked |
| F-016 | Product | Product variation / option selection | Confirmed Available | VID-001 | Yes | Product 彩のジェラートCUBE displays two option selectors and a price range ￥19,800 〜 ￥121,000|
| F-017 | Product | Quantity field on product detail page | Visible Only | FEAT-002 | No | Numeric field showing 1. Value was not changed before adding to cart |
| F-018 | Cart | Add to cart | Confirmed Available | FEAT-003 | Yes | Button カートに入れる triggered a modal reading カートに追加しました。 with options お買い物を続ける and カートへ進む. Header cart count incremented |
| F-019 | Cart | Cart page | Confirmed Available | FEAT-004, FEAT-005 | Yes | Page ショッピングカート displays a 5-step progress indicator: カートの商品 → お客様情報 → ご注文手続き → ご注文内容確認 → 完了. Table columns: 削除 / 商品内容 / 数量 / 小計 |
| F-020 | Cart | Cart quantity update | Confirmed Available | FEAT-004, FEAT-005 | Yes | Minus and plus controls observed. Quantity 2 with subtotal ￥2,200 and quantity 1 with subtotal ￥1,100 both captured. Total recalculated correctly in both states |
| F-021 | Cart | Cart item removal | Visible Only | FEAT-004 | No | An × control is present in the 削除 column. It was not used |
| F-022 | Cart | Cart persistence across pages | Confirmed Available | FEAT-006 | Yes | Header cart indicator still showed 1 item / ￥1,100 after navigating from the cart to the login page |
| F-023 | Account | Registration form display | Confirmed Available | FEAT-001, VID-001 | Yes | Full field list confirmed including 電話番号, メールアドレス, パスワード (半角英数記号12〜50文字), 生年月日, 性別, 職業, メールマガジン送付について and the terms checkbox|
| F-024 | Account | Registration completion | Restricted | — | No | Cannot complete because email verification is disabled (LIM-02, LIM-03) |
| F-025 | Account | Login form display | Confirmed Available | FEAT-006, VID-001 | Yes | Login form confirmed at /mypage/login with email, password, remember checkbox and both support links|
| F-026 | Account | Login (successful) | Restricted | — | No | No usable member account can exist in this environment (LIM-03) |
| F-027 | Account | Login (invalid credentials error handling) | Unable to Verify | — | No | A login attempt was made but the resulting screen was not captured. Outcome is unknown. See section 5 |
| F-028 | Account | Logout | Not Yet Observed | — | No | Not reachable without a logged-in session |
| F-029 | Account | Password reset | Visible Only | FEAT-006 | No | Link ログイン情報をお忘れですか？ visible. Not clicked. Would also be blocked by LIM-02 |
| F-030 | Account | Favourites (お気に入り) | Visible Only | ENV-001, FEAT-002 | No | Header link and product page button お気に入りに追加 both visible. Not used. Likely requires login |
| F-031 | Checkout | Guest purchase entry point | Visible Only | FEAT-006 | No | Panel 会員登録をせずに購入手続きをされたい方は、下記よりお進みください with button ゲスト購入 is present. Button was not clicked |
| F-032 | Checkout | レジに進む (proceed to checkout) button | Visible Only | FEAT-004 | No | Visible on the cart page. Not clicked |
| F-033 | Checkout | Customer information form | Not Yet Observed | — | No | Step 2 of the progress indicator. Not reached |
| F-034 | Checkout | Checkout form validation | Not Yet Observed | — | No | Not reached |
| F-035 | Checkout | Delivery method selection | Not Yet Observed | — | No | Not reached |
| F-036 | Checkout | Payment method selection | Not Yet Observed | — | No | Not reached. Must never be tested with real payment details |
| F-037 | Checkout | Order confirmation and completion | Not Yet Observed | — | No | Not reached |
| F-038 | System | 404 error page | Confirmed Available | FEAT-007 | Yes | Page displays warning icon, heading ページがみつかりません。, message URLに間違いがないかご確認ください。 and button トップページへ. The action that produced this page was not recorded. See section 5 |
| F-039 | System | Email delivery | Not Available in Test Environment | — | No | Disabled by the demo operator (LIM-02) |
| F-040 | System | Admin screen | Not Available in Test Environment | — | No | Blocked in the public demo (LIM-04) |
| F-041 | UI | Responsive behaviour | Confirmed Available | MOB-002 | Yes | Mobile layout confirmed in Google Chrome for iOS. Header icons render correctly and a hamburger menu control appears that is not present on desktop|
| F-042 | UI | Home page carousel behaviour | Visible Only | ENV-001 | No | Three slide indicator dots are visible. Automatic rotation and manual navigation were not verified |
| F-043 | Product | Listing per-page and sort order controls | Confirmed Available | VID-001 | Yes | Controls observed with values 20件 and 価格が低い順 |
| F-044 | Cart | Add to cart directly from the product listing page | Confirmed Available | VID-001 | Yes | Product added without opening the detail page |
| F-045 | Cart | Multiple different products held in the cart | Confirmed Available | VID-001 | Yes | ￥1,100 + ￥19,800 = ￥20,900. Total arithmetic correct |
| F-046 | Cart | Selected variation values displayed on the cart line | Confirmed Available | VID-001 | Yes | Displayed as フレーバー：チョコ and サイズ：64cm × 64cm |
| F-047 | Registration | Empty-form submission validation | Confirmed Available | VID-001 | Yes | All required fields highlighted with 入力されていません。 Form not submitted |
| F-048 | Registration | Postal code lookup link | Confirmed Available | VID-001 | Yes | Opens post.japanpost.jp in a new browser tab |
| F-049 | Registration | Katakana name field format validation | Unable to Verify | VID-001 | No | Romaji entered but the form was not resubmitted. Outcome unknown. See OPEN-03 |

### Summary count

| Status | Count |
|---|---|
| Confirmed Available | 25 |
| Visible Only | 9 |
| Restricted | 2 |
| Not Available in Test Environment | 2 |
| Not Yet Observed | 9 |
| Unable to Verify | 2 |
| **Total features assessed** | **49** |

---

## 5. Open Items Requiring Clarification

These two items were observed but cannot yet be classified. They are recorded
here as open questions, not as defects.

### OPEN-01 — Login attempt outcome not captured

A login attempt was made on the login page. The screen that appeared afterwards
was not captured, so it is not known whether an error message was displayed,
whether the page reloaded, or whether the attempt failed silently.

**Required action:** repeat the attempt using a fictional email address and a
throwaway password, and capture the resulting screen.

### OPEN-02 — 404 page appeared, trigger unknown

A "page not found" screen was captured shortly after the login page. The URL and
the action that produced it were not recorded.

This could be normal behaviour (for example a mistyped URL) or it could be
unexpected behaviour (for example a valid link leading to a missing page). Until
the trigger is known and the result can be repeated, this is **not** a defect.

**Required action:** identify the exact URL or click that produced the 404, then
attempt to repeat it at least twice. Record the full URL in the address bar.

---

## 6. Scope Recommendation for Phase 2

Based on confirmed observations only, the following modules are candidates for
the test scope:

**Recommended in scope**
- Home page rendering and header navigation
- Product detail page content (image, price, description, related category)
- Add to cart
- Cart page display, quantity update, and total recalculation
- Cart persistence during a browsing session
- 404 error page presentation

**Recommended out of scope for now (require further observation first)**
- Search and search results
- Category navigation result pages
- Product listing page
- Cart item removal
- Guest checkout flow
- Responsive behaviour

**Permanently out of scope in this environment**
- Member registration completion, login, logout, password reset
- Email delivery
- Admin screen
- Real payment processing

---

## 7. Next Observation Session — Required Actions

To move the "Visible Only" and "Not Yet Observed" items into scope, complete the
following in a second session of approximately 45 minutes:

1. Scroll to the footer and record all link names.
2. Click each of the four category links and capture the result page.
3. Open the product listing page and record how products are displayed.
4. Run a search using a keyword taken from a visible product name. Capture the result.
5. Run a search using a nonsense keyword such as `zzzzz`. Capture the empty state.
6. Change the quantity on a product detail page before adding to cart.
7. Remove an item from the cart using the × control.
8. Click ゲスト購入 and record how far the guest checkout flow can proceed.
9. On the first checkout form, submit with all fields empty and capture the validation messages.
10. Resolve OPEN-01 and OPEN-02 above.
11. Resize the browser window to a narrow width and capture the home page.
12. Record the exact Google Chrome version and browser viewport size.

---

## 8. Document Control

| Version | Date | Change |
|---|---|---|
| 0.1 | 2026-09-01 | Initial analysis from first observation session |
| 0.2 | 2026-09-02 | Added second observation session findings. Corrected browser from Safari to Google Chrome. Added ENV-EC-002 mobile environment. Feature count 42 to 49 |
