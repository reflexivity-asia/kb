<!--
id: RX-PRODUCT-1057
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
source_id: 6a269fb8e429230e769e416b
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: review-needed
source_route: entity/get-filtered-entities
-->

# 条件を指定してエンティティを取得

**メソッド:** `POST`

**エンドポイント:** `/entity/v2/filtered`

#### ボディパラメータ

- `filter` — integer — `2`: FilterTag
- `args` — array

### レスポンス

**200** — Object: エンティティ一覧を返します。

#### レスポンス属性

`tag`, `id`, `known_as`, `name`, `name_full`, `name_short`, `active`, `asset_class`, `class`, `country`, `currency`, `exchange`, `gics`, `has_news`, `isin`, `market_classification`, `mnemonic`, `mnemonic_ibes`, `primary_method`, `priority`, `region`, `search`, `spx`, `sub_class`, `overview_disabled`, `ticker`, `ticker_bloomberg`, `default_snake`, `connected`, `popular`, `company_description`, `logo_url`, `gated`, `american_deposit_receipt`, `polygon_ticker`, `fx_currency`, `trading_country`, `cusip`, `sedol`, `figi`, `subscribable_ticker`, `logo_urls`

`asset_class` の enum:

- `0` — ASSET_CLASS_UNSPECIFIED
- `1` — ASSET_CLASS_COMMODITY
- `2` — ASSET_CLASS_FX
- `3` — ASSET_CLASS_EQUITY
- `4` — ASSET_CLASS_FI
- `5` — ASSET_CLASS_CURRENCY

`class` の enum:

- `0` — CLASS_UNSPECIFIED
- `1` — CLASS_ECO
- `2` — CLASS_COMMODITY
- `3` — CLASS_CREDIT
- `4` — CLASS_EQUITY
- `5` — CLASS_ETF
- `6` — CLASS_FI
- `7` — CLASS_FUTURE
- `8` — CLASS_FX
- `9` — CLASS_STOCK
- `10` — CLASS_CURRENCY
- `11` — CLASS_MUTUAL_FUND

**400** — Object: 不正なリクエストです。

---

[← ドキュメント](../../README.md)
