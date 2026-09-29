<!--
id: RX-PRODUCT-1014
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Delete a conversation

[← Documentation](../../../README.md)
Permanently deletes the specified conversation.

### Header Parameters
Authorization string
### Path Parameters
id string Required Conversation ID.

## Response
204 Object Deleted successfully.

401 Object Unauthorized.

403 Object Forbidden.

500 Object Internal server error.

## Request and response example

DELETE

/conversation/v2/{id}

cURL `1 curl --location --request DELETE 'https://api.reflexivity.com/conversation/v2/conv_01j9abc123' \ 2 --header 'Authorization: JWT' \` Try in API Explorer
### Response
204 401 403 500 `Deleted successfully.`
