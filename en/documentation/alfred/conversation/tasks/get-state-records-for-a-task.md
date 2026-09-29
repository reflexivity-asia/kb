<!--
id: RX-PRODUCT-1017
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Get state records for a task

[← Documentation](../../../README.md)
Returns all state records produced during a specific task (identified by its request ID).

### Header Parameters
Authorization string
### Path Parameters
id string Required Conversation ID.

reqid string Required Request ID of the task.

## Response Expand all
200 Object Successfully retrieved task records.

### Response Attributes
states array Show child attributes

401 Object Unauthorized.

404 Object Conversation or task not found.

500 Object Internal server error.

## Request and response example

GET

/conversation/v2/{id}/tasks/{reqid}

cURL `1 curl --location --globoff 'https://api.reflexivity.com/conversation/v2/conv_01j9abc123/tasks/{reqid}' \ 2 --header 'Authorization: JWT'` Try in API Explorer
### Response
200 401 404 500 `{ "states" : [ { "id" : "rec_01j9xyz789" , "name" : "analysis" , "title" : "Analysing market data" , "start_time" : "2024-09-01T10:01:00Z" , "duration_seconds" : 5 , "total_seconds" : 12 , "next" : "output" , "status" : "OK" , "content_type" : "text/markdown" , "content" : "Based on current data, the Q3 outlook is..." , "analysis_mode" : "Quick" } ] }` Show more
