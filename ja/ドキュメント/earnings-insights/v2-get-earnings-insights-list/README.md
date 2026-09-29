<!--
id: RX-PRODUCT-1050
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f23353e
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: review-needed
source_route: earnings-insights/v2-get-earnings-insights-list
-->

# V2 決算インサイト一覧を取得

**メソッド:** `GET`

**エンドポイント:** `/earnings-insights/v2?type=preview&from=2026-01-01T00:00:00Z&to=2026-12-31T23:59:59Z&page=&page_size=`

企業の基本情報を含む決算インサイトの一覧をページネーション付きで返します。インサイト種別と日付範囲で絞り込めます。

#### クエリパラメータ

- `type` — string — インサイト種別で絞り込みます。enum: `preview`, `recap`
- `from` — string (date-time) — 絞り込み開始日時（含む、RFC3339形式）
- `to` — string (date-time) — 絞り込み終了日時（含む、RFC3339形式）
- `page` — integer — ページ番号。最小値: 1
- `page_size` — integer — 1ページあたりの件数。最小値: 1、最大値: 1000

### レスポンス

**200** — Object: 決算インサイト一覧を正常に返します。

#### レスポンス属性

- `id` — string (uuid)
- `type` — string — enum: `preview`, `recap`
- `title` — string
- `company` — object
- `created_at` — string (date-time)

---

[← ドキュメント](../../README.md)
