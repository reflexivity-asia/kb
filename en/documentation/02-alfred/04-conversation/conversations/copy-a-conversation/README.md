<!--
id: RX-PRODUCT-1013
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a27deeaefde700c1f406873
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: alfred/conversation/conversations/copy-a-conversation
-->
# Copy a conversation

Creates a copy of an existing conversation with a new access level. Can be used to publish a private conversation as a public copy.

#### Header Parameters

Authorization string
#### Path Parameters

id string Required Conversation ID.

#### Body Parameters

name string Display name for the copy (1–1000 characters). Defaults to the source conversation's name if omitted.

access_level string Read-access level of a conversation.

Enum values: `none``private``restricted``public`
### Response

201 Object Copy created successfully.

#### Response Attributes

conversation_id string ID of the conversation. Present on creation; omitted on continuation.

name string Name of the conversation. Present on creation; omitted on continuation.

request_id string ID of the submitted request. Present on start/continue; omitted on copy.

400 Object Bad request — invalid name.

401 Object Unauthorized.

404 Object Source conversation not found.

409 Object Conflict — permission denied (copy already exists or access conflict).

500 Object Internal server error.

---

[← Documentation](../../../../README.md)
