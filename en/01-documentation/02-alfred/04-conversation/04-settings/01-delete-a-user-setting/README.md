<!--
id: RX-PRODUCT-1026
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a27deeaefde700c1f40688b
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: alfred/conversation/settings/delete-a-user-setting
-->
# Delete a user setting

Removes a named user setting, reverting it to its default value.

#### Header Parameters

Authorization string
#### Path Parameters

name string Required Setting name (e.g. `preferences.format`, `tools.websearch`).

### Response

204 Object Setting deleted successfully.

401 Object Unauthorized.

404 Object Setting not found.

500 Object Internal server error.

---

[← Documentation](../../../../README.md)
