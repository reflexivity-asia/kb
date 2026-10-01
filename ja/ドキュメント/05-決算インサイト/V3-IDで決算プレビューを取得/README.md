<!--
id: RX-PRODUCT-1048
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
source_id: 6a22f0d78b402c5641fc8972
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: review-needed
source_route: earnings-insights/v3-get-earnings-preview-by-id
-->

# V3 IDで決算プレビューを取得

**メソッド:** `GET`

**エンドポイント:** `/earnings-insights/v3/preview/{id}`

指定した決算インサイトの詳細プレビューを返します。シナリオ、目標株価、KPI、テーマ、影響を受ける企業などが含まれます。決算発表前に生成されます。v2とは異なり、すべてのテーマは単一の `themes` 配列で返され、各テーマにはカタログに基づく `id` が付与されます。`other_themes` フィールドはありません。

#### ヘッダーパラメータ

`Accept-Language` — string

レスポンス本文の言語を指定する IETF BCP 47 言語タグです。指定すると、タイトル、説明、KPI、テーマなどのインサイト本文を指定言語で返します。省略時は `en` が既定値です。指定言語のインサイトが存在しない場合は `404` を返します。

現在対応している言語: `ar`, `de`, `en`, `fr`, `he`, `hu`, `it`, `ja`, `ko`, `nl`, `pt`, `ru`, `es`, `zh-Hans`, `zh-Hant`

#### パスパラメータ

`id` — string (uuid) — **必須**

決算インサイト・プレビューの一意なIDです。

### レスポンス

**200** — Object: 決算プレビューの詳細を正常に返します。

#### レスポンス属性

- `id` — string (uuid)
- `type` — string — enum: `preview`
- `title` — string
- `company` — object
- `earnings` — object
- `price_targets` — object
- `beats_scenario` — object
- `misses_scenario` — object
- `sentiment_expectations` — array
- `seasonality` — array
- `kpis` — array
- `key_items_to_watch` — array
- `investment_outlook` — object
- `themes` — array
- `impacted_companies` — array
- `created_at` — string (date-time)

**404** — Object: インサイトが見つからない、または指定言語のインサイトが利用できません。

---

[← ドキュメント](../../README.md)
