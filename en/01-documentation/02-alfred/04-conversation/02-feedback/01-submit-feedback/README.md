<!--
id: RX-PRODUCT-1022
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a27deeaefde700c1f406883
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: alfred/conversation/feedback/submit-feedback
-->
# Submit feedback

Records thumbs-up / thumbs-down feedback for a specific task within a conversation.

#### Header Parameters

Authorization string
#### Body Parameters

conversation_id string Required ID of the conversation.

request_id string Required ID of the task (request) within the conversation.

feedback string Thumbs feedback value.

Enum values: `Neutral``Bad``Good`
### Response

204 Object Feedback recorded.

400 Object Bad request — missing required fields.

401 Object Unauthorized.

---

[← Documentation](../../../../README.md)
