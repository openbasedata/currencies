# Currencies Open Base Data

## How To Use

```bash
npm install @openbasedata/currencies
```

`data.json` contains currency metadata with:

- `name` in English
- `nativeName` in each currency's native language

Other localized translations are split into `/translations/<locale>.json` (one language per file) to keep the main dataset smaller.

## Data Structure

```json
[
  {
    "code": "CNY",
    "numericCode": "156",
    "name": "Chinese Renminbi Yuan",
    "nativeName": "人民币",
    "symbol": "¥"
  }
]
```

| Field         | Type     | Required | Description                                                                 |
| ------------- | -------- | -------- | --------------------------------------------------------------------------- |
| `code`        | `string` | Yes      | ISO 4217 alphabetic currency code (3 uppercase letters), e.g. `CNY`.        |
| `numericCode` | `string` | Yes      | ISO 4217 numeric currency code (3-digit string, zero-padded), e.g. `"156"`. |
| `name`        | `string` | Yes      | English currency name.                                                      |
| `nativeName`  | `string` | Yes      | Currency name in the native language of the issuing country.                |
| `symbol`      | `string` | Yes      | Commonly used currency symbol, e.g. `¥`.                                    |

## Translations

Translations are stored in `/translations`, one file per locale (for example: `/translations/zh-Hans.json`, `/translations/fr.json`). English is stored directly in `data.json`.

Each translation file has this structure:

```json
{
  "CNY": {
    "name": "Chinese Renminbi Yuan"
  }
}
```
