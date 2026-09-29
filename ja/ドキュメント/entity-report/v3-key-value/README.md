<!--
id: RX-PRODUCT-1061
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
source_id: 6a2698f40d17aeec4a2f1d3e
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: review-needed
source_route: entity-report/v3-key-value
-->

# V3 Key-value

**メソッド:** `GET`

**エンドポイント:** `/entity-report/v3/entity/{entity_tag}/key-values`

カードに表示するSnakeのファンダメンタル情報を取得します。

#### パスパラメータ

`entity_tag` — string — **必須**

エンティティの一意な識別子です。

### レスポンス

**200** — Object: 正常終了

#### レスポンス属性

- `expression` — string — Snakeの式
- `value_string` — string — 文字列形式の値
- `label` — string — 値のラベル
- `explanation` — string — ファンダメンタルカードの説明
- `group_code` — string — 所属グループのコード
- `group_name` — string — 所属グループ名
- `group_icon_url` — string — 所属グループのアイコンURL

**400** — Object: entity tag が不正です。

**404** — Object: entity tag が見つかりません。

---

[← ドキュメント](../../README.md)
