# 01 / EC-CUBE 手動テスト設計・不具合報告

ECサイト構築パッケージ EC-CUBE 4.2.3 を自分のPCに立てて、機能の洗い出しからテストケース設計、実施、不具合報告まで一通りやりました。

## 結果

| 項目 | 数 |
|---|---:|
| 洗い出した機能 | 49 |
| 整理した要件 | 27 |
| 設計・実施したテストケース | 40 |
| 検出した不具合 | 【要確認：実際の件数】 |

対象：EC-CUBE 4.2.3（ローカル構築）
時期：2026年8月
設計・実施・報告はすべて一人でやりました。

## この題材を選んだ理由

仕事ではソフトウェアテストに触れる機会がないので、実際に動くサイトを自分で用意するところから始めました。

EC-CUBEにしたのは、日本のEC構築でよく使われていて業務に近いこと、注文・決済・在庫・会員といったお金と個人情報が動く機能が揃っていること、公式ドキュメントがあるので仕様と実装を突き合わせられることの3点です。

## やったこと

### 機能の洗い出し（49件）

管理画面とフロント画面を実際に触って、ユーザーができる操作を1つずつ書き出しました。この段階では優先度をつけず、数を揃えることだけを考えています。

### 要件への整理（27件）

49件を、実際の使われ方（商品を探す、カートに入れる、注文する、管理側で処理する）の流れに沿って27件にまとめ直しました。

機能ごとにテストを作ると、画面が正しく表示されるかの確認で終わってしまいます。一連の流れとして成立しているかが抜けるので、要件の形に直しました。

### テストケースの設計（40件）

27件の要件それぞれに、正常系・異常系・境界値を割り当てました。40という数字を先に決めたわけではなく、要件から落としていった結果です。

優先度のつけ方はこうしています。

| 優先度 | 対象 |
|---|---|
| 高 | カート投入、注文確定、会員登録・ログイン |
| 中 | 商品検索、在庫表示、管理画面の受注処理 |
| 低 | 表示崩れ、文言、ソート順 |

お金と個人情報が動くところを上に置きました。

組み合わせを全部試すのは無理なので、**確認しないと決めた範囲も記録しています**。どの組み合わせを落としたか、なぜ落としたかを残しました。後から見た人が、抜けなのか意図なのかを判断できるようにするためです。

### 実施と記録

各ケースについて、期待結果、実際の結果、判定、判定の根拠を記録しました。合格にした場合も、なぜ合格と判断したかを書いています。

## 不具合報告の形式

次の項目を毎回同じ順番で書いています。

- タイトル（症状が一行で分かるもの）
- 発生環境（OS、ブラウザ、EC-CUBEのバージョン）
- 再現手順（番号付き、1手順1操作）
- 期待結果
- 実際の結果
- 再現率
- スクリーンショット
- 影響範囲と優先度

基準にしているのは、読んだ人が同じ手順をなぞれば同じ結果になるかどうかです。

### 検出した不具合の例

【要確認：実際に見つけた不具合を1件、上の形式で書く】

## リポジトリ構成

```
.
├── docs/
│   ├── requirements.md        整理した27件の要件
│   └── scope.md               確認する範囲と、確認しないと決めた範囲
├── test-cases/
│   └── test-cases.xlsx        テストケース40件
├── bug-reports/
├── evidence/
│   └── screenshots/
└── README.md
```

【要確認：実際のフォルダ構成に合わせて書き換える】

## 環境

EC-CUBE 4.2.3（ローカル構築）、macOS 15.7（Intel MacBook Pro）、Google Chrome、Excel

## やってみて分かったこと

テスト設計の時間の大半は、何を確認するかより、何を確認しないかを決めることに使いました。全部は試せないので、どこで線を引いたかを説明できる状態にしておかないと、後で「なぜここを見ていないのか」に答えられなくなります。

不具合報告は、書いた本人が分かっているかではなく、次に読む人が動かせるかで決まります。自分では再現できているのに、手順を書いてみると情報が足りていないことが何度かありました。

## 次にやること

- JSTQB Foundation Level 受験（2026年11月11日）
- ここで設計したケースのうち、繰り返す部分を Playwright で自動化（[02](https://github.com/amishanita/02-saucedemo-playwright-python)）

## 関連リポジトリ

| | 内容 |
|---|---|
| 01（このリポジトリ） | EC-CUBE 手動テスト設計・不具合報告 |
| [02](https://github.com/amishanita/02-saucedemo-playwright-python) | Playwright と pytest によるUI自動テスト |
| [03](https://github.com/amishanita/03-restful-booker-api-automation) | REST API のテストと不具合検出 |
| [04](https://github.com/amishanita/04-saucedemo-ci-cd-qa) | GitHub Actions による自動実行 |

---

# English

# 01 / EC-CUBE Manual Test Design and Bug Reporting

I installed EC-CUBE 4.2.3, a Japanese e-commerce platform, on my own machine and worked through the whole cycle: feature inventory, requirements, test design, execution, defect reports.

## Results

| Item | Count |
|---|---:|
| Features inventoried | 49 |
| Requirements derived | 27 |
| Test cases designed and executed | 40 |
| Defects found | TBD |

Done in August 2026. I did the design, the execution and the reporting myself.

## Why this subject

Testing isn't part of my job, so I needed an application of my own to work on. EC-CUBE is widely used for e-commerce in Japan, it has the parts where money and personal data move, and it publishes documentation, so I could compare what the docs say with what the software does.

## What I did

**Feature inventory, 49 items.** I walked through the admin screens and the storefront and wrote down every action a user can take. No prioritising at this stage.

**Requirements, 27 items.** I regrouped those features along the way the site actually gets used: browse, add to cart, order, process in the back office. Testing feature by feature checks that screens render. It misses whether the sequence holds together.

**Test cases, 40.** Positive, negative and boundary cases against each requirement. I didn't set out to write 40; that's what came out of the requirements.

Priority went to the money path first (cart, checkout, accounts), then search and back-office processing, then layout and wording.

Trying every combination isn't possible, so I also recorded what I decided not to test and why. Someone reading it later should be able to tell a gap from a decision.

**Execution.** For each case I recorded the expected result, the actual result, the verdict, and the reasoning behind it, including for passes.

## Bug report format

Title, environment, numbered steps, expected, actual, reproduction rate, screenshot, impact and priority. Same order every time. The test is whether someone else can follow the steps and land on the same result.

## Environment

EC-CUBE 4.2.3 (local), macOS 15.7, Google Chrome, Excel.

## What I learned

Most of the time went into deciding what to leave out, not what to cover. If you can't explain where you drew the line, you can't answer for the parts you skipped.

A defect report is only useful if the next person can act on it. More than once I could reproduce something myself, then found the steps I'd written weren't enough for anyone else.

## Next

JSTQB Foundation Level on 11 November 2026. Automating the repeatable cases in [02](https://github.com/amishanita/02-saucedemo-playwright-python).

**Tamang Amish** — [GitHub](https://github.com/amishanita) / [LinkedIn](https://www.linkedin.com/in/tamang-amish-669289250)
