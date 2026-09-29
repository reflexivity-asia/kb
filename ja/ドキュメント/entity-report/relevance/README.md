<!--
id: RX-PRODUCT-1060
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
source_id: 6a1ea624d2cd820b12c29016
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: review-needed
source_route: entity-report/relevance
-->

# V1 Relevance

**メソッド:** `GET`

**エンドポイント:** `/entity-report/v1/entity/{entity_tag}/relevance`

カードに表示する関連情報を取得します。

#### パスパラメータ

`entity_tag` — string — **必須**

エンティティの一意な識別子です。

### レスポンス

**200** — Object: 正常終了

#### レスポンス属性

- `id` — integer — カードID
- `expression` — string — カードの内部式
- `last_value` — number — Snakeの直近値
- `name` — string — カード名
- `image_url` — string — カード画像のURL
- `explanation` — string — カードの説明
- `connected_article_title` — string — 関連記事のタイトル
- `connected_article_url` — string — 関連記事のURL
- `scenario_condition` — object — Scenarioツールに送信するペイロード
- `group_code` — string — 所属グループのコード
- `group_name` — string — 所属グループ名
- `group_icon_url` — string — 所属グループのアイコンURL
- `snake_last_date` — string — Snakeの最終更新日

**400** — Object: entity tag が不正です。

**404** — Object: entity tag が見つかりません。

---

[← ドキュメント](../../README.md)
