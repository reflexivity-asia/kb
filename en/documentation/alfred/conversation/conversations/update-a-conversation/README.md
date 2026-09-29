<!--
id: RX-PRODUCT-1012
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a27deeaefde700c1f40686f
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: alfred/conversation/conversations/update-a-conversation
-->
# Update a conversation

Updates the name and/or favourite status of a conversation. At least one field must be provided.

#### Header Parameters

Authorization string
#### Path Parameters

id string Required Conversation ID.

#### Body Parameters

name string New display name (1–1000 characters, leading/trailing whitespace is stripped).

favourite boolean Set to `true` to mark as favourite, `false` to remove.

### Response

204 Object Updated successfully (or nothing to update).

400 Object Bad request — invalid name (empty or exceeds 1000 characters).

401 Object Unauthorized.

403 Object Forbidden.

404 Object Conversation not found.

500 Object Internal server error.

---

[← Documentation](../../../../README.md)
