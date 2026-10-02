<!--
id: RX-PRODUCT-1010
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Get tasks for a conversation

[← Documentation](../../../README.md)
Returns the conversation header and a paginated list of tasks (user requests) within it.

### Header Parameters
Authorization string
### Query Parameters
page integer Page number (1-indexed, default 1).

Minimum 1 Default value 1 page_size integer Number of items per page (default 10).

Minimum 1 Default value 10
### Path Parameters
id string Required Conversation ID.

## Response Expand all
200 Object Successfully retrieved tasks.

### Response Attributes
id string Unique conversation identifier.

name string Display name of the conversation.

summary string Auto-generated summary of the conversation.

access_level string Read-access level of a conversation.

Enum values: `none``private``restricted``public` status string Status of the conversation derived from its last request.

Enum values: `Unspecified``Processing``Done``Error``Cancel``Fatal` favourite boolean Whether the user has marked the conversation as a favourite.

created_date string (date-time) Timestamp when the conversation was created.

date string (date-time) Timestamp of the last update to the conversation.

favourited_at string | null (date-time) Timestamp when the conversation was marked as a favourite. Null if not favourited.

tasks array Show child attributes

400 Object Bad request — invalid pagination parameters.

401 Object Unauthorized.

404 Object Conversation not found.

500 Object Internal server error.

## Request and response example

GET

/conversation/v2/{id}?page=1&page_size=10

cURL `1 curl --location 'https://api.reflexivity.com/conversation/v2/6054d465-4b2d-437f-9a02-5deca1533253?page=1&page_size=10' \ 2 --header 'Authorization: JWT' \` Try in API Explorer
### Response
200 400 401 404 500 `{ "id" : "conv_01j9abc123" , "name" : "Market outlook Q3" , "summary" : "Discussion about Q3 market trends and inflation." , "access_level" : "private" , "status" : "Done" , "favourite" : false , "created_date" : "2024-09-01T10:00:00Z" , "date" : "2024-09-01T11:30:00Z" , "favourited_at" : "" , "tasks" : [ { "request_id" : "req_01j9ghi012" , "start_time" : "2024-09-01T10:01:00Z" , "total_seconds" : 30 , "input" : "What is the inflation outlook for Q3?" , "output" : "Based on current data, inflation is expected to..." , "first_state" : { "id" : "rec_01j9xyz789" , "name" : "analysis" , "title" : "Analysing market data" , "start_time" : "2024-09-01T10:01:00Z" , "duration_seconds" : 5 , "total_seconds" : 12 , "next" : "output" , "status" : "OK" , "content_type" : "text/markdown" , "content" : "Based on current data, the Q3 outlook is..." , "analysis_mode" : "Quick" } , "last_state" : { "id" : "rec_01j9xyz789" , "name" : "analysis" , "title" : "Analysing market data" , "start_time" : "2024-09-01T10:01:00Z" , "duration_seconds" : 5 , "total_seconds" : 12 , "next" : "output" , "status" : "OK" , "content_type" : "text/markdown" , "content" : "Based on current data, the Q3 outlook is..." , "analysis_mode" : "Quick" } , "analysis_mode" : "Quick" , "attachments" : [ { "file_id" : "file_01j9def456" , "file_name" : "report.pdf" , "size" : 204800 , "content_type" : "application/pdf" } ] } ] }` Show more
