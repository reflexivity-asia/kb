<!--
id: RX-PRODUCT-1079
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
source_id: 6a269e4a0d17aeec4a2faa81
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: review-needed
source_route: price-history/get-prices
-->

# 価格履歴を取得

**メソッド:** `GET`

**エンドポイント:** `/price-history/v1/prices?ticker=STLA&entity_tag=stla_nyse&resolution=1D&from=2018-03-13T18:53:00Z&to=2020-03-19T16:58:00Z&datasource=nasdaq`

指定したパラメータに基づいて価格データの一覧を返します。

#### クエリパラメータ

- `ticker` — string — **必須** — 証券のsubscribable ticker
- `entity_tag` — string — **必須** — エンティティの一意な識別子
- `resolution` — string — 既定値: `1m`
- `from` — string (date-time) — 取得開始日時。省略すると利用可能な最初のデータポイントから返します。
- `to` — string (date-time) — 取得終了日時。省略すると利用可能な最後のデータポイントまで返します。
- `datasource` — string — 既定値: `nasdaq`。enum: `nasdaq`, `cboe`

### レスポンス

**200** — Object: ローソク足データを正常に返します。

#### レスポンス属性

- `time` — string (date-time) — **必須** — ローソク足のタイムスタンプ
- `open` — number — **必須**
- `high` — number — **必須**
- `low` — number — **必須**
- `close` — number — **必須**

**400** — Object: 必須パラメータがない、またはresolutionが不正です。

**401** — Object: ユーザーに権限がありません。

**500** — Object: サーバー内部エラーです。

---

[← ドキュメント](../../README.md)
