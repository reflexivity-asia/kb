<!--
id: RX-PRODUCT-1024
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Get a user setting

[← Documentation](../../../README.md)
Returns the current value of a named user setting.
If the setting has not been explicitly set, the default value is returned.

Known settings:

Name

Description

`preferences.format`

Output format preference prompt (max 30,000 characters).

`tools.websearch`

Allowed web-search source domains (1–50 entries).

### Header Parameters
Authorization string
### Path Parameters
name string Required Setting name (e.g. `preferences.format`, `tools.websearch`).

## Response Expand all
200 Object Successfully retrieved setting value.

### Response Attributes
prompt string sources array Show child attributes

401 Object Unauthorized.

404 Object Setting not found.

500 Object Internal server error.

## Request and response example

GET

/conversation/v2/settings/{name}

cURL `1 curl --location 'https://api.reflexivity.com/conversation/v2/settings/preferences.format' \ 2 --header 'Authorization: JWT'` Try in API Explorer
### Response
200 401 404 500 `{ "prompt" : "Always respond in bullet points." , "sources" : [ "bloomberg.com" , "ft.com" ] }`
