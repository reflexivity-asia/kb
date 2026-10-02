<!--
id: RX-PRODUCT-1018
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Get a single state record

[← Documentation](../../../README.md)
Returns a single state record by its ID within a conversation.

### Header Parameters
Authorization string
### Path Parameters
id string Required Conversation ID.

recid string Required State record ID.

## Response
200 Object Successfully retrieved state record.

### Response Attributes
id string Unique record identifier.

name string Name of the state that produced this record.

title string Human-readable title for this state step.

start_time string (date-time) When this state started executing.

duration_seconds integer How long this state took to execute, in seconds.

total_seconds integer Cumulative time from the start of the request to the end of this state, in seconds.

next string Name of the next state to execute. Empty if this is the terminal state.

status string Status of the output produced by a state in the state machine.

Enum values: `None``OK``No-Content``Error``Cancel``Fatal` content_type string MIME type of the `content` field (e.g. `text/markdown`). Empty for `No-Content` status.

content string Output produced by this state. Empty for `No-Content` status.

analysis_mode string Analysis depth used when processing the request.
Send `"Auto"` or omit the field to let the service decide.

Enum values: `None``Quick``Deep``Auto` 401 Object Unauthorized.

404 Object Conversation or record not found.

500 Object Internal server error.

## Request and response example

GET

/conversation/v2/{id}/records/{recid}

cURL `1 curl --location --globoff 'https://api.reflexivity.com/conversation/v2/conv_01j9abc123/records/{recid}' \ 2 --header 'Authorization: JWT'` Try in API Explorer
### Response
200 401 404 500 `{ "id" : "rec_01j9xyz789" , "name" : "analysis" , "title" : "Analysing market data" , "start_time" : "2024-09-01T10:01:00Z" , "duration_seconds" : 5 , "total_seconds" : 12 , "next" : "output" , "status" : "OK" , "content_type" : "text/markdown" , "content" : "Based on current data, the Q3 outlook is..." , "analysis_mode" : "Quick" }` Show more
