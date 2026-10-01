<!--
id: RX-PRODUCT-1036
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
source_id: 6a7468d91ccf0d45acdd18f9
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: current
source_route: alfred/microsoft-integration/services/list-connectable-services
-->

# 接続可能なサービス一覧

**メソッド:** `GET`

**エンドポイント:** `/alfred-integrations/v1/services`

#### ヘッダーパラメータ

- `Authorization-User-Id` — string

### レスポンス

**200** — Object: プロバイダー別にグループ化したサービスカタログを返します。

#### レスポンス属性

- `provider` — string
- `services` — array — 子属性あり

**401** — Object: ユーザーIDが指定されていません。

#### レスポンス属性

- `error` — string — **必須** — 機械判読可能なエラーコード
- `message` — string — 人が読めるメッセージ（任意）
- `details` — string — デバッグ情報（任意）

**500** — Object: サーバー内部エラーです。

#### レスポンス属性

- `error` — string — **必須** — 機械判読可能なエラーコード
- `message` — string — 人が読めるメッセージ（任意）
- `details` — string — デバッグ情報（任意）

---

[← ドキュメント](../../../../README.md)
