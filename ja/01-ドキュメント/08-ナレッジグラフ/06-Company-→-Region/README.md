<!--
id: RX-PRODUCT-1069
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f23355e
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: review-needed
source_route: knowledge-graph/company-region
-->

# 🌍 Company → Region

**メソッド:** `GET`

**エンドポイント:** `/ontology/v3/company/{tag}/region-exposure?limit=`

企業のより広い地域別エクスポージャーを、次の要素に基づいて返します。

1. **Revenue Attribution**: 企業の総売上高のうち、特定の国・地域に帰属する割合
2. **Strategic Importance**: その国・地域が企業の将来戦略にどの程度重要か
3. **Supply Chain Dependencies**: 地理的なサプライチェーンの所在と依存関係
4. **Capital Investments**: 設備投資、R&D、マーケティング予算など地域別の投資・資源配分

#### クエリパラメータ

`limit` — integer — 返す結果件数を制限します。

#### パスパラメータ

`tag` — string — **必須**

企業のtagです。

### レスポンス

**200** — Object: 企業がエクスポージャーを持つ地域と詳細を返します。

#### レスポンス属性

- `code` — string — 地域コード
- `name` — string — 地域名
- `icon_url` — string — 地域アイコンのURL
- `relationship` — object — 詳細なリレーションシップ情報

**400** — Object: 不正なリクエストです。

**404** — Object: 見つかりません。

**500** — Object: サーバー内部エラーです。

---

[← ドキュメント](../../README.md)
