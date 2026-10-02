<!--
id: RX-PRODUCT-1013
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Copy a conversation

[← Documentation](../../../README.md)
Creates a copy of an existing conversation with a new access level. Can be used to publish a private conversation as a public copy.

### Header Parameters
Authorization string
### Path Parameters
id string Required Conversation ID.

### Body Parameters
name string Display name for the copy (1–1000 characters). Defaults to the source conversation's name if omitted.

access_level string Read-access level of a conversation.

Enum values: `none``private``restricted``public`
## Response
201 Object Copy created successfully.

### Response Attributes
conversation_id string ID of the conversation. Present on creation; omitted on continuation.

name string Name of the conversation. Present on creation; omitted on continuation.

request_id string ID of the submitted request. Present on start/continue; omitted on copy.

400 Object Bad request — invalid name.

401 Object Unauthorized.

404 Object Source conversation not found.

409 Object Conflict — permission denied (copy already exists or access conflict).

500 Object Internal server error.

## Request and response example

POST

/conversation/v2/{id}/copy

cURL `1 curl --location 'https://api.reflexivity.com/conversation/v2/6054d465-4b2d-437f-9a02-5deca1533253/copy' \ 2 --header 'Authorization: JWT' \ 3 --data '{ 4 "name": "Public copy of market outlook", 5 "access_level": "private" 6 }'` Try in API Explorer
### Response
201 400 401 404 409 500 `{ "conversation_id" : "conv_01j9abc123" , "name" : "Market outlook Q3" , "request_id" : "req_01j9ghi012" }`
