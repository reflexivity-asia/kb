<!--
id: RX-PRODUCT-1080
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
source_id: 6a269dd10d17aeec4a2fa243
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: review-needed
source_route: price-history/get-delayed-prices
-->

# 遅延価格を取得

**メソッド:** `GET`

**エンドポイント:** `/price-history/v1/delayed?ticker=STLA&entity_tag=stla_nyse&datasource=nasdaq`

指定したパラメータに基づいて価格データの一覧を返します。

返される価格の対象期間は、現在時刻の24時間15分前から15分前までです。

#### クエリパラメータ

- `ticker` — string — **必須** — 証券のsubscribable ticker
- `entity_tag` — string — **必須** — エンティティの一意な識別子
- `datasource` — string — 既定値: `nasdaq`。enum: `nasdaq`, `cboe`

### レスポンス

**200** — Object: ローソク足データを正常に返します。

#### レスポンス属性

- `time` — string (date-time) — **必須**
- `open` — number — **必須**
- `high` — number — **必須**
- `low` — number — **必須**
- `close` — number — **必須**

**400** — Object: 必須パラメータがない、またはresolutionが不正です。

**401** — Object: ユーザーに権限がありません。

**500** — Object: サーバー内部エラーです。

---

[← ドキュメント](../../README.md)
