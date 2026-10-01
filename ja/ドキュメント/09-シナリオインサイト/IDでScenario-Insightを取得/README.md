<!--
id: RX-PRODUCT-1076
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f23354c
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: review-needed
source_route: scenario-insights/get-insight-based-on-requested-id
-->

# IDでScenario Insightを取得

**メソッド:** `GET`

**エンドポイント:** `/insights/v1/{id}`

#### パスパラメータ

`id` — string — **必須**

### レスポンス

**200** — Object: インサイトを返します。

#### レスポンス属性

- `conditions` — array
- `episodes` — array
- `hit_ratio` — object
- `metadata` — object
- `id` — string
- `title` — string
- `content` — array
- `disclaimer` — string
- `card` — object
- `created_at` — string (date-time)
- `charts` — array

**404** — Object: 見つかりません。

**500** — Object: サーバー内部エラーです。

---

[← ドキュメント](../../README.md)
