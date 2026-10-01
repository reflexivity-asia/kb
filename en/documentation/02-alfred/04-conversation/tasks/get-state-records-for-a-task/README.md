<!--
id: RX-PRODUCT-1017
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a27deeaefde700c1f406879
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: alfred/conversation/tasks/get-state-records-for-a-task
-->
# Get state records for a task

Returns all state records produced during a specific task (identified by its request ID).

#### Header Parameters

Authorization string
#### Path Parameters

id string Required Conversation ID.

reqid string Required Request ID of the task.

### Response Expand all

200 Object Successfully retrieved task records.

#### Response Attributes

states array Show child attributes

401 Object Unauthorized.

404 Object Conversation or task not found.

500 Object Internal server error.

---

[← Documentation](../../../../README.md)
