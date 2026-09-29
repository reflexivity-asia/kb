<!--
id: RX-PRODUCT-1004
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
kb_imported: 2026-09-29
status: published
translation_status: current
resource: Reflexivity Documentation
-->
# 質問する

[Alfred](../README.md) · [ドキュメント](../../README.md)

**メソッド:** `POST`

各アシスタントからのイベントをストリーミング形式で返します。

#### Body Parameters

`question` — `string` — **必須**

Alfredに送る質問です。

`ancillary` — `object`

Alfredが回答するための追加情報です。

`session_id` — `string` — **必須**

セッションIDです。

`target` — `string`

対象のアシスタントを指定します。

### レスポンス

**200** — Object: Alfred APIの状態。

#### Response Attributes

`source` — `string`

ストリーミングイベントの送信元。イベントを生成したアシスタントを示します。

`event` — `string`

イベント種別です。

`data` — `object`

アシスタントから受け取ったデータです。

`request_id` — `string`

リクエストIDです。

**400** — Object: 不正なリクエスト。

**500** — Object: 内部エラー。

**Endpoint:** `POST /alfred/v1`

## リクエスト例

```bash
curl --location 'https://api.reflexivity.com/alfred/v1' \
--data '{
  "question": "How did Tesla perform in the last quarter?",
  "ancillary": {
    "documents": [
      "23a2b674-999a-4be2-ae59-f793b2554154",
      "9a8ff2d8-1208-4b49-9452-21cd21422dae"
    ]
  },
  "session_id": "API_Explorer_session",
  "target": "document-assistant"
}'
```

## レスポンス例

```json
{
  "source": "document-assistant",
  "event": "Metadata",
  "data": {
    "citation_group_id": "123",
    "document_ids": [
      "9a8ff2d8-1208-4b49-9452-21cd21422dae"
    ],
    "message": "Tesla's performance in the last quarter (Q4 2024) showed mixed results...",
    "overview": {
      "companies": 1,
      "document_types": {
        "document_types": {
          "Presentation": {
            "count": 2,
            "relevance": 0.6865049494405595
          },
          "Transcript": {
            "count": 2,
            "relevance": 0.7023648825
          }
        }
      }
    }
  },
  "request_id": "123"
}
```

---

← [🧠 Alfred v1 を利用する](../consuming-alfred/README.md) · [🧠 Conversation v2 経由でAlfredを利用する](../consuming-alfred-via-conversation-v2/README.md) →
