<!--
id: RX-PRODUCT-1025
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Set a user setting

[← Documentation](../../../README.md)
Creates or replaces a named user setting. The request body must be a valid JSON value matching the setting's schema.

### Header Parameters
Authorization string
### Path Parameters
name string Required Setting name (e.g. `preferences.format`, `tools.websearch`).

### Body Parameters
prompt string
## Response
204 Object Setting saved successfully.

400 Object Bad request — unrecognized setting or invalid value.

401 Object Unauthorized.

500 Object Internal server error.

## Request and response example

PUT

/conversation/v2/settings/{name}

cURL `1 curl --location --request PUT 'https://api.reflexivity.com/conversation/v2/settings/preferences.format' \ 2 --header 'Authorization: JWT' \ 3 --data '{ 4 "prompt": "Always respond in bullet points." 5 }'` Try in API Explorer
### Response
204 400 401 500 `Setting saved successfully.`
