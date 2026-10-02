<!--
id: RX-PRODUCT-1042
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Get theme performance

[← Documentation](../README.md)
Returns the aggregate performance time series for the specified theme and period. It also includes the entities used in the calculation.

### Body Parameters
theme_id string Required Theme identifier.

period string Required Period for performance calculation (e.g., "1D", "1W", "1M", "3M", "6M", "1Y").

## Response Expand all
200 Object Successful response

### Response Attributes
entities array Show child attributes

aggregate array Show child attributes

request object Show child attributes

response object Show child attributes

400 Object Bad request.

404 Object Not found.

500 Object Internal server error.

## Request and response example

POST

/calculator/v1/theme-performance

cURL `1 curl --location 'https://api.reflexivity.com/calculator/v1/theme-performance' \ 2 --data '{ 3 "theme_id": "69d9c830-3a7b-41b6-a796-746539839d1a", 4 "period": "1W" 5 }'` Try in API Explorer
### Response
200 400 404 500 `{ "entities" : [ "" ] , "aggregate" : [ { "index" : "2025-06-03T00:00:00Z" , "value" : 0.01348089256670848 } ] , "request" : { "theme_id" : "b7e6e2c2-1f2a-4c3b-9e7d-2a4b6e2c2f1a" , "period" : "1M" } , "response" : { "entities" : [ "msft_nasd" , "aapl_nasd" ] , "aggregate" : [ { "index" : "2025-06-03T00:00:00Z" , "value" : 0 } , { "index" : "2025-06-04T00:00:00Z" , "value" : 0.12 } , { "index" : "2025-06-05T00:00:00Z" , "value" : 0.18 } , { "index" : "2025-06-06T00:00:00Z" , "value" : 0.22 } , { "index" : "2025-06-07T00:00:00Z" , "value" : 0.19 } , { "index" : "2025-06-10T00:00:00Z" , "value" : 0.25 } ] } }` Show more
