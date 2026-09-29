<!--
id: RX-PRODUCT-1012
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Update a conversation

[← Documentation](../../../README.md)
Updates the name and/or favourite status of a conversation. At least one field must be provided.

### Header Parameters
Authorization string
### Path Parameters
id string Required Conversation ID.

### Body Parameters
name string New display name (1–1000 characters, leading/trailing whitespace is stripped).

favourite boolean Set to `true` to mark as favourite, `false` to remove.

## Response
204 Object Updated successfully (or nothing to update).

400 Object Bad request — invalid name (empty or exceeds 1000 characters).

401 Object Unauthorized.

403 Object Forbidden.

404 Object Conversation not found.

500 Object Internal server error.

## Request and response example

PUT

/conversation/v2/{id}

cURL `1 curl --location --request PUT 'https://api.reflexivity.com/conversation/v2/6054d465-4b2d-437f-9a02-5deca1533253' \ 2 --header 'Authorization: JWT' \ 3 --data '{ 4 "name": "Updated market analysis", 5 "favourite": true 6 }'` Try in API Explorer
### Response
204 400 401 403 404 500 `Updated successfully (or nothing to update).`
