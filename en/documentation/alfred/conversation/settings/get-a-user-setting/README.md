<!--
id: RX-PRODUCT-1024
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a27deeaefde700c1f406887
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: alfred/conversation/settings/get-a-user-setting
-->
# Get a user setting

Returns the current value of a named user setting.
If the setting has not been explicitly set, the default value is returned.

Known settings:

Name

Description

`preferences.format`

Output format preference prompt (max 30,000 characters).

`tools.websearch`

Allowed web-search source domains (1–50 entries).

#### Header Parameters

Authorization string
#### Path Parameters

name string Required Setting name (e.g. `preferences.format`, `tools.websearch`).

### Response Expand all

200 Object Successfully retrieved setting value.

#### Response Attributes

prompt string sources array Show child attributes

401 Object Unauthorized.

404 Object Setting not found.

500 Object Internal server error.

---

[← Documentation](../../../../README.md)
