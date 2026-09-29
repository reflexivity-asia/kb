<!--
id: RX-PRODUCT-1041
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Get snake data

[← Documentation](../README.md)

### Body Parameters
snake_expression string date_since integer
## Response Expand all
200 Object Successful response

### Response Attributes
meta object Show child attributes

result object Show child attributes

400 Object Bad request.

404 Object Not found.

500 Object Internal server error.

## Request and response example

POST

/ca/v2/q

cURL `1 curl --location 'https://api.reflexivity.com/ca/v2/q' \ 2 --data '{ 3 "snake_expression": "spx.toggle_leading_indicator", 4 "date_since": 5813313694984116000 5 }'` Try in API Explorer
### Response
200 400 404 500 `{ "meta" : { "snake" : "spx.toggle_leading_indicator" , "entity" : "spx" , "currency" : "USD" , "description" : "" , "latest_date" : "2024-03-21T00:00:00Z" , "latest_price" : -0.0184606646 , "name" : "S&P 500" , "canonical_name" : "spx.toggle_leading_indicator" , "display_format" : "perc" , "ticker" : "$SPX" } , "result" : { "schema" : { "fields" : [ { "name" : "index" , "type" : "datetime" } , { "name" : "value" , "type" : "number" } ] , "primaryKey" : [ "index" ] } , "data" : [ { "index" : "2023-06-28T00:00:00Z" , "value" : 0.1915061499 } , { "index" : "2023-06-29T00:00:00Z" , "value" : 0.2040066041 } , { "index" : "2023-06-30T00:00:00Z" , "value" : 0.1992818478 } , { "index" : "2023-07-03T00:00:00Z" , "value" : 0.062159577 } , { "index" : "2023-07-04T00:00:00Z" , "value" : -0.0052941204 } ] } }` Show more
