<!--
id: RX-PRODUCT-1075
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f23354e
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: review-needed
source_route: scenario-insights/get-filtered-insights
-->

# Scenario Insightを絞り込む

**メソッド:** `POST`

**エンドポイント:** `/insights/v1/filter`

リクエストボディの各フィールドはすべて任意です。フィルターを使用しない場合は、そのフィールドを省略するか、`null` または空配列（`[]`）を指定します。

少なくとも1つの絞り込み条件（例: entity）を指定してください。フィルターなしのクエリは処理に時間がかかり、タイムアウトする場合があります。

空文字列や空文字列を要素に含む値は送らないでください。次の例はいずれも `400` を返します。

- `from_date` / `to_date` / `direction` に `""`
- 数値配列（`class`, `asset_cls`, `stars`, `sub_cls`）に `[""]`

フィルターはすべて組み合わせて適用されます。条件を絞り込みすぎると結果が0件になることがあります。

#### ボディパラメータ

- `topic` — array — 指定したトピックのいずれかに一致するインサイト
- `asset_cls` — array — 指定した資産クラスのいずれかに一致するインサイト。enum: `0`, `1`, `2`, `3`, `4`, `5`
- `class` — array — 指定したクラスのいずれかに一致するインサイト
- `direction` — integer — `1`: Up、`2`: Down
- `eco` — array — 指定した経済圏のいずれかに一致するインサイト
- `entity` — array — 指定したentity tagのいずれかに一致するインサイト
- `event` — array — 指定したイベントのいずれかに一致するインサイト
- `horizon` — array — 指定したhorizonのいずれかに一致するインサイト
- `last_value__lte` — number
- `market_cap_usd_bn__gte` — number
- `market_cap_usd_bn__lt` — number
- `median_return__gte` — number
- `median_return__lt` — number
- `sector` — array
- `stars` — array
- `sub_class` — array
- `from_date` — string (date-time) — 指定日時より後に作成されたインサイト
- `to_date` — string (date-time) — 指定日時より前に作成されたインサイト
- `page` — integer — ページ番号
- `limit` — integer — 返す件数の上限

### レスポンス

**200** — Object: インサイト一覧を返します。

#### レスポンス属性

- `result` — array

**400** — Object: 不正なリクエストです。

**500** — Object: サーバー内部エラーです。

---

[← ドキュメント](../../README.md)
