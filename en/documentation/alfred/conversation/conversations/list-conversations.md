<!--
id: RX-PRODUCT-1008
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# List conversations

[← Documentation](../../../README.md)
Returns a paginated list of the authenticated user's private conversations, each with its public copies nested.

### Header Parameters
Authorization string
### Query Parameters
page integer Page number (1-indexed, default 1).

Minimum 1 Default value 1 page_size integer Number of items per page (default 10).

Minimum 1 Default value 10
## Response Expand all
200 Object Successfully retrieved conversations.

### Response Attributes
conversations array Show child attributes

400 Object Bad request — invalid pagination parameters.

401 Object Unauthorized.

500 Object Internal server error.

## Request and response example

GET

/conversation/v2?page=1&page_size=10

cURL `1 curl --location 'https://api.reflexivity.com/conversation/v2?page=1&page_size=10' \ 2 --header 'Authorization: JWT' \` Try in API Explorer
### Response
200 400 401 500 `{ "conversations" : [ { "id" : "conv_01j9abc123" , "name" : "Market outlook Q3" , "summary" : "Discussion about Q3 market trends." , "access_level" : "private" , "status" : "Done" , "favourite" : false , "created_date" : "2024-09-01T10:00:00Z" , "date" : "2024-09-01T11:30:00Z" , "favourited_at" : "" , "public_copies" : [ { "id" : "conv_01j9abc123" , "name" : "Market outlook Q3" , "summary" : "Discussion about Q3 market trends and inflation." , "access_level" : "private" , "status" : "Done" , "favourite" : false , "created_date" : "2024-09-01T10:00:00Z" , "date" : "2024-09-01T11:30:00Z" , "favourited_at" : "" } ] } ] }` Show more
