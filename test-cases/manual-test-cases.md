# Manual Test Cases (テストケース)

**Project:** EC-CUBE Manual QA Testing & Bug Reporting
**Phase:** 5 of 15
**Environment ID:** ENV-EC-001
**Total test cases:** 40
**Execution status:** All Not Executed

---

## Before You Execute

1. Run TC-001, TC-016, and TC-022 first as a smoke check. If any fails, stop and
   investigate the environment before continuing.
2. Record the actual product name and price used in each case. Store data resets
   roughly hourly and products may change.
3. Capture a screenshot at the moment of observation, named `TC-0XX-short-description.png`.
4. If a data reset interrupts a case, mark it **Blocked** and restart it from step 1.
5. Before recording anything as Failed, repeat it twice and check it against the
   known limitations list.

---

## Module: Navigation

### TC-001
| Field | Value |
|---|---|
| **Test Case ID** | TC-001 |
| **Requirement ID** | REQ-001 |
| **Scenario ID** | SCN-001 |
| **Module** | Navigation |
| **Title** | Home page loads completely with header, title, category links, and hero area |
| **Test Type** | Smoke |
| **Priority** | High |
| **Preconditions** | Chrome open, no page loaded |
| **Test Data** | URL: https://ec-cube.sakura.ne.jp/4-2-demo/ |
| **Test Steps** | 1. Navigate to the demo URL<br>2. Wait for the page to finish loading<br>3. Observe the header region<br>4. Observe the page title area<br>5. Observe the category link row<br>6. Observe the hero carousel area |
| **Expected Result** | The page loads without error. The header, the title "EC-CUBE4.2 デモサイト", four category links, and a hero image area are all visible. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | Run this first in every session as an environment check |

### TC-002
| Field | Value |
|---|---|
| **Test Case ID** | TC-002 |
| **Requirement ID** | REQ-002 |
| **Scenario ID** | SCN-002 |
| **Module** | Navigation |
| **Title** | Header displays the category dropdown, keyword field, and all three account links |
| **Test Type** | Functional |
| **Priority** | High |
| **Preconditions** | Home page loaded |
| **Test Data** | None |
| **Test Steps** | 1. Look at the top-left of the header<br>2. Confirm a dropdown labelled 全ての商品 is present<br>3. Confirm a text field with placeholder キーワードを入力 is present<br>4. Look at the top-right of the header<br>5. Confirm the links 新規会員登録, お気に入り, and ログイン are present |
| **Expected Result** | All five controls are visible and correctly labelled. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | — |

### TC-003
| Field | Value |
|---|---|
| **Test Case ID** | TC-003 |
| **Requirement ID** | REQ-002 |
| **Scenario ID** | SCN-002 |
| **Module** | Navigation |
| **Title** | Four category links appear below the site title |
| **Test Type** | UI |
| **Priority** | Medium |
| **Preconditions** | Home page loaded |
| **Test Data** | None |
| **Test Steps** | 1. Look below the site title<br>2. Read each link name from left to right |
| **Expected Result** | Four links are shown: 新規カテゴリ, 新入荷, ジェラート, アイスサンド. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | Link names may change if demo data is reconfigured. Record what is actually shown |

### TC-004
| Field | Value |
|---|---|
| **Test Case ID** | TC-004 |
| **Requirement ID** | REQ-003 |
| **Scenario ID** | SCN-003 |
| **Module** | Navigation |
| **Title** | Cart indicator shows zero items and zero yen when the cart is empty |
| **Test Type** | Functional |
| **Priority** | High |
| **Preconditions** | No items in the cart. Clear the cart or use a fresh browser session |
| **Test Data** | None |
| **Test Steps** | 1. Open the home page with an empty cart<br>2. Look at the cart control in the header |
| **Expected Result** | The cart badge shows 0 and the total shows ￥0. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | Use a new incognito window if the cart cannot be emptied |

### TC-005
| Field | Value |
|---|---|
| **Test Case ID** | TC-005 |
| **Requirement ID** | REQ-004 |
| **Scenario ID** | SCN-004 |
| **Module** | Navigation |
| **Title** | Selecting the ジェラート category opens a filtered product listing |
| **Test Type** | Functional |
| **Priority** | High |
| **Preconditions** | Home page loaded |
| **Test Data** | Category: ジェラート |
| **Test Steps** | 1. Click the category link ジェラート<br>2. Wait for the page to load<br>3. Read the breadcrumb area<br>4. Read the result count text |
| **Expected Result** | A product listing page opens. The breadcrumb shows 全て | ジェラート and a result count in the form 〇件の商品が見つかりました is displayed. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | Observed URL pattern: /products/list?category_id=1 |

### TC-006
| Field | Value |
|---|---|
| **Test Case ID** | TC-006 |
| **Requirement ID** | REQ-004 |
| **Scenario ID** | SCN-004 |
| **Module** | Navigation |
| **Title** | Each remaining category link opens its own listing without error |
| **Test Type** | Functional |
| **Priority** | Medium |
| **Preconditions** | Home page loaded |
| **Test Data** | Categories: 新規カテゴリ, 新入荷, アイスサンド |
| **Test Steps** | 1. Click 新規カテゴリ and record the result count<br>2. Return to the home page<br>3. Click 新入荷 and record the result count<br>4. Return to the home page<br>5. Click アイスサンド and record the result count |
| **Expected Result** | Each link opens a listing page without an error. Each page displays a result count. Counts may differ between categories. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | A count of zero is an acceptable result if the category is genuinely empty. Record the number seen |

### TC-007
| Field | Value |
|---|---|
| **Test Case ID** | TC-007 |
| **Requirement ID** | REQ-001 |
| **Scenario ID** | SCN-001 |
| **Module** | Navigation |
| **Title** | Hero carousel displays slide position indicators |
| **Test Type** | UI |
| **Priority** | Low |
| **Preconditions** | Home page loaded |
| **Test Data** | None |
| **Test Steps** | 1. Scroll to the hero image area<br>2. Look immediately below the image<br>3. Count the indicator dots<br>4. Note which dot appears active |
| **Expected Result** | Three indicator dots are shown and exactly one is highlighted as active. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | This case covers indicator display only. Rotation behaviour is out of scope |

---

## Module: Product

### TC-008
| Field | Value |
|---|---|
| **Test Case ID** | TC-008 |
| **Requirement ID** | REQ-005 |
| **Scenario ID** | SCN-005 |
| **Module** | Product |
| **Title** | Product listing shows a result count matching the number of tiles displayed |
| **Test Type** | Functional |
| **Priority** | High |
| **Preconditions** | A category listing page is open |
| **Test Data** | Category: ジェラート |
| **Test Steps** | 1. Open the ジェラート listing<br>2. Read the number in the 〇件の商品が見つかりました text<br>3. Count the product tiles shown on the page |
| **Expected Result** | The stated count equals the number of product tiles displayed. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | If the count exceeds the per-page setting, count tiles on the first page and check for pagination |

### TC-009
| Field | Value |
|---|---|
| **Test Case ID** | TC-009 |
| **Requirement ID** | REQ-006 |
| **Scenario ID** | SCN-005 |
| **Module** | Product |
| **Title** | Listing page displays per-page and sort order controls |
| **Test Type** | UI |
| **Priority** | Medium |
| **Preconditions** | A category listing page is open |
| **Test Data** | None |
| **Test Steps** | 1. Look at the top-right of the listing area<br>2. Confirm a per-page dropdown is present and read its current value<br>3. Confirm a sort order dropdown is present and read its current value |
| **Expected Result** | Two dropdowns are visible. Observed defaults were 20件 and 価格が低い順. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | Presence only. Changing the values is a separate case |

### TC-010
| Field | Value |
|---|---|
| **Test Case ID** | TC-010 |
| **Requirement ID** | REQ-006 |
| **Scenario ID** | SCN-005 |
| **Module** | Product |
| **Title** | Changing the sort order reorders the displayed products |
| **Test Type** | Functional |
| **Priority** | Medium |
| **Preconditions** | A listing page showing at least two products is open |
| **Test Data** | Sort values available in the dropdown |
| **Test Steps** | 1. Record the order of product names currently displayed<br>2. Open the sort order dropdown<br>3. Select a different sort value<br>4. Wait for the listing to update<br>5. Record the new order of product names |
| **Expected Result** | The product order changes in a way consistent with the selected sort value. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | Requires a category with two or more products. If none exists, mark Blocked |

### TC-011
| Field | Value |
|---|---|
| **Test Case ID** | TC-011 |
| **Requirement ID** | REQ-007 |
| **Scenario ID** | SCN-006 |
| **Module** | Product |
| **Title** | Product detail page displays the product name as a heading |
| **Test Type** | Functional |
| **Priority** | High |
| **Preconditions** | A product exists in the store |
| **Test Data** | Any available product |
| **Test Steps** | 1. Open a product from the listing or home page<br>2. Observe the heading area to the right of the main image |
| **Expected Result** | The product name is displayed as the page heading and matches the name shown on the listing. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | Record the exact product name used |

### TC-012
| Field | Value |
|---|---|
| **Test Case ID** | TC-012 |
| **Requirement ID** | REQ-008 |
| **Scenario ID** | SCN-006 |
| **Module** | Product |
| **Title** | Product detail page displays a main image and at least one thumbnail |
| **Test Type** | UI |
| **Priority** | Medium |
| **Preconditions** | Product detail page open |
| **Test Data** | Any available product |
| **Test Steps** | 1. Observe the left side of the page<br>2. Confirm a main product image is displayed and fully rendered<br>3. Look below the main image for thumbnail images |
| **Expected Result** | A main image renders without a broken image placeholder. At least one thumbnail is shown below it. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | Thumbnail count may vary by product |

### TC-013
| Field | Value |
|---|---|
| **Test Case ID** | TC-013 |
| **Requirement ID** | REQ-009 |
| **Scenario ID** | SCN-006 |
| **Module** | Product |
| **Title** | Product price is displayed with a tax-inclusive label |
| **Test Type** | Functional |
| **Priority** | High |
| **Preconditions** | Product detail page open |
| **Test Data** | Any single-price product |
| **Test Steps** | 1. Locate the price on the product detail page<br>2. Confirm the yen symbol and amount are shown<br>3. Look for a tax indicator next to the price |
| **Expected Result** | The price is shown in yen with a 税込 label. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | Observed example: ￥1,100 税込 |

### TC-014
| Field | Value |
|---|---|
| **Test Case ID** | TC-014 |
| **Requirement ID** | REQ-010 |
| **Scenario ID** | SCN-006 |
| **Module** | Product |
| **Title** | Product description text is displayed on the detail page |
| **Test Type** | Functional |
| **Priority** | Medium |
| **Preconditions** | Product detail page open |
| **Test Data** | Any available product |
| **Test Steps** | 1. Scroll to the area below the action buttons<br>2. Read the description text |
| **Expected Result** | Description text is present, readable, and not truncated mid-word or showing placeholder text. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | Some demo products may legitimately have short descriptions |

### TC-015
| Field | Value |
|---|---|
| **Test Case ID** | TC-015 |
| **Requirement ID** | REQ-011 |
| **Scenario ID** | SCN-006 |
| **Module** | Product |
| **Title** | Related category is displayed as a link on the product detail page |
| **Test Type** | Functional |
| **Priority** | Low |
| **Preconditions** | Product detail page open |
| **Test Data** | Any product assigned to a category |
| **Test Steps** | 1. Locate the 関連カテゴリ section<br>2. Confirm a category name is shown<br>3. Confirm it is styled as a clickable link |
| **Expected Result** | The related category is displayed as a link. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | Clicking the link is covered by TC-016 |

### TC-016
| Field | Value |
|---|---|
| **Test Case ID** | TC-016 |
| **Requirement ID** | REQ-011 |
| **Scenario ID** | SCN-006 |
| **Module** | Product |
| **Title** | Related category link opens the matching category listing |
| **Test Type** | Functional |
| **Priority** | Medium |
| **Preconditions** | Product detail page open with a related category shown |
| **Test Data** | The category name displayed on the product |
| **Test Steps** | 1. Note the related category name<br>2. Click the related category link<br>3. Read the breadcrumb on the resulting page<br>4. Confirm the product from step 1 appears in the results |
| **Expected Result** | A listing page for that category opens and includes the originating product. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | — |

### TC-017
| Field | Value |
|---|---|
| **Test Case ID** | TC-017 |
| **Requirement ID** | REQ-012 |
| **Scenario ID** | SCN-007 |
| **Module** | Product |
| **Title** | A product with options displays selector controls and a price range |
| **Test Type** | Functional |
| **Priority** | High |
| **Preconditions** | A product with variations exists |
| **Test Data** | Product: 彩のジェラートCUBE or any variation product available |
| **Test Steps** | 1. Open a product that has options<br>2. Confirm two selector dropdowns are displayed<br>3. Read the price area |
| **Expected Result** | Two option selectors are shown and the price is displayed as a range rather than a single value. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | Observed example: ￥19,800 〜 ￥121,000 |

---

## Module: Cart

### TC-018
| Field | Value |
|---|---|
| **Test Case ID** | TC-018 |
| **Requirement ID** | REQ-013 |
| **Scenario ID** | SCN-008 |
| **Module** | Cart |
| **Title** | Adding a product from the detail page shows a confirmation message |
| **Test Type** | Smoke |
| **Priority** | High |
| **Preconditions** | Product detail page open for a product without required options |
| **Test Data** | Any single-price product |
| **Test Steps** | 1. Note the product name and price<br>2. Click カートに入れる<br>3. Observe the screen immediately after the click |
| **Expected Result** | A confirmation message reading カートに追加しました。 appears with options to continue shopping or go to the cart. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | — |

### TC-019
| Field | Value |
|---|---|
| **Test Case ID** | TC-019 |
| **Requirement ID** | REQ-014 |
| **Scenario ID** | SCN-003 |
| **Module** | Cart |
| **Title** | Header cart count and total update immediately after adding a product |
| **Test Type** | Functional |
| **Priority** | High |
| **Preconditions** | Cart is empty. Product detail page open |
| **Test Data** | A product with a known price |
| **Test Steps** | 1. Record the header cart count and total before adding<br>2. Record the product price<br>3. Click カートに入れる<br>4. Dismiss the confirmation<br>5. Read the header cart count and total again |
| **Expected Result** | The count increases by one and the total increases by exactly the product price. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | Write down both numbers before and after. Do not rely on memory |

### TC-020
| Field | Value |
|---|---|
| **Test Case ID** | TC-020 |
| **Requirement ID** | REQ-013 |
| **Scenario ID** | SCN-009 |
| **Module** | Cart |
| **Title** | A product can be added to the cart directly from the listing page |
| **Test Type** | Functional |
| **Priority** | Medium |
| **Preconditions** | A listing page showing an add-to-cart control is open |
| **Test Data** | Any product visible on the listing |
| **Test Steps** | 1. Record the header cart count<br>2. On the listing page, set any required options<br>3. Click the カートに入れる control on the product tile<br>4. Observe the result<br>5. Read the header cart count |
| **Expected Result** | The product is added and the header cart count increases by one, without needing to open the detail page. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | — |

### TC-021
| Field | Value |
|---|---|
| **Test Case ID** | TC-021 |
| **Requirement ID** | REQ-012 |
| **Scenario ID** | SCN-007 |
| **Module** | Cart |
| **Title** | A variation product cannot be added without selecting its options |
| **Test Type** | Negative |
| **Priority** | High |
| **Preconditions** | A product with required option selectors is open |
| **Test Data** | Product with two option dropdowns, both left unselected |
| **Test Steps** | 1. Open a product with option selectors<br>2. Leave both selectors at their default 選択してください state<br>3. Click カートに入れる<br>4. Observe the result |
| **Expected Result** | The product is not added. A message indicates that options must be selected. The header cart count does not change. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | This expectation is based on standard behaviour, not on a confirmed specification. If the product is added without options, verify twice before treating it as a defect |

### TC-022
| Field | Value |
|---|---|
| **Test Case ID** | TC-022 |
| **Requirement ID** | REQ-015 |
| **Scenario ID** | SCN-010 |
| **Module** | Cart |
| **Title** | Cart page lists each item with name, unit price, quantity, and subtotal |
| **Test Type** | Smoke |
| **Priority** | High |
| **Preconditions** | At least one item in the cart |
| **Test Data** | Any added product |
| **Test Steps** | 1. Open the cart page<br>2. Read the table column headers<br>3. For the item row, read the product name, unit price, quantity, and subtotal |
| **Expected Result** | The table shows columns 削除, 商品内容, 数量, 小計. The item row displays the correct name, unit price, quantity, and subtotal. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | — |

### TC-023
| Field | Value |
|---|---|
| **Test Case ID** | TC-023 |
| **Requirement ID** | REQ-016 |
| **Scenario ID** | SCN-010 |
| **Module** | Cart |
| **Title** | Cart page displays the five-step checkout progress indicator |
| **Test Type** | UI |
| **Priority** | Medium |
| **Preconditions** | At least one item in the cart |
| **Test Data** | None |
| **Test Steps** | 1. Open the cart page<br>2. Observe the numbered indicator above the item table<br>3. Read each step label<br>4. Note which step appears active |
| **Expected Result** | Five steps are shown: カートの商品, お客様情報, ご注文手続き, ご注文内容確認, 完了. Step 1 is highlighted as the current step. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | — |

### TC-024
| Field | Value |
|---|---|
| **Test Case ID** | TC-024 |
| **Requirement ID** | REQ-017 |
| **Scenario ID** | SCN-011 |
| **Module** | Cart |
| **Title** | Plus control increases the item quantity by one |
| **Test Type** | Functional |
| **Priority** | High |
| **Preconditions** | Cart contains one item at quantity 1 |
| **Test Data** | Any added product |
| **Test Steps** | 1. Record the current quantity<br>2. Click the plus control on the item row<br>3. Wait for the page to update<br>4. Read the quantity again |
| **Expected Result** | The quantity increases from 1 to 2. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | — |

### TC-025
| Field | Value |
|---|---|
| **Test Case ID** | TC-025 |
| **Requirement ID** | REQ-017 |
| **Scenario ID** | SCN-011 |
| **Module** | Cart |
| **Title** | Minus control decreases the item quantity by one |
| **Test Type** | Functional |
| **Priority** | High |
| **Preconditions** | Cart contains one item at quantity 2 |
| **Test Data** | Any added product |
| **Test Steps** | 1. Record the current quantity<br>2. Click the minus control on the item row<br>3. Wait for the page to update<br>4. Read the quantity again |
| **Expected Result** | The quantity decreases from 2 to 1. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | — |

### TC-026
| Field | Value |
|---|---|
| **Test Case ID** | TC-026 |
| **Requirement ID** | REQ-018 |
| **Scenario ID** | SCN-012 |
| **Module** | Cart |
| **Title** | Item subtotal equals unit price multiplied by quantity after a quantity change |
| **Test Type** | Functional |
| **Priority** | High |
| **Preconditions** | Cart contains one item |
| **Test Data** | A product with a known unit price |
| **Test Steps** | 1. Record the unit price and the current subtotal<br>2. Increase the quantity to 2<br>3. Read the new subtotal<br>4. Calculate unit price × 2 by hand<br>5. Compare the two figures |
| **Expected Result** | The displayed subtotal equals the manually calculated value. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | Do the arithmetic yourself. Do not assume the displayed figure is right |

### TC-027
| Field | Value |
|---|---|
| **Test Case ID** | TC-027 |
| **Requirement ID** | REQ-018 |
| **Scenario ID** | SCN-012 |
| **Module** | Cart |
| **Title** | Cart total and the summary line agree with each other after a quantity change |
| **Test Type** | Functional |
| **Priority** | High |
| **Preconditions** | Cart contains at least one item |
| **Test Data** | Any added product |
| **Test Steps** | 1. Change the quantity of an item<br>2. Read the 合計 figure at the bottom right<br>3. Read the summary sentence above the table beginning 商品の合計金額は<br>4. Compare the two figures |
| **Expected Result** | Both figures show the same amount. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | The same total is displayed in two places, so a mismatch would be a genuine defect |

### TC-028
| Field | Value |
|---|---|
| **Test Case ID** | TC-028 |
| **Requirement ID** | REQ-019 |
| **Scenario ID** | SCN-013 |
| **Module** | Cart |
| **Title** | Two different products coexist in the cart as separate lines |
| **Test Type** | Functional |
| **Priority** | High |
| **Preconditions** | Cart contains one product. A second, different product is available |
| **Test Data** | Two products with known prices |
| **Test Steps** | 1. Note the product already in the cart<br>2. Navigate to a different product<br>3. Add it to the cart<br>4. Open the cart page<br>5. Count the item rows |
| **Expected Result** | The cart shows two separate rows, one for each product, each with its own price and quantity. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | — |

### TC-029
| Field | Value |
|---|---|
| **Test Case ID** | TC-029 |
| **Requirement ID** | REQ-019 |
| **Scenario ID** | SCN-013 |
| **Module** | Cart |
| **Title** | Cart total equals the sum of all line subtotals with multiple products |
| **Test Type** | Functional |
| **Priority** | High |
| **Preconditions** | Cart contains two different products |
| **Test Data** | Two products with known prices |
| **Test Steps** | 1. Open the cart page<br>2. Record each line subtotal<br>3. Add the subtotals together by hand<br>4. Read the 合計 figure<br>5. Compare |
| **Expected Result** | The displayed total equals the manually calculated sum of the line subtotals. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | Observed example during analysis: ￥1,100 + ￥19,800 = ￥20,900 |

### TC-030
| Field | Value |
|---|---|
| **Test Case ID** | TC-030 |
| **Requirement ID** | REQ-020 |
| **Scenario ID** | SCN-014 |
| **Module** | Cart |
| **Title** | Selected option values appear against the cart line for a variation product |
| **Test Type** | Functional |
| **Priority** | Medium |
| **Preconditions** | A variation product has been added with specific options selected |
| **Test Data** | Record the option values chosen at the time of adding |
| **Test Steps** | 1. Open a product with options<br>2. Select a value in each option selector and write both down<br>3. Add the product to the cart<br>4. Open the cart page<br>5. Read the option text shown under the product name |
| **Expected Result** | The cart line displays the same option values that were selected. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | Observed format during analysis: フレーバー：チョコ / サイズ：64cm × 64cm |

### TC-031
| Field | Value |
|---|---|
| **Test Case ID** | TC-031 |
| **Requirement ID** | REQ-020 |
| **Scenario ID** | SCN-014 |
| **Module** | Cart |
| **Title** | Variation product line price matches the price for the selected option combination |
| **Test Type** | Functional |
| **Priority** | High |
| **Preconditions** | A variation product with a price range is available |
| **Test Data** | Product showing a price range |
| **Test Steps** | 1. Open a product showing a price range<br>2. Select a specific option combination<br>3. Record the price displayed after selection<br>4. Add it to the cart<br>5. Open the cart and read the unit price on that line |
| **Expected Result** | The unit price in the cart matches the price shown after the options were selected, and falls within the advertised range. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | Price mismatches between selection and cart are high severity if found |

### TC-032
| Field | Value |
|---|---|
| **Test Case ID** | TC-032 |
| **Requirement ID** | REQ-021 |
| **Scenario ID** | SCN-015 |
| **Module** | Cart |
| **Title** | Cart contents survive navigation to another page and back |
| **Test Type** | Functional |
| **Priority** | High |
| **Preconditions** | Cart contains at least one item |
| **Test Data** | Any added product |
| **Test Steps** | 1. Record the cart count and total from the header<br>2. Navigate to the home page<br>3. Navigate to a category listing<br>4. Navigate to the login page<br>5. Read the header cart count and total at each step<br>6. Return to the cart page and confirm the contents |
| **Expected Result** | The cart count and total remain unchanged on every page, and the cart page still lists the same items. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | If a data reset occurs mid-test, mark Blocked and restart |

### TC-033
| Field | Value |
|---|---|
| **Test Case ID** | TC-033 |
| **Requirement ID** | REQ-021 |
| **Scenario ID** | SCN-015 |
| **Module** | Cart |
| **Title** | Cart contents survive a browser page reload |
| **Test Type** | Functional |
| **Priority** | Medium |
| **Preconditions** | Cart contains at least one item |
| **Test Data** | Any added product |
| **Test Steps** | 1. Open the cart page and record its contents<br>2. Press the browser reload button<br>3. Wait for the page to reload<br>4. Compare the contents with step 1 |
| **Expected Result** | The same items, quantities, and totals are shown after reload. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | Not yet observed. This is a reasonable expectation, not a confirmed behaviour |

---

## Module: Registration

### TC-034
| Field | Value |
|---|---|
| **Test Case ID** | TC-034 |
| **Requirement ID** | REQ-022 |
| **Scenario ID** | SCN-016 |
| **Module** | Registration |
| **Title** | Registration form displays all name, address, and contact fields |
| **Test Type** | UI |
| **Priority** | Medium |
| **Preconditions** | Registration page open at /entry |
| **Test Data** | None |
| **Test Steps** | 1. Open 新規会員登録 from the header<br>2. Read each field label from top to bottom<br>3. Note which labels carry a 必須 marker |
| **Expected Result** | The form shows お名前, お名前(カナ), 会社名, 住所 with postal code and prefecture controls, 電話番号, メールアドレス, パスワード, 生年月日, 性別, 職業, and メールマガジン送付について. Required fields carry a 必須 marker. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | Registration cannot be completed in this environment because email is disabled. This case covers display only |

### TC-035
| Field | Value |
|---|---|
| **Test Case ID** | TC-035 |
| **Requirement ID** | REQ-023 |
| **Scenario ID** | SCN-017 |
| **Module** | Registration |
| **Title** | Submitting the registration form with every field empty is rejected |
| **Test Type** | Negative |
| **Priority** | High |
| **Preconditions** | Registration page open with no data entered |
| **Test Data** | All fields left empty |
| **Test Steps** | 1. Open the registration page<br>2. Do not enter anything in any field<br>3. Scroll to the bottom<br>4. Click 同意する<br>5. Scroll through the whole form and read every message shown |
| **Expected Result** | The form is not submitted. Each required field is highlighted and displays 入力されていません。 The user remains on the registration page. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | This behaviour was observed during analysis but has not been formally executed against this test case |

### TC-036
| Field | Value |
|---|---|
| **Test Case ID** | TC-036 |
| **Requirement ID** | REQ-023 |
| **Scenario ID** | SCN-017 |
| **Module** | Registration |
| **Title** | Optional fields are not flagged when the form is submitted empty |
| **Test Type** | Negative |
| **Priority** | Medium |
| **Preconditions** | Registration page open, form submitted empty per TC-035 |
| **Test Data** | All fields left empty |
| **Test Steps** | 1. Perform the steps of TC-035<br>2. Locate the 会社名 field<br>3. Locate the 生年月日, 性別, and 職業 fields<br>4. Check whether any of them shows an error message |
| **Expected Result** | Fields without a 必須 marker show no validation error. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | An error on an optional field would be a genuine defect |

### TC-037
| Field | Value |
|---|---|
| **Test Case ID** | TC-037 |
| **Requirement ID** | REQ-024 |
| **Scenario ID** | SCN-017 |
| **Module** | Registration |
| **Title** | Katakana name fields reject romaji input |
| **Test Type** | Negative |
| **Priority** | High |
| **Preconditions** | Registration page open |
| **Test Data** | お名前(カナ) セイ: `ramu`, メイ: `amsu`. Other required fields completed with approved fictional data from the test data guide |
| **Test Steps** | 1. Enter テスト and 太郎 in the お名前 fields<br>2. Enter `ramu` and `amsu` in the お名前(カナ) fields<br>3. Complete all other required fields with approved fictional data<br>4. Tick the terms checkbox<br>5. Click 同意する<br>6. Look directly under the お名前(カナ) fields |
| **Expected Result** | A validation message appears indicating the katakana fields require katakana characters. The form is not submitted. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | **This is the highest-value case in the suite.** The expectation is based on the field label, not a confirmed specification. If romaji is accepted, repeat twice before raising a defect. See OPEN-03 in the scenarios document |

### TC-038
| Field | Value |
|---|---|
| **Test Case ID** | TC-038 |
| **Requirement ID** | REQ-025 |
| **Scenario ID** | SCN-018 |
| **Module** | Registration |
| **Title** | Postal code lookup link opens the external Japan Post service |
| **Test Type** | Functional |
| **Priority** | Low |
| **Preconditions** | Registration page open |
| **Test Data** | None |
| **Test Steps** | 1. Locate the 郵便番号検索 link beside the postal code field<br>2. Click it<br>3. Observe where it opens<br>4. Read the URL in the address bar |
| **Expected Result** | An external postal code search page opens in a new browser tab, and the registration page remains open in the original tab. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | Observed destination during analysis: post.japanpost.jp |

---

## Module: Account Access

### TC-039
| Field | Value |
|---|---|
| **Test Case ID** | TC-039 |
| **Requirement ID** | REQ-026 |
| **Scenario ID** | SCN-019 |
| **Module** | Account |
| **Title** | Login page displays the credential fields and both support links |
| **Test Type** | UI |
| **Priority** | Medium |
| **Preconditions** | Login page open at /mypage/login |
| **Test Data** | None |
| **Test Steps** | 1. Click ログイン in the header<br>2. Confirm an email field and a password field are shown<br>3. Confirm the checkbox 次回から自動的にログインする is present<br>4. Confirm the links ログイン情報をお忘れですか？ and 新規会員登録 are present |
| **Expected Result** | All four elements render on the login page. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | Successful login is Not Applicable in this environment because no member account can be created |

---

## Module: System

### TC-040
| Field | Value |
|---|---|
| **Test Case ID** | TC-040 |
| **Requirement ID** | REQ-027 |
| **Scenario ID** | SCN-020 |
| **Module** | System |
| **Title** | An invalid URL returns a page-not-found screen with a route back to the top page |
| **Test Type** | Negative |
| **Priority** | Medium |
| **Preconditions** | Browser open |
| **Test Data** | URL: https://ec-cube.sakura.ne.jp/4-2-demo/thispagedoesnotexist |
| **Test Steps** | 1. Type the invalid URL into the address bar<br>2. Press Enter<br>3. Read the message displayed<br>4. Confirm a button back to the top page is present<br>5. Click that button |
| **Expected Result** | A page displays ページがみつかりません。 with the guidance URLに間違いがないかご確認ください。 and a トップページへ button that returns to the home page. |
| **Actual Result** | Not Executed |
| **Status** | Not Executed |
| **Severity** | N/A |
| **Evidence** | Not Available |
| **Execution Date** | Not Executed |
| **Tester** | — |
| **Notes** | Record the exact URL used, so the case is repeatable |

---

## Coverage Summary

| Module | Test Cases | IDs |
|---|---|---|
| Navigation | 7 | TC-001 to TC-007 |
| Product | 10 | TC-008 to TC-017 |
| Cart | 16 | TC-018 to TC-033 |
| Registration | 5 | TC-034 to TC-038 |
| Account | 1 | TC-039 |
| System | 1 | TC-040 |
| **Total** | **40** | |

| Test Type | Count |
|---|---|
| Functional | 24 |
| UI | 7 |
| Negative | 6 |
| Smoke | 3 |

| Priority | Count |
|---|---|
| High | 20 |
| Medium | 14 |
| Low | 3 |
| — | 3 (smoke, counted under High) |

| Status | Count |
|---|---|
| Not Executed | 40 |
| Passed | 0 |
| Failed | 0 |
| Blocked | 0 |
| Not Applicable | 0 |

---

## Estimated Execution Time

Roughly 10 minutes per case including evidence capture, so **6 to 7 hours total**.
Work in blocks under one hour because the demo data resets approximately hourly.

Suggested order:
1. Smoke: TC-001, TC-018, TC-022
2. Navigation: TC-002 to TC-007
3. Product: TC-008 to TC-017
4. Cart: TC-018 to TC-033
5. Registration and Account: TC-034 to TC-039
6. System: TC-040
