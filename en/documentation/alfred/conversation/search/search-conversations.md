<!--
id: RX-PRODUCT-1020
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Search conversations

[← Documentation](../../../README.md)
Full-text search across the user's conversations. Returns matching conversations with a representative state record for each result.

### Header Parameters
Authorization string
### Query Parameters
q string Required Search query string.

page integer Page number (1-indexed, default 1).

Minimum 1 Default value 1 page_size integer Number of items per page (default 10).

Minimum 1 Default value 10
## Response Expand all
200 Object Successfully retrieved search results.

### Response Attributes
results array Show child attributes

400 Object Bad request — invalid pagination parameters.

401 Object Unauthorized.

500 Object Internal server error.

## Request and response example

GET

/conversation/v2/search?q=inflation outlook&page=1&page_size=10

cURL `1 curl --location 'https://api.reflexivity.com/conversation/v2/search?q=inflation%20outlook&page=1&page_size=10' \ 2 --header 'Authorization: JWT'` Try in API Explorer
### Response
200 400 401 500 `{ "results" : [ { "conversation_id" : "conv_01j9abc123" , "request_id" : "req_01j9ghi012" , "name" : "Market outlook Q3" , "updated_at" : "2024-09-01T11:30:00Z" , "state" : { "id" : "rec_01j9xyz789" , "name" : "analysis" , "title" : "Analysing market data" , "start_time" : "2024-09-01T10:01:00Z" , "duration_seconds" : 5 , "total_seconds" : 12 , "next" : "output" , "status" : "OK" , "content_type" : "text/markdown" , "content" : "Based on current data, the Q3 outlook is..." , "analysis_mode" : "Quick" } } ] }` Show more
