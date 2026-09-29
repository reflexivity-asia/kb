<!--
id: RX-PRODUCT-1010
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a27deeaefde700c1f40686b
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: alfred/conversation/conversations/get-tasks-for-a-conversation
-->
# Get tasks for a conversation

Returns the conversation header and a paginated list of tasks (user requests) within it.

#### Header Parameters

Authorization string
#### Query Parameters

page integer Page number (1-indexed, default 1).

Minimum 1 Default value 1 page_size integer Number of items per page (default 10).

Minimum 1 Default value 10
#### Path Parameters

id string Required Conversation ID.

### Response Expand all

200 Object Successfully retrieved tasks.

#### Response Attributes

id string Unique conversation identifier.

name string Display name of the conversation.

summary string Auto-generated summary of the conversation.

access_level string Read-access level of a conversation.

Enum values: `none``private``restricted``public` status string Status of the conversation derived from its last request.

Enum values: `Unspecified``Processing``Done``Error``Cancel``Fatal` favourite boolean Whether the user has marked the conversation as a favourite.

created_date string (date-time) Timestamp when the conversation was created.

date string (date-time) Timestamp of the last update to the conversation.

favourited_at string | null (date-time) Timestamp when the conversation was marked as a favourite. Null if not favourited.

tasks array Show child attributes

400 Object Bad request — invalid pagination parameters.

401 Object Unauthorized.

404 Object Conversation not found.

500 Object Internal server error.

---

[← Documentation](../../../../README.md)
