<!--
id: RX-PRODUCT-1005
type: product
language: en
locale: en
author: Reflexivity GTM Team
kb_imported: 2026-09-29
status: published
translation_status: canonical
resource: Reflexivity Documentation
-->
# 🧠 Consuming Alfred via Conversation v2

[Alfred](../README.md) · [Documentation](../../README.md)

The Conversation v2 API is the next generation of the Alfred integration, powered by the code-agent backend. It replaces the message/step model with a **task and state-record** model, adds support for file attachments, tool configuration, analysis modes, conversation copying, and per-user settings. This guide walks you through integrating Alfred using the v2 conversation endpoints.

## 🔄 Workflow

The interaction with Alfred via Conversation v2 follows this flow:

1. Send your question to the Start Conversation API — you receive a `conversation_id` and a `request_id`.
2. Receive a notification on the Notifications API when the request has an update. The notification includes `conversation_id` and `request_id`.
3. Poll Get Tasks with the `conversation_id` to retrieve the list of tasks and their summary (first + last state record).
4. Optionally, fetch the full state record chain with Get Task Records for a given `request_id`.
5. Render the output from the final state record.

**NOTE**: Steps 2–5 repeat until the conversation `status` is `Done`, `Error`, `Cancel`, or `Fatal`.

#### Conversation status meanings

| Status | Description |
| --- | --- |
| `Processing` | A request is currently being handled. |
| `Done` | The last request completed successfully. |
| `Cancel` | The last request was cancelled by the user. |
| `Error` | The last request ended with a transient error. The conversation can be recovered by continuing it. |
| `Fatal` | The last request caused an unrecoverable error. A new conversation must be started. |

When `status` is `Error` or `Fatal`, the notification payload includes an error code:

| Error code | Status | Description |
| --- | --- | --- |
| `MAX_ITERATIONS` | `Error` | Maximum code-generation attempts for a request reached. |
| `SERVICE_BUSY` | `Error` | LLM provider was temporarily unavailable. |
| `CONTEXT_LIMIT` | `Fatal` | Conversation exceeds the maximum token limit for the LLM's context window. |
| `REFUSAL` | `Fatal` | LLM refused to complete the request. |

## 📋 Tasks & State Records

A **task** represents a single user request within a conversation — one message sent to Alfred and everything that happened while processing it. A conversation is a sequence of tasks:

```text
Conversation
 └── Task 1  (user: "What is Apple's revenue?")
      └── StateRecord: planning
      └── StateRecord: data_fetch
      └── StateRecord: analysis
      └── StateRecord: output          ← terminal state (next == "")
 └── Task 2  (user: "Compare that to Microsoft")
      └── StateRecord: planning
      └── ...
```

Each task is identified by a `request_id` and contains a summary with:

| Field | Description |
| --- | --- |
| `input` | The user's message (taken from the first state record's output) |
| `output` | Alfred's final answer (taken from the last state record's output) |
| `start_time` | When the request began processing |
| `total_seconds` | Total elapsed time for the request |
| `analysis_mode` | The reasoning depth used (Quick / Deep / None) |
| `attachments` | Files the user attached to this request |
| `first_state` / `last_state` | Bookend state records for quick rendering |

The full reasoning chain lives in **state records** — the individual steps the state machine executed to produce the answer. Use Get Task Records to retrieve the complete ordered list for a task.

A state record with `next === ""` and a non-empty `name` is the **terminal state**, meaning the request is complete.

### v1 vs v2 terminology

In v1 these were called **messages** (with nested **steps**). In v2 the same concept is modelled as **tasks** (with **state records**). The relationship is identical — one user turn = one task = many state records.

## 📝 Output Format

State records carry two key fields:

| Field | Description |
| --- | --- |
| `content_type` | MIME type of the content (e.g. `text/markdown`). Empty when `status` is `No-Content`. |
| `content` | The output produced by this state step. |

Markdown content may contain **component links** — standard markdown links with a recognised component type in the title and a UUID in the href. These links drive client-side visualisations.

### Component Links

```md
[chart](656ac7c9720a4d0ca2c8431e8a63fcb7, "line-chart")
```

Component data is fetched separately — see the Component API below.

## 📊 Analysis Modes

Each request can optionally specify an `analysis_mode`. Only two values are valid in a request:

| Request value | Description |
| --- | --- |
| `"Auto"` (or omit) | Service decides the mode. It will attempt Quick analysis and automatically escalate to Deep if needed. |
| `"Deep"` | Forces full, multi-step quantitative reasoning from the start. |

### Quick in responses

"Quick" is **not** a valid value to send in a request. It may appear in response fields to indicate that the request was resolved with a quick analysis without needing to escalate.

---

## 🛠️ API Reference

### Start a Conversation

Creates a new conversation and submits the user's first message to Alfred.

**Method**: `POST`

**URL**: `https://api.reflexivity.com/conversation/v2`

**Request Schema**:

```json
{
  "message": "string",
  "analysis_mode": "Auto | Deep",
  "attachments": ["file-id"],
  "tools_config": {
    "group_filter": {
      "policy": "None | Block | Allow",
      "groups": ["string"]
    },
    "parameters": {}
  }
}
```

**Response Schema**:

```json
{
  "conversation_id": "string",
  "name": "string",
  "request_id": "string"
}
```

**Error codes**:

| HTTP Status | Code | Description |
| --- | --- | --- |
| 403 | `QUESTION_RESTRICTED` | The question has been restricted by the platform. |
| 400 | `ATTACHMENT_LIMIT_EXCEEDED` | Too many attachments provided. |
| 429 | — | Question quota exceeded. |

### Continue a Conversation

**Method**: `POST`

**URL**: `https://api.reflexivity.com/conversation/v2/{conversationID}`

Send `"continue"` (case-insensitive) as the message to resume a paused conversation.

Response:

```json
{"request_id":"string"}
```

### Get Tasks

**Method**: `GET`

**URL**: `https://api.reflexivity.com/conversation/v2/{conversationID}?page=1&page_size=10`

Returns the conversation header and a paginated list of tasks. Each task contains `request_id`, `start_time`, `total_seconds`, `input`, `output`, optional `analysis_mode`, attachments, and the optional `first_state` / `last_state`.

### Get Task Records

**Method**: `GET`

**URL**: `https://api.reflexivity.com/conversation/v2/{conversationID}/tasks/{requestID}`

Returns `{"states": StateRecord[]}`.

A `StateRecord` contains `id`, `name`, `title`, `start_time`, `duration_seconds`, `total_seconds`, `next`, `status`, `content_type`, `content`, and optional `analysis_mode`.

A state record with `next === ""` and a non-empty `name` is the terminal state.

### Get a Single State Record

**Method**: `GET`

**URL**: `https://api.reflexivity.com/conversation/v2/{conversationID}/records/{recordID}`

Returns a `StateRecord`.

### List Conversations

**Method**: `GET`

**URL**: `https://api.reflexivity.com/conversation/v2?page=1&page_size=10`

Returns a paginated list of the user's private conversations, including fields such as `id`, `name`, `summary`, `access_level`, `status`, favourite fields and `public_copies`.

### Update Conversation

**Method**: `PUT`

**URL**: `https://api.reflexivity.com/conversation/v2/{conversationID}`

At least one of `name` (1–1000 characters) or `favourite` must be supplied.

### Delete Conversation

**Method**: `DELETE`

**URL**: `https://api.reflexivity.com/conversation/v2/{conversationID}`

Permanently deletes a conversation and any public copies.

### Copy Conversation

**Method**: `POST`

**URL**: `https://api.reflexivity.com/conversation/v2/{conversationID}/copy`

Optional request fields: `name` and `access_level` (`none`, `private`, `restricted`, `public`). Returns `conversation_id` and `name`.

### Cancel the Active Task

**Method**: `PUT`

**URL**: `https://api.reflexivity.com/conversation/v2/{conversationID}/tasks`

Request body: `{"action":"cancel"}`.

### Search Conversations

**Method**: `GET`

**URL**: `https://api.reflexivity.com/conversation/v2/search?q={query}&page=1&page_size=10`

Returns matching conversations with `conversation_id`, `request_id`, `name`, `updated_at`, and a representative `state`.

### Feedback

**Method**: `POST`

**URL**: `https://api.reflexivity.com/conversation/v2/feedback`

Request fields: `conversation_id`, `request_id`, and `feedback` (`Neutral`, `Bad`, `Good`).

### User Settings

Supported settings:

| Setting name | Description |
| --- | --- |
| `preferences.format` | Output format preference prompt (max 30,000 characters). |
| `tools.websearch` | Allowed web-search source domains (1–50 entries). |

Get: `GET /conversation/v2/settings/{name}`

Set: `PUT /conversation/v2/settings/{name}`

Delete/reset: `DELETE /conversation/v2/settings/{name}`

### Notifications API

WebSocket URL: `wss://ws.reflexivity.com/v2/notifier`

Notifications contain `conversation_id`, `request_id`, `status`, and an optional `error`. Use the conversation and request IDs to fetch the latest state records.

### Component API

**Method**: `GET`

**URL**: `https://api.reflexivity.com/reasoner-data/v1/{componentID}`

Returns component-specific data used to render visualisations embedded in markdown output, including table payloads and column metadata.

## 🤝 Need Help?

- Help center: [Getting started with Reflexivity](https://support.reflexivity.com/hc/en-us/articles/26906922816404-What-is-Reflexivity)
- Contact: [support@reflexivity.com](mailto:support@reflexivity.com)

---

© 2026 Reflexivity

---

← [Ask question](../ask-question/README.md) · [Conversation](../conversation/README.md) →
