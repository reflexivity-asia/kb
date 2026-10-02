<!--
id: RX-PRODUCT-1022
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Submit feedback

[← Documentation](../../../README.md)
Records thumbs-up / thumbs-down feedback for a specific task within a conversation.

### Header Parameters
Authorization string
### Body Parameters
conversation_id string Required ID of the conversation.

request_id string Required ID of the task (request) within the conversation.

feedback string Thumbs feedback value.

Enum values: `Neutral``Bad``Good`
## Response
204 Object Feedback recorded.

400 Object Bad request — missing required fields.

401 Object Unauthorized.

## Request and response example

POST

/conversation/v2/feedback

cURL `1 curl --location 'https://api.reflexivity.com/conversation/v2/feedback' \ 2 --header 'Authorization: JWT' \ 3 --data '{ 4 "conversation_id": "conv_01j9abc123", 5 "request_id": "req_01j9ghi012", 6 "feedback": "Good" 7 }'` Try in API Explorer
### Response
204 400 401 `Feedback recorded.`
