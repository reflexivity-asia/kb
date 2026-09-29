<!--
id: RX-PRODUCT-1011
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a27deeaefde700c1f40686d
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: alfred/conversation/conversations/continue-a-conversation
-->
# Continue a conversation

Submits a follow-up message to an existing conversation.

#### Header Parameters

Authorization string
#### Path Parameters

id string Required Conversation ID.

#### Body Parameters Expand all

message string Required The user's message. Must be non-empty after trimming whitespace. Send `"continue"` (case-insensitive) to resume a paused conversation.

analysis_mode string Analysis depth used when processing the request.
Send `"Auto"` or omit the field to let the service decide.

Enum values: `None``Quick``Deep``Auto` attachments array File IDs (previously uploaded) to attach to this request.

tools_config object Configuration for the tools available to the agent during a request.

Show child attributes

### Response

200 Object Message submitted successfully.

#### Response Attributes

conversation_id string ID of the conversation. Present on creation; omitted on continuation.

name string Name of the conversation. Present on creation; omitted on continuation.

request_id string ID of the submitted request. Present on start/continue; omitted on copy.

400 Object Bad request — invalid request body or too many attachments.

#### Response Attributes

message string Human-readable error description.

code string Machine-readable error code.

401 Object Unauthorized.

403 Object Forbidden — question is restricted or permission denied.

#### Response Attributes

message string Human-readable error description.

code string Machine-readable error code.

404 Object Conversation not found.

429 Object Too Many Requests — question quota exceeded.

500 Object Internal server error.

---

[← Documentation](../../../../README.md)
