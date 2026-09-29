<!--
id: RX-PRODUCT-1014
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a27deeaefde700c1f406871
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: alfred/conversation/conversations/delete-a-conversation
-->
# Delete a conversation

Permanently deletes the specified conversation.

#### Header Parameters

Authorization string
#### Path Parameters

id string Required Conversation ID.

### Response

204 Object Deleted successfully.

401 Object Unauthorized.

403 Object Forbidden.

500 Object Internal server error.

---

[← Documentation](../../../../README.md)
