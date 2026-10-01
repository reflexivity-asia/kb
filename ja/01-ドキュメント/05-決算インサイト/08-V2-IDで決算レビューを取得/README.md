<!--
id: RX-PRODUCT-1052
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f233542
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: review-needed
source_route: earnings-insights/v2-get-earnings-recap-by-id
-->

# V2 IDで決算レビューを取得

**メソッド:** `GET`

**エンドポイント:** `/earnings-insights/v2/recap/{id}`

指定した決算インサイトの詳細レビューを返します。実績、KPI、同業比較、リスク評価、テーマ、引用元などが含まれます。決算発表後に生成されます。

#### ヘッダーパラメータ

`Accept-Language` — string

レスポンス本文の言語を指定する IETF BCP 47 言語タグです。指定すると、タイトル、説明、KPI、テーマなどのインサイト本文を指定言語で返します。省略時は `en` が既定値です。指定言語のインサイトが存在しない場合は `404` を返します。

現在対応している言語: `ar`, `de`, `en`, `fr`, `he`, `hu`, `it`, `ja`, `ko`, `nl`, `pt`, `ru`, `es`, `zh-Hans`, `zh-Hant`

#### パスパラメータ

`id` — string (uuid) — **必須**

決算インサイト・レビューの一意なIDです。

### レスポンス

**200** — Object: 決算レビューの詳細を正常に返します。

#### レスポンス属性

- `id` — string (uuid)
- `type` — string — enum: `recap`
- `title` — string
- `company` — object
- `earnings` — object
- `key_metrics` — string
- `guidance_update` — string
- `price_scenario` — object
- `kpis` — array
- `peer_comparison_sector_context` — array
- `risk_assessment_update` — array
- `themes` — array
- `other_themes` — array
- `impacted_companies` — array
- `citations` — array
- `created_at` — string (date-time)

**404** — Object: インサイトが見つからない、または指定言語のインサイトが利用できません。

---

[← ドキュメント](../../README.md)
