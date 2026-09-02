# Test Data Guide (テストデータ方針)

**Project:** EC-CUBE Manual QA Testing & Bug Reporting
**Environment:** Public shared demo (ENV-EC-001)

---

## 1. Why this policy exists

The application under test is a **public demo site shared with other users**. The
site operator states plainly that real names and addresses must not be entered.
Anything typed into it should be treated as visible to strangers.

On top of that, this repository is public on GitHub. Any screenshot committed
here is permanently readable by anyone.

Both facts lead to one rule:

> Only fictional data enters the test environment, and only fictional data enters
> this repository.

---

## 2. Never use

- Real full name
- Real home or work address
- Real phone number
- Real personal or work email address
- **A password used on any other service**
- Credit card or bank account details
- Residence card (在留カード) or My Number (マイナンバー) details
- API tokens, cookies, or session identifiers
- Shared demo login credentials, even if someone published them

---

## 3. Approved fictional data

Do not use any of these until the related form is confirmed to exist and is in
scope. As of the Phase 1 analysis, no form has been submitted.

### Customer identity

| Field | Value |
|---|---|
| 姓 (Last name) | テスト |
| 名 (First name) | 太郎 |
| セイ (Last name kana) | テスト |
| メイ (First name kana) | タロウ |
| Last name (romaji) | Test |
| First name (romaji) | Taro |
| 会社名 (Company, optional) | Leave blank |

### Contact

| Field | Value |
|---|---|
| Email | qa.test.example@example.test |
| Alternate email | qa.tester.02@example.test |
| Telephone | 090-0000-0000 |

`example.test` is a reserved domain that cannot receive mail. This is deliberate.
Email delivery is disabled on this demo anyway (LIM-02).

### Address

| Field | Value |
|---|---|
| 郵便番号 (Postal code) | 1000001 |
| 都道府県 (Prefecture) | 東京都 |
| 市区町村名 (City) | 千代田区 |
| 番地・ビル名 (Street) | テスト1-2-3 |

Note: the registration form includes a 郵便番号検索 (postal code lookup) link. If
that lookup is tested, use the postal code above and confirm which prefecture and
city it returns before relying on it.

### Passwords

Use a throwaway string that exists nowhere else, for example:

```
QaDemo!Test2026
```

This value is written here **only because it is disposable and used solely on a
public demo site**. Never place a real password in this repository, even in a
private file.

---

## 4. Search keywords (for future use)

Do not populate these until the search feature is actually executed and its
behaviour is recorded.

| Type | Values | Status |
|---|---|---|
| Valid keywords | To be taken from real product names visible on the site | Not yet collected |
| No-match keyword | `zzzzz` | Not yet executed |
| Whitespace only | Single space character | Not yet executed |
| Long string | 256 characters | Not yet executed |
| Special characters | `<>&"'` | Not yet executed |

Note that the fifth row is for input-handling observation only. This is a
functional and boundary check on how the field handles unusual characters. Do not
attempt any form of attack against a shared public site.

---

## 5. Boundary values (for future use)

The cart quantity control has been observed to work between 1 and 2. The upper
and lower limits are unknown.

| Field | Value to test | Status |
|---|---|---|
| Cart quantity | Decrease below 1 | Not yet executed |
| Cart quantity | Very large value such as 9999 | Not yet executed |
| Product detail quantity | 0 | Not yet executed |
| Product detail quantity | Non-numeric text | Not yet executed |

---

## 6. Incident record

Recording mistakes honestly is part of the QA discipline this project is meant to
demonstrate.

| ID | Date | Description | Action taken |
|---|---|---|---|
| INC-01 | 2026-09-01 | A real personal email address and a password were entered into the login form of the public shared demo site, and the screen was captured in a screenshot | Screenshot excluded from the repository and deleted. Password to be changed on any service where it was reused. Fictional data policy written and adopted before any further testing |

This incident is the reason this document exists. It is kept in the repository as
a record of the control that was put in place, not as evidence of testing.

---

## 7. Pre-commit checklist

Before every commit, confirm:

- [ ] No screenshot shows a real email address
- [ ] No screenshot shows a password field with a real password entered
- [ ] No screenshot shows a real name, address, or phone number
- [ ] No file contains an API token, cookie, or session ID
- [ ] Every data value used in a test case appears in section 3 of this document
