<!--
id: RX-PRODUCT-1067
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f233558
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: review-needed
source_route: knowledge-graph/theme-company
-->

# 🎯 Theme → Company

**メソッド:** `GET`

**エンドポイント:** `/ontology/v3/theme/{theme_id}/company-exposure?limit=`

指定したテーマに対する重要度で企業をランキングして返します。対象となるには時価総額が10億米ドルを超えている必要があります。

ランキングには次の要素を使用します。

1. **Revenue Contribution**: テーマ全体のグローバル売上高に占める企業の寄与度
2. **Products and Services**: 企業の製品・サービス・ブランドがテーマの中核をどの程度形成しているか
3. **Capital Investment**: テーマ全体のR&D、設備投資、インフラ投資に占める企業の寄与度
4. **Strategic Importance**: テーマにおける市場シェア、業界標準への影響、エコシステムでのリーダーシップ
5. **Brand Significance**: 企業ブランドの認知度とテーマとの結びつき

#### クエリパラメータ

`limit` — integer — 返す結果件数を制限します。

#### パスパラメータ

`theme_id` — string — **必須**

テーマIDです。

### レスポンス

**200** — Object: テーマへのエクスポージャーを持つ企業と詳細メタデータを返します。

#### レスポンス属性

- `company` — string — company tag
- `relationship` — object — 詳細なリレーションシップ情報

**400** — Object: 不正なリクエストです。

**404** — Object: 見つかりません。

**500** — Object: サーバー内部エラーです。

---

[← ドキュメント](../../README.md)
