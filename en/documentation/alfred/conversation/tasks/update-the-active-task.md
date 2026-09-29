<!--
id: RX-PRODUCT-1016
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Update the active task

[← Documentation](../../../README.md)
Updates the currently processing task within a conversation.
Currently the only supported action is `cancel`, which aborts the in-flight request.

### Header Parameters
Authorization string
### Path Parameters
id string Required Conversation ID.

### Body Parameters
action string The action to perform. Currently only `"cancel"` is supported.

Enum values: `cancel`
## Response
204 Object Action applied (or action was a no-op).

400 Object Bad request — invalid request body.

401 Object Unauthorized.

403 Object Forbidden.

404 Object Conversation not found.

500 Object Internal server error.

## Request and response example

PUT

/conversation/v2/{id}/tasks

cURL `1 curl --location --request PUT 'https://api.reflexivity.com/conversation/v2/conv_01j9abc123/tasks' \ 2 --header 'Authorization: JWT' \ 3 --data '{ 4 "action": "cancel" 5 }'` Try in API Explorer
### Response
204 400 401 403 404 500 `Action applied (or action was a no-op).`
