# EC-CUBE Manual QA Testing Portfolio

マニュアルテスト・ポートフォリオプロジェクト

---

## 日本語版

### プロジェクト概要

EC-CUBE 4.2.3 の公開デモサイトに対して、マニュアルテストの設計・分析を実施したポートフォリオプロジェクトです。49個の機能を観察・分析し、27個の要件を定義、40個のテストケースを設計しました。テスト実行ではなく、テスト設計と要件管理のスキルを示すプロジェクトです。

### テスト対象

**アプリケーション:** EC-CUBE 4.2.3（オープンソース型 EC システム）  
**テスト環境:** https://ec-cube.sakura.ne.jp/4-2-demo/  
**テスト言語:** 日本語

### テスト目的

日本の EC サイトに対するマニュアルテストの実施能力を示す。以下のスキルを実証する：

* 要件分析と定義
* テスト計画書の作成
* テストケース設計
* テストシナリオの構築
* 要件-シナリオ-テストケース間のトレーサビリティ管理
* テスト証跡（スクリーンショット）の管理

### テスト範囲

**評価した機能数:** 49 個

**実装範囲:**
* ホームページ表示
* ヘッダ・フッタナビゲーション
* カテゴリリンク
* 商品一覧（ページネーション、並び替え）
* 商品詳細ページ（商品名、画像、価格、説明、選択肢）
* バリエーション選択（フレーバー、サイズなど）
* カート表示と数量変更
* 商品削除（表示のみ）
* カート小計・合計金額の計算
* カート保存（ブラウザ セッション）
* 5ステップチェックアウトプログレス表示
* ゲスト会員登録フォーム
* 郵便番号検索機能（表示のみ）
* フォームバリデーション（必須項目、形式チェック）
* ログインページ表示
* 404 エラーページ

### テスト環境

| 項目 | 値 |
|---|---|
| **ブラウザ** | Google Chrome for iOS |
| **OS** | iOS |
| **デバイス** | iPhone |
| **テスト日時** | 2026-09-01 ～ 2026-09-02 JST |
| **テスト言語** | 日本語 |

### 使用ツール

* Google Chrome for iOS（モバイルテスト）
* Microsoft Excel（テストケース管理、RTM）
* Markdown（ドキュメント作成）
* JSON（テストデータ構造）
* CSV（要件管理）

### テスト内容

#### 1. 要件分析
* 49 個の機能を実装の有無、制限状況で分類
* 分類: 確認完了 25個、表示のみ 9個、制限 2個、未実装 2個、未観察 9個、不明 2個

#### 2. 要件定義
* 機能観察に基づいて 27 個の要件を定義
* 要件: REQ-001 ～ REQ-027

#### 3. テストシナリオ設計
* 確認済み機能から 20 個のテストシナリオを構築
* シナリオ: SCN-001 ～ SCN-020

#### 4. テストケース設計
* 40 個の完全なテストケースを設計
* テストケース: TC-001 ～ TC-040
* テストタイプ：機能テスト（24 個）、UI テスト（7 個）、ネガティブテスト（6 個）、スモークテスト（3 個）
* 各テストケースには前提条件、テストステップ、予想結果を記載

#### 5. トレーサビリティ管理
* 27 要件 → 20 シナリオ → 40 テストケース を完全にマッピング
* 要件-シナリオ-テストケース RTM を作成（カバレッジ 100%）

#### 6. 非バグの調査（NDF-001）
* モバイルでヘッダアイコンが表示されないことを発見
* Google Chrome for iOS で再検証
* アイコンが正しく表示されることを確認
* 原因: クラウド内ブラウザの表示バグ
* 結論: 環境の問題 → EC-CUBE のバグではない

### 成果物

**ドキュメント（8個）**
* `docs/01_application-analysis.md` - 機能分析（49個機能）
* `docs/02_scope-and-requirements.md` - 要件定義（27個要件）
* `docs/03_test-plan.md` - テスト計画書
* `docs/04_test-scenarios.md` - テストシナリオ（20個）
* `docs/05_test-execution-guide.md` - テスト実行ガイド
* `docs/06_bug-reporting-guide.md` - バグレポートプロセス
* `docs/07_jira-workflow.md` - Jira ワークフロー（シミュレーション）
* `docs/08_test-summary-report.md` - テストサマリーレポート

**テストケース（3個ファイル）**
* `test-cases/manual-test-cases.md` - 40個全テストケース
* `test-cases/test-cases.json` - 構造化テストデータ
* `test-cases/test-data.json` - テストデータ値

**Excel ワークブック（6個）**
* `excel/01_test_plan.xlsx` - テスト計画サマリー
* `excel/02_test_cases.xlsx` - 40個テストケース表
* `excel/03_test_execution.xlsx` - テスト実行記録
* `excel/04_bug_reports.xlsx` - バグレポート追跡表
* `excel/05_rtm.xlsx` - 要件トレーサビリティマトリクス
* `excel/06_test_summary.xlsx` - テスト結果サマリー（フォーミュラ使用）

**テスト証跡（4個）**
* `evidence/evidence-index.csv` - スクリーンショット インベントリ
* `evidence/screenshots/application-analysis/MOB-003-registration-form.png`
* `evidence/screenshots/application-analysis/MOB-004-cart-page.png`
* `evidence/screenshots/application-analysis/MOB-005-cart-variations.png`
* `evidence/screenshots/application-analysis/MOB-006-registration-form-second-try.png`

**バグレポート（2個ファイル）**
* `bug-reports/bug-reports.md` - バグレポート（NDF-001 のみ）
* `bug-reports/bug-reports.json` - 構造化バグデータ

**テストデータ（2個ファイル）**
* `test-data/test-data-guide.md` - テストデータポリシー
* `test-data/safe-fictional-test-data.md` - ダミーテストデータ

**Jira シミュレーション（3個ファイル）**
* `jira/jira-backlog.csv` - 22個イシューバックログ
* `jira/jira-workflow.md` - ワークフロー定義
* `jira/jira-issue-templates.md` - イシューテンプレート

**レポート（3個ファイル）**
* `reports/rtm.md` - 要件トレーサビリティマトリクス
* `reports/test-execution-results.json` - 実行結果データ
* `reports/test-summary-report.md` - テストサマリーレポート

### テスト結果

**テスト実行状況**
* テストケース設計数: 40 個
* テスト実行数: 0 個
* 合格: 0 個
* 失敗: 0 個

**理由:** このプロジェクトはテスト設計ポートフォリオです。テスト実行は行わず、テストケース設計と要件分析のスキルを示すことに重点を置いています。

### バグレポート

**報告済みバグ数: 0 個**

**非バグ調査結果: 1 個（NDF-001）**
* **タイトル:** ヘッダアイコン表示異常（環境バグ）
* **観察:** モバイルでヘッダアイコンが空白に表示された
* **調査:** Google Chrome for iOS で再検証
* **結論:** クラウド内ブラウザの表示バグ。EC-CUBE のバグではない

### テスト証跡

4 個のモバイル スクリーンショットを含む：

* **MOB-003** - 会員登録フォーム（ステップ 1）
* **MOB-004** - カートページ（2 商品、¥20,900）
* **MOB-005** - カート内バリエーション表示
* **MOB-006** - 会員登録フォーム（ステップ 2）

### 学んだこと

* **機能分析スキル** - 49 個の機能を観察し、実装・制限状況で正確に分類
* **要件定義スキル** - 観察に基づいて 27 個の明確な要件を定義
* **テストケース設計スキル** - 40 個のテストケースを段階的に構成
* **トレーサビリティ管理** - 要件からテストケースまで完全にマッピング
* **バグ判別スキル** - 環境バグと製品バグの区別方法を実証

### プロジェクト規模

| 項目 | 個数 |
|---|---:|
| ドキュメント | 8 |
| テストケース | 40 |
| 要件 | 27 |
| テストシナリオ | 20 |
| テスト証跡（スクリーンショット） | 4 |
| Excel ワークブック | 6 |
| JSON ファイル | 4 |
| Jira イシュー | 22 |
| **合計ファイル数** | **54** |

### 透明性と倫理

**AI アシスタント使用の開示**

このプロジェクトのテスト設計と要件分析はすべて手作業で実施しました。ドキュメント構造、フォーマット、一貫性の維持には AI アシスタントを使用しています。

* ✓ テスト観察：手作業（EC-CUBE デモサイトでのテスト）
* ✓ 要件定義：手作業（観察に基づく定義）
* ✓ テストケース設計：手作業（すべてのロジック）
* ✓ テスト証跡：実物（iPhone スクリーンショット）
* ✓ ドキュメント構造：AI アシスタント（フォーマット）
* ✓ データ不正：なし（すべて実物）

---

## English Version

### Project Overview

This is a manual QA testing portfolio project for EC-CUBE 4.2.3, an open-source e-commerce platform. The project includes analysis of 49 application features, definition of 27 functional requirements, and design of 40 test cases with full traceability mapping. This is a test design portfolio, not a test execution portfolio.

### Application Under Test

**Application:** EC-CUBE 4.2.3  
**Environment:** https://ec-cube.sakura.ne.jp/4-2-demo/  
**Language:** Japanese

### Test Objective

Demonstrate manual QA testing capability for Japanese e-commerce websites. The project demonstrates:

* Requirements analysis and definition
* Test planning
* Test case design
* Test scenario construction
* Requirements-to-test-case traceability management
* Test evidence management

### Test Scope

**Features analyzed:** 49

**In-scope testing:**
* Home page display
* Header and footer navigation
* Category links
* Product listing (pagination, sorting)
* Product detail pages (name, image, price, description, options)
* Product variations (flavor, size, etc.)
* Add to cart functionality
* Shopping cart display
* Quantity adjustment controls
* Item removal from cart (display only)
* Cart subtotal and total calculations
* Cart persistence
* 5-step checkout progress indicator
* Guest registration form
* Postal code lookup (display only)
* Form validation (required fields, format checks)
* Login page display
* 404 error page

### Test Environment

| Item | Value |
|---|---|
| **Browser** | Google Chrome for iOS |
| **OS** | iOS |
| **Device** | iPhone |
| **Test Dates** | 2026-09-01 to 2026-09-02 JST |
| **Test Language** | Japanese |

### Tools

* Google Chrome for iOS (mobile testing)
* Microsoft Excel (test case management, traceability)
* Markdown (documentation)
* JSON (test data structure)
* CSV (requirements management)

### Testing Performed

#### 1. Feature Analysis
* 49 features classified by availability and access status
* Classification: Available (25), Display-only (9), Restricted (2), Not available (2), Not observed (9), Unable to verify (2)

#### 2. Requirements Definition
* 27 functional requirements defined from observation
* Requirements: REQ-001 to REQ-027

#### 3. Test Scenario Design
* 20 test scenarios constructed from confirmed features
* Scenarios: SCN-001 to SCN-020

#### 4. Test Case Design
* 40 complete test cases designed
* Test cases: TC-001 to TC-040
* Test types: Functional (24), UI (7), Negative (6), Smoke (3)
* Each test case includes preconditions, test steps, and expected results

#### 5. Traceability Management
* 27 Requirements → 20 Scenarios → 40 Test Cases fully mapped
* Requirements Traceability Matrix (RTM) created with 100% coverage

#### 6. Non-Defect Investigation (NDF-001)
* Suspected header icon rendering issue on mobile
* Re-verified in Google Chrome for iOS
* Icons rendered correctly
* Root cause: In-app browser display artifact
* Conclusion: Environment issue → Not a product defect

### Deliverables

**Documentation (8 files)**
* `docs/01_application-analysis.md` - Feature analysis
* `docs/02_scope-and-requirements.md` - Requirements definition
* `docs/03_test-plan.md` - Test plan
* `docs/04_test-scenarios.md` - Test scenarios
* `docs/05_test-execution-guide.md` - Test execution guide
* `docs/06_bug-reporting-guide.md` - Bug reporting process
* `docs/07_jira-workflow.md` - Jira workflow
* `docs/08_test-summary-report.md` - Test summary report

**Test Cases (3 files)**
* `test-cases/manual-test-cases.md` - All 40 test cases
* `test-cases/test-cases.json` - Structured test data
* `test-cases/test-data.json` - Test data values

**Excel Workbooks (6 files)**
* `excel/01_test_plan.xlsx` - Test plan summary
* `excel/02_test_cases.xlsx` - 40 test cases table
* `excel/03_test_execution.xlsx` - Test execution records
* `excel/04_bug_reports.xlsx` - Defect tracking table
* `excel/05_rtm.xlsx` - Requirements Traceability Matrix
* `excel/06_test_summary.xlsx` - Test result summary (formulas)

**Test Evidence (4 files)**
* `evidence/evidence-index.csv` - Screenshot inventory
* Mobile screenshots in `evidence/screenshots/application-analysis/`

**Bug Reports (2 files)**
* `bug-reports/bug-reports.md` - Bug reports (NDF-001 only)
* `bug-reports/bug-reports.json` - Structured bug data

**Test Data (2 files)**
* `test-data/test-data-guide.md` - Test data policy
* `test-data/safe-fictional-test-data.md` - Test data

**Jira Simulation (3 files)**
* `jira/jira-backlog.csv` - 22-issue backlog
* `jira/jira-workflow.md` - Workflow definition
* `jira/jira-issue-templates.md` - Issue templates

**Reports (3 files)**
* `reports/rtm.md` - Requirements Traceability Matrix
* `reports/test-execution-results.json` - Execution data
* `reports/test-summary-report.md` - Test summary report

### Test Results

**Test Execution Status**
* Test cases designed: 40
* Test cases executed: 0 (design portfolio only)
* Passed: 0
* Failed: 0

**Note:** This is a test design portfolio demonstrating requirements analysis and test case design skills, not test execution.

### Bug Reports

**Defects reported: 0**

**Non-defect investigation: 1 (NDF-001)**
* **Title:** Header Icon Display Issue (Environment)
* **Observation:** Header icons displayed as blank on mobile
* **Investigation:** Re-verified in Google Chrome for iOS
* **Conclusion:** In-app browser artifact. Not an EC-CUBE defect.

### Test Evidence

Four mobile screenshots included showing registration form, cart page, and cart variations.

### What I Learned

* **Feature Analysis** - Observed and classified 49 features by implementation status
* **Requirements Definition** - Defined 27 clear requirements from observation
* **Test Case Design** - Designed 40 test cases with clear structure
* **Traceability Management** - Created complete mapping with 100% coverage
* **Defect Investigation** - Distinguished environment issues from product defects

### Project Size

| Item | Count |
|---|---:|
| Documentation files | 8 |
| Test cases | 40 |
| Requirements | 27 |
| Test scenarios | 20 |
| Test evidence (screenshots) | 4 |
| Excel workbooks | 6 |
| JSON files | 4 |
| Jira issues | 22 |
| **Total files** | **54** |

### Transparency and Ethics

**AI Assistant Disclosure**

All test observation, analysis, and design decisions were performed manually. AI assistance was used only for documentation structure, formatting, and consistency.

* ✓ Test observation: Manual
* ✓ Requirements definition: Manual
* ✓ Test case design: Manual
* ✓ Test evidence: Real (iPhone screenshots)
* ✓ Documentation structure: AI-assisted
* ✓ Data integrity: None fabricated

This project contains no fabricated test results, invented bugs, fake screenshots, or false test data.

---

**このプロジェクトは、テスト設計スキルを示すための手作業で実施されたポートフォリオプロジェクトです。**

**This project is a manual QA portfolio demonstrating test design and requirements analysis skills.**
