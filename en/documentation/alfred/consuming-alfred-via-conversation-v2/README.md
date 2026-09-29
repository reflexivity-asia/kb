<!--
id: RX-PRODUCT-1005
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a27d463d24bb0f7bf1dac73
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: alfred/consuming-alfred-via-conversation-v2
-->
# 🧠 Consuming Alfred via Conversation v2

The Conversation v2 API is the next generation of the Alfred integration, powered by the code-agent backend. It replaces the message/step model with a task and state-record model, adds support for file attachments, tool configuration, analysis modes, conversation copying, and per-user settings. This guide walks you through integrating Alfred using the v2 conversation endpoints.

## 🔄 Workflow

The interaction with Alfred via Conversation v2 follows this flow:

- Send your question to the [Start Conversation API](../../README.md) — you receive a `conversation_id` and a `request_id` .

- Receive a notification on the [Notifications API](../../README.md) when the request has an update. The notification includes `conversation_id` and `request_id` .

- Poll [Get Tasks](../../README.md) with the `conversation_id` to retrieve the list of tasks and their summary (first + last state record).

- Optionally, fetch the full state record chain with [Get Task Records](../../README.md) for a given `request_id` .

- Render the output from the final state record.
NOTE : Steps 2–5 repeat until the conversation `status` is `Done` , `Error` , `Cancel` , or `Fatal` .

#### Conversation status meanings

Title Description Status

Description

`Processing`

A request is currently being handled.

`Done`

The last request completed successfully.

`Cancel`

The last request was cancelled by the user.

`Error`

The last request ended with a transient error. The conversation can be recovered by continuing it.

`Fatal`

The last request caused an unrecoverable error. A new conversation must be started.

When `status` is `Error` or `Fatal` , the notification payload includes an error code:

Title Description Title Error code

Status

Description

`MAX_ITERATIONS`

`Error`

Maximum code-generation attempts for a request reached.

`SERVICE_BUSY`

`Error`

LLM provider was temporarily unavailable.

`CONTEXT_LIMIT`

`Fatal`

Conversation exceeds the maximum token limit for the LLM's context window.

`REFUSAL`

`Fatal`

LLM refused to complete the request.

## 📋 Tasks & State Records

A task represents a single user request within a conversation — one message sent to Alfred and everything that happened while processing it. A conversation is a sequence of tasks:

Plain Text Conversation
└── Task 1 (user: "What is Apple's revenue?")
└── StateRecord: planning
└── StateRecord: data_fetch
└── StateRecord: analysis
└── StateRecord: output ← terminal state (next == "")
└── Task 2 (user: "Compare that to Microsoft")
└── StateRecord: planning
└── ... `Conversation
└── Task 1 (user: "What is Apple's revenue?")
└── StateRecord: planning
└── StateRecord: data_fetch
└── StateRecord: analysis
└── StateRecord: output ← terminal state (next == "")
└── Task 2 (user: "Compare that to Microsoft")
└── StateRecord: planning
└── ...`

Each task is identified by a `request_id` and contains a summary with:

Title Description Field

Description

`input`

The user's message (taken from the first state record's output)

`output`

Alfred's final answer (taken from the last state record's output)

`start_time`

When the request began processing

`total_seconds`

Total elapsed time for the request

`analysis_mode`

The reasoning depth used (Quick / Deep / None)

`attachments`

Files the user attached to this request

`first_state` / `last_state`

Bookend state records for quick rendering

The full reasoning chain lives in state records — the individual steps the state machine executed to produce the answer (e.g. planning → data fetch → code generation → output). Use [Get Task Records](../../README.md) to retrieve the complete ordered list for a task.

A state record with next === "" and a non-empty name is the terminal state , meaning the request is complete.

### v1 vs v2 terminology

In v1 these were called messages (with nested steps ). In v2 the same concept is modelled as tasks (with state records ).
The relationship is identical — one user turn = one task = many state records.

## 📝 Output Format

State records carry two key fields:

Title Description Field

Description

`content_type`

MIME type of the content (e.g. `text/markdown` ). Empty when `status` is `No-Content` .

`content`

The output produced by this state step.

Markdown content may contain component links — standard markdown links with a recognised component type in the title and a UUID in the href. These links drive client-side visualisations.

### Component Links

Markdown `[chart](656ac7c9720a4d0ca2c8431e8a63fcb7, "line-chart")`

#### Supported Component Types

### Show all component types

####

Title Description enum

component

table

table

bar-chart

bar chart

horizontal-bar-chart

horizontal bar chart

line-chart

advanced line chart

apache-area-time

area time

apache-axis-bubble

axis bubble

apache-bar-100

bar 100

apache-bar

bar chart v2

apache-bar-negative

bar chart with negatives

apache-box-whisker

box whisker

apache-bubble

bubble

apache-bubble-time

bubble time

apache-bump

bump chart

apache-candle

candle

apache-candle-bar

candle bar

apache-confidence

confidence

apache-donut

donut

apache-donut-time

donut time

apache-force-graph

force graph

apache-gradient-square

gradient square

apache-grouped-bars

grouped bars

apache-heatmap

heatmap

apache-heatmap-calendar

heatmap calendar

apache-line

basic line chart

apache-line-and-bar

line and bar chart

apache-line-race

line chart race version

apache-sankey

sankey

apache-sankey-vertical

sankey vertical

apache-scatter

scatter

apache-stacked-area

stacked area

apache-stacked-bar-horizontal

stacked bar horizontal

apache-technicals-chart

technicals chart

apache-us-map

US map visualisation

apache-waterfall

waterfall

Component data is fetched separately — see the [Component API](../../README.md).

## 📊 Analysis Modes

Each request can optionally specify an `analysis_mode` . Only two values are valid in a request:

Title Description Request value

Description

`"Auto"` (or omit)

Service decides the mode. It will attempt Quick analysis and automatically escalate to Deep if needed.

`"Deep"`

Forces full, multi-step quantitative reasoning from the start.

### Quick in responses

"Quick" is not a valid value to send in a request. It may appear in response fields (e.g. analysis_mode on a task or state record) to indicate that the request was resolved with a quick analysis without needing to escalate.

---

## 🛠️ API Reference

### Start a Conversation

Creates a new conversation and submits the user's first message to Alfred.

Method : `POST`

URL : `https://api.reflexivity.com/conversation/v2`

Request Schema :

JSON `{
message: string; // User's question (required, non-empty)
analysis_mode?: "Auto" | "Deep"; // Defaults to Auto
attachments?: string[]; // Optional array of previously-uploaded file IDs
tools_config?: {
group_filter?: {
policy: "None" | "Block" | "Allow";
groups: string[]; // Tool group names the policy applies to
};
parameters?: {
[toolName: string]: Record ; // Per-tool parameter overrides
};
};
}` Response Schema :

JSON `{
conversation_id: string; // ID of the newly created conversation
name: string; // Auto-generated conversation name
request_id: string; // ID of the submitted request — use this to poll state records
}`

Error codes :

Title Description Title HTTP Status

Code

Description

403

`QUESTION_RESTRICTED`

The question has been restricted by the platform.

400

`ATTACHMENT_LIMIT_EXCEEDED`

Too many attachments provided.

429

—

Question quota exceeded.

---

### Continue a Conversation

Submits a follow-up message to an existing conversation.

Method : `POST`

URL : `https://api.reflexivity.com/conversation/v2/{conversationID}`

Send `"continue"` (case-insensitive) as the message to resume a paused conversation.

Request Schema : same as [Start a Conversation](../../README.md).

Response Schema :

JSON `{
request_id: string; // ID of the submitted follow-up request
}`

---

### Get Tasks

Returns the conversation header and a paginated list of tasks (user requests). Each task includes a summary with the first and last state record.

Method : `GET`

URL : `https://api.reflexivity.com/conversation/v2/{conversationID}?page=1&page_size=10`

Response Schema :

JSON `{
// Conversation header fields
id: string;
name: string;
summary: string;
access_level: "none" | "private" | "restricted" | "public";
status: "Unspecified" | "Processing" | "Done" | "Error" | "Cancel" | "Fatal";
favourite: boolean;
created_date: string; // ISO 8601 datetime
date: string; // ISO 8601 datetime (last updated)
favourited_at: string | null;

tasks: Array ;
first_state?: StateRecord;
last_state?: StateRecord;
}>;
}
}`

---

### Get Task Records

Returns the full ordered list of state records produced during a specific task. Use this to stream or progressively render Alfred's reasoning steps.

Method : `GET`

URL : `https://api.reflexivity.com/conversation/v2/{conversationID}/tasks/{requestID}`

Response Schema :

JSON `{
states: StateRecord[];
}` Where `StateRecord` is:

JSON `type StateRecord = {
id: string;
name: string; // State machine step name (e.g. "analysis", "output")
title: string; // Human-readable title shown to the user
start_time: string; // ISO 8601 datetime
duration_seconds: number; // How long this step took
total_seconds: number; // Cumulative time from start of request to end of this step
next: string; // Next state name; empty string if this is the terminal state
status: "None" | "OK" | "No-Content" | "Error" | "Cancel" | "Fatal";
content_type: string; // MIME type (e.g. "text/markdown"); empty for No-Content
content: string; // Output text; empty for No-Content
analysis_mode?: "None" | "Quick" | "Deep";
};` A state record with `next === ""` and a non-empty `name` is the terminal state — the request is complete.

---

### Get a Single State Record

Fetches a specific state record by its ID.

Method : `GET`

URL : `https://api.reflexivity.com/conversation/v2/{conversationID}/records/{recordID}`

Response Schema : `StateRecord` (see above).

---

### List Conversations

Returns a paginated list of the user's private conversations. Each conversation may include public copies.

Method : `GET`

URL : `https://api.reflexivity.com/conversation/v2?page=1&page_size=10`

Response Schema :

JSON `{
conversations: Array ; // Public copies of this conversation
}>;
}`
---

### Update Conversation

Updates the display name and/or favourite status of a conversation. At least one field must be provided.

Method : `PUT`

URL : `https://api.reflexivity.com/conversation/v2/{conversationID}`

Request Schema :

JSON `{
name?: string; // 1–1000 characters; leading/trailing whitespace is stripped
favourite?: boolean;
}`
---

### Delete Conversation

Permanently deletes a conversation and any public copies.

Method : `DELETE`

URL : `https://api.reflexivity.com/conversation/v2/{conversationID}`

---

### Copy Conversation

Creates a copy of an existing conversation, optionally with a different access level. Useful for publishing a private conversation as a public shareable copy.

Method : `POST`

URL : `https://api.reflexivity.com/conversation/v2/{conversationID}/copy`

Request Schema :

JSON `{
name?: string; // Defaults to source conversation name
access_level?: "none" | "private" | "restricted" | "public";
}` Response Schema :

JSON `{
conversation_id: string;
name: string;
}`
---

### Cancel the Active Task

Cancels the currently processing request in a conversation.

Method : `PUT`

URL : `https://api.reflexivity.com/conversation/v2/{conversationID}/tasks`

Request Schema :

JSON `{
action: "cancel"; // Only "cancel" is currently supported
}`
---

### Search Conversations

Full-text search across the user's conversations. Returns matching conversations with a representative state record for each result.

Method : `GET`

URL : `https://api.reflexivity.com/conversation/v2/search?q={query}&page=1&page_size=10`

Response Schema :

JSON `{
results: Array ;
}`
---

### Feedback

Records thumbs-up / thumbs-down feedback for a specific task.

Method : `POST`

URL : `https://api.reflexivity.com/conversation/v2/feedback`

Request Schema :

JSON `{
conversation_id: string; // required
request_id: string; // required
feedback: "Neutral" | "Bad" | "Good";
}`
---

### User Settings

Per-user settings allow customisation of Alfred's behaviour. Currently supported settings:

Title Description Setting name

Description

`preferences.format`

Output format preference prompt (max 30,000 characters).

`tools.websearch`

Allowed web-search source domains (1–50 entries).

#### Get a Setting

Method : `GET`

URL : `https://api.reflexivity.com/conversation/v2/settings/{name}`

Response : JSON value of the setting. Example for `preferences.format` :

JSON `{
"prompt": "Always respond in bullet points."
}` Example for `tools.websearch` :

JSON `{
"sources": ["bloomberg.com", "ft.com", "reuters.com"]
}`

#### Set a Setting

Method : `PUT`

URL : `https://api.reflexivity.com/conversation/v2/settings/{name}`

Request Body : JSON value matching the setting's schema (see examples above).

#### Delete a Setting

Reverts the setting to its default value.

Method : `DELETE`

URL : `https://api.reflexivity.com/conversation/v2/settings/{name}`

---

### Notifications API

A WebSocket API that broadcasts real-time updates when a request has new output.

URL : `wss://ws.reflexivity.com/v2/notifier`

Message Response Schema :

JSON `{
event: {
type: "alfred";
};
metadata: {
conversation_id: string;
payload: {
request_id: string;
status: "Processing" | "Done" | "Error" | "Cancel" | "Fatal";
error?: string; // Present only when status is "Error" or "Fatal"
};
};
}` On receiving a notification, use `conversation_id` and `request_id` to fetch the latest state records via [Get Task Records](../../README.md).

---

### Component API

Fetches the data required to render a visualisation component embedded in markdown output.

Method : `GET`

URL : `https://api.reflexivity.com/reasoner-data/v1/{componentID}`

Response Schema (Table) :

JSON `type TableData = { value: string; tooltip?: string; logo?: string };
type TableRow = Record ;
type ColumnsType = "text" | "directional" | "number";
type TableColumns = {
type: ColumnsType;
sticky?: boolean;
tooltip?: string;
id: T;
title: string;
};
type TableV2Payload = {
data: TableRow [];
stickyHeader?: boolean;
columnsMeta: TableColumns [];
pagination?: {
itemsPerPage?: number;
strategy?: "scroll" | "buttons";
};
};`

## 🤝 Need Help?

If you need assistance with the Alfred API or have questions about Reflexivity's platform:

- Visit our help center: [Getting started with Reflexivity](https://support.reflexivity.com/hc/en-us/articles/26906922816404-What-is-Reflexivity)

- Contact Us: [support@reflexivity.com](mailto:support@reflexivity.com)

---
© 2026 Reflexivity

---

[← Documentation](../../README.md)
