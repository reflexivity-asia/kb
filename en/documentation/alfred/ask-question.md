<!--
id: RX-PRODUCT-1004
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Ask question

[← Documentation](../README.md)
Returns streamed event response from the assistants.

### Body Parameters Expand all
question string Required The question to ask Alfred.

ancillary object Additional information to help Alfred answer the question.

Show child attributes

session_id string Required The session id.

target string Specifies target assistant.

## Response Expand all
200 Object Alfred API status.

### Response Attributes
source string The source of the streamed event. It specifies the assistant that generated the event.

event string The event type.

data object The data received from the assistant.

Show child attributes

request_id string The request id.

400 Object Bad request.

500 Object Internal error.

## Request and response example

POST

/alfred/v1

cURL `1 curl --location 'https://api.reflexivity.com/alfred/v1' \ 2 --data '{ 3 "question": "How did Tesla perform in the last quarter?", 4 "ancillary": { 5 "documents": [ 6 "23a2b674-999a-4be2-ae59-f793b2554154", 7 "9a8ff2d8-1208-4b49-9452-21cd21422dae" 8 ] 9 }, 10 "session_id": "API_Explorer_session", 11 "target": "document-assistant" 12 }'` Try in API Explorer
### Response
200 400 500 `{ "source" : "document-assistant" , "event" : "Metadata" , "data" : { "citation_group_id" : "123" , "document_ids" : [ "9a8ff2d8-1208-4b49-9452-21cd21422dae" ] , "message" : "Tesla's performance in the last quarter (Q4 2024) showed mixed results..." , "overview" : { "companies" : 1 , "document_types" : { "document_types" : { "Presentation" : { "count" : 2 , "relevance" : 0.6865049494405595 } , "Transcript" : { "count" : 2 , "relevance" : 0.7023648825 } } } } } , "request_id" : "123" }` Show more
