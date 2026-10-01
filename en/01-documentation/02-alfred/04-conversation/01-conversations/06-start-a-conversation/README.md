<!--
id: RX-PRODUCT-1009
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a27deeaefde700c1f406869
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: alfred/conversation/conversations/start-a-conversation
-->
# Start a conversation

Creates a new conversation and submits the first user message to the code-agent.

#### Header Parameters

Authorization string
#### Body Parameters Expand all

message string Required The user's message. Must be non-empty after trimming whitespace. Send `"continue"` (case-insensitive) to resume a paused conversation.

analysis_mode string Analysis depth used when processing the request.
Send `"Auto"` or omit the field to let the service decide.

Enum values: `None``Quick``Deep``Auto` attachments array File IDs (previously uploaded) to attach to this request.

tools_config object Configuration for the tools available to the agent during a request.

Show child attributes

### Response

201 Object Conversation created successfully.

#### Response Attributes

conversation_id string ID of the conversation. Present on creation; omitted on continuation.

name string Name of the conversation. Present on creation; omitted on continuation.

request_id string ID of the submitted request. Present on start/continue; omitted on copy.

400 Object Bad request — invalid request body or too many attachments.

#### Response Attributes

message string Human-readable error description.

code string Machine-readable error code.

401 Object Unauthorized.

403 Object Forbidden — question is restricted.

#### Response Attributes

message string Human-readable error description.

code string Machine-readable error code.

429 Object Too Many Requests — question quota exceeded.

500 Object Internal server error.

---

[← Documentation](../../../../README.md)
