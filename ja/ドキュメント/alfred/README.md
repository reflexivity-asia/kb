<!--
id: RX-PRODUCT-1002
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f23352e
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: current
source_route: alfred
-->
# Alfred

Alfredを使うと、アプリケーションからユーザーの質問をアシスタントサービスに送信し、関連メタデータとともに生成された回答を受け取れます。ユーザーの質問、セッションコンテキスト、必要に応じたルーティング情報をバックエンドのアシスタントサービスへ送る、チャット形式のワークフローに利用できます。

Alfredは、一般知識に関する質問と、特定のアシスタントを指定した質問の両方に対応します。

## ベースパス

`/alfred/v1`

## はじめに

[Alfred v1 を利用する](consuming-alfred/README.md)

- エンドポイントを呼び出す前に、Alfredのリクエストフロー、セッションの動作、ターゲットのルーティング、ストリーミングされるメタデータの扱いを確認してください。

## エンドポイント

[質問する](ask-question/README.md): `POST /alfred/v1`

- セッションコンテキスト付きでユーザーの質問を送信します。特定のアシスタントに処理させる場合は、リクエストにルーティング情報を含めることができます。

一般知識への質問: `POST /alfred/v1/general-knowledge`

- 専門アシスタントへのルーティングを必要としない一般知識の質問を送信します。

## 補足

- リクエストにはセッションコンテキストを含めることができ、会話を特定のユーザー操作に関連付けられます。
- 特定のアシスタントに質問をルーティングする場合は `target` フィールドを指定できます。
- レスポンスには、クライアントアプリケーションで処理・表示できるメタデータイベントが含まれる場合があります。

---

[← ドキュメント](../README.md)
