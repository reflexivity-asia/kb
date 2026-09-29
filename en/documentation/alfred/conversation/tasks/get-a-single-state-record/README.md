<!--
id: RX-PRODUCT-1018
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a27deeaefde700c1f40687b
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: alfred/conversation/tasks/get-a-single-state-record
-->
# Get a single state record

Returns a single state record by its ID within a conversation.

#### Header Parameters

Authorization string
#### Path Parameters

id string Required Conversation ID.

recid string Required State record ID.

### Response

200 Object Successfully retrieved state record.

#### Response Attributes

id string Unique record identifier.

name string Name of the state that produced this record.

title string Human-readable title for this state step.

start_time string (date-time) When this state started executing.

duration_seconds integer How long this state took to execute, in seconds.

total_seconds integer Cumulative time from the start of the request to the end of this state, in seconds.

next string Name of the next state to execute. Empty if this is the terminal state.

status string Status of the output produced by a state in the state machine.

Enum values: `None``OK``No-Content``Error``Cancel``Fatal` content_type string MIME type of the `content` field (e.g. `text/markdown`). Empty for `No-Content` status.

content string Output produced by this state. Empty for `No-Content` status.

analysis_mode string Analysis depth used when processing the request.
Send `"Auto"` or omit the field to let the service decide.

Enum values: `None``Quick``Deep``Auto` 401 Object Unauthorized.

404 Object Conversation or record not found.

500 Object Internal server error.

---

[← Documentation](../../../../README.md)
