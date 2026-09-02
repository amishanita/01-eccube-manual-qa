# Safe Fictional Test Data

Quick reference. The full policy is in `test-data-guide.md`.

## Customer

| Field | Value |
|---|---|
| 姓 | テスト |
| 名 | 太郎 |
| セイ | テスト |
| メイ | タロウ |
| 会社名 | (leave blank) |
| メールアドレス | qa.test.example@example.test |
| 電話番号 | 090-0000-0000 |
| 郵便番号 | 1000001 |
| 都道府県 | 東京都 |
| 市区町村名 | 千代田区 |
| 番地・ビル名 | テスト1-2-3 |
| パスワード | QaDemo!Test2026 |

## Invalid Data for Negative Tests

| Purpose | Value |
|---|---|
| Romaji in katakana field | ramu / amsu |
| Malformed email | test@@test |
| Password too short | Qa1! |
| No-match search keyword | zzzzz |

## Boundary Values

| Field | Rule |
|---|---|
| Password | 半角英数記号12〜50文字 (12 to 50 half-width alphanumeric and symbols) |
| Cart quantity | Minimum observed: 1. Maximum unknown |

## Never Use

Real name, real address, real phone, real email, a password used elsewhere,
payment details, residence card or My Number details, API tokens, cookies.

## Why example.test

`example.test` is a reserved domain that cannot receive mail. It is deliberately
undeliverable, which is correct here since demo email is disabled anyway.
