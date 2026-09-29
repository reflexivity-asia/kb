<!--
id: RX-PRODUCT-1026
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Delete a user setting

[← Documentation](../../../README.md)
Removes a named user setting, reverting it to its default value.

### Header Parameters
Authorization string
### Path Parameters
name string Required Setting name (e.g. `preferences.format`, `tools.websearch`).

## Response
204 Object Setting deleted successfully.

401 Object Unauthorized.

404 Object Setting not found.

500 Object Internal server error.

## Request and response example

DELETE

/conversation/v2/settings/{name}

cURL `1 curl --location --request DELETE 'https://api.reflexivity.com/conversation/v2/settings/preferences.format' \ 2 --header 'Authorization: JWT'` Try in API Explorer
### Response
204 401 404 500 `Setting deleted successfully.`
