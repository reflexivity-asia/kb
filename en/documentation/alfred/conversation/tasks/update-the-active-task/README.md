<!--
id: RX-PRODUCT-1016
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a27deeaefde700c1f406877
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: alfred/conversation/tasks/update-the-active-task
-->
# Update the active task

Updates the currently processing task within a conversation.
Currently the only supported action is `cancel`, which aborts the in-flight request.

#### Header Parameters

Authorization string
#### Path Parameters

id string Required Conversation ID.

#### Body Parameters

action string The action to perform. Currently only `"cancel"` is supported.

Enum values: `cancel`
### Response

204 Object Action applied (or action was a no-op).

400 Object Bad request — invalid request body.

401 Object Unauthorized.

403 Object Forbidden.

404 Object Conversation not found.

500 Object Internal server error.

---

[← Documentation](../../../../README.md)
