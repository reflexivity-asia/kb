<!--
id: RX-PRODUCT-1004
type: product
language: en
locale: en
author: Reflexivity GTM Team
kb_imported: 2026-09-29
status: published
translation_status: canonical
resource: Reflexivity Documentation
-->
# Ask question

[Alfred](../README.md) · [Documentation](../../README.md)

**Method:** `POST`

Returns streamed event response from the assistants.

#### Body Parameters

`question` — `string` — **Required**

The question to ask Alfred.

`ancillary` — `object`

Additional information to help Alfred answer the question.

`session_id` — `string` — **Required**

The session id.

`target` — `string`

Specifies target assistant.

### Response

**200** — Object: Alfred API status.

#### Response Attributes

`source` — `string`

The source of the streamed event. It specifies the assistant that generated the event.

`event` — `string`

The event type.

`data` — `object`

The data received from the assistant.

`request_id` — `string`

The request id.

**400** — Object: Bad request.

**500** — Object: Internal error.

**Endpoint:** `POST /alfred/v1`

## Request example

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

## Response example

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

← [🧠 Consuming Alfred v1](../consuming-alfred/README.md) · [🧠 Consuming Alfred via Conversation v2](../consuming-alfred-via-conversation-v2/README.md) →
