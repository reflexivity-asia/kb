<!--
id: RX-PRODUCT-1053
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f233544
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: review-needed
source_route: earnings-insights/v1-filter-earnings-insights
-->

# V1 決算インサイトを絞り込む

**メソッド:** `POST`

**エンドポイント:** `/earnings-insights/v1/filter`

指定した条件に基づいて決算インサイトの一覧を返します。

リクエストボディの各フィールドはすべて任意です。使用しないフィールドは空の値を送らず、省略してください。

- `from` / `to` に空文字列を送ると `400` を返します。
- `entities` / `earnings_ids` に空配列（`[]`）を送ると何も一致せず、結果は0件になります。

#### ヘッダーパラメータ

`Accept-Language` — string

レスポンス本文の言語を指定する IETF BCP 47 言語タグです。省略時は `en` が既定値です。指定言語が利用できない場合は `404` を返します。

現在対応している言語: `ar`, `de`, `en`, `fr`, `he`, `hu`, `it`, `ja`, `ko`, `nl`, `pt`, `ru`, `es`, `zh-Hans`, `zh-Hant`

#### ボディパラメータ

- `entities` — array — entity tag の一覧。使用しない場合は省略します。
- `earnings_ids` — array — earnings ID の一覧。使用しない場合は省略します。
- `types` — array — enum: `preview`, `recap`
- `from` — string (date-time) — 絞り込み開始日時（含む）
- `to` — string (date-time) — 絞り込み終了日時（含む）
- `page` — integer — ページ番号
- `page_size` — integer — 1ページあたりの件数

### レスポンス

**200** — Object: 条件に一致する決算インサイトを返します。

#### レスポンス属性

- `id` — string (uuid)
- `type` — string — enum: `recap`, `preview`
- `entity_tag` — string
- `earnings_id` — string (uuid)
- `title` — string
- `created_at` — string (date-time)
- `updated_at` — string (date-time)

---

[← ドキュメント](../../README.md)
