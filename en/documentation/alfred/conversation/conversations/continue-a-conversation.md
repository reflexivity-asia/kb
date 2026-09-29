<!--
id: RX-PRODUCT-1011
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Continue a conversation

[← Documentation](../../../README.md)
Submits a follow-up message to an existing conversation.

### Header Parameters
Authorization string
### Path Parameters
id string Required Conversation ID.

### Body Parameters Expand all
message string Required The user's message. Must be non-empty after trimming whitespace. Send `"continue"` (case-insensitive) to resume a paused conversation.

analysis_mode string Analysis depth used when processing the request.
Send `"Auto"` or omit the field to let the service decide.

Enum values: `None``Quick``Deep``Auto` attachments array File IDs (previously uploaded) to attach to this request.

tools_config object Configuration for the tools available to the agent during a request.

Show child attributes

## Response
200 Object Message submitted successfully.

### Response Attributes
conversation_id string ID of the conversation. Present on creation; omitted on continuation.

name string Name of the conversation. Present on creation; omitted on continuation.

request_id string ID of the submitted request. Present on start/continue; omitted on copy.

400 Object Bad request — invalid request body or too many attachments.

### Response Attributes
message string Human-readable error description.

code string Machine-readable error code.

401 Object Unauthorized.

403 Object Forbidden — question is restricted or permission denied.

### Response Attributes
message string Human-readable error description.

code string Machine-readable error code.

404 Object Conversation not found.

429 Object Too Many Requests — question quota exceeded.

500 Object Internal server error.

## Request and response example

POST

/conversation/v2/{id}

cURL `1 curl --location 'https://api.reflexivity.com/conversation/v2/6054d465-4b2d-437f-9a02-5deca1533253' \ 2 --header 'Authorization: JWT' \ 3 --data '{ 4 "message": "What is the inflation outlook for Q3?", 5 "analysis_mode": "Quick", 6 "attachments": [], 7 "tools_config": { 8 "group_filter": { 9 "policy": "Allow", 10 "groups": [ 11 "web_search", 12 "code_execution" 13 ] 14 }, 15 "parameters": { 16 "web_search": { 17 "max_results": 5 18 } 19 } 20 } 21 }'` Try in API Explorer
### Response
200 400 401 403 404 429 500 `{ "conversation_id" : "conv_01j9abc123" , "name" : "Market outlook Q3" , "request_id" : "req_01j9ghi012" }`
