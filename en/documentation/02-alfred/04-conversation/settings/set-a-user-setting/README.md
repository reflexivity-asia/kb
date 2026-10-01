<!--
id: RX-PRODUCT-1025
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a27deeaefde700c1f406889
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: alfred/conversation/settings/set-a-user-setting
-->
# Set a user setting

Creates or replaces a named user setting. The request body must be a valid JSON value matching the setting's schema.

#### Header Parameters

Authorization string
#### Path Parameters

name string Required Setting name (e.g. `preferences.format`, `tools.websearch`).

#### Body Parameters

prompt string
### Response

204 Object Setting saved successfully.

400 Object Bad request — unrecognized setting or invalid value.

401 Object Unauthorized.

500 Object Internal server error.

---

[← Documentation](../../../../README.md)
