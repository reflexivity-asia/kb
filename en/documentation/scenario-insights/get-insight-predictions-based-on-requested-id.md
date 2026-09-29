<!--
id: RX-PRODUCT-1077
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Get scenario insight predictions by ID

[← Documentation](../README.md)

### Path Parameters
id string Required
## Response Expand all
200 Object Return predictions for the requested insight.

### Response Attributes
relative_idx integer horizon string mean number median number count integer percentiles object Show child attributes

high number low number std_dev number min number max number date string (date-time) 404 Object Not found.

500 Object Internal server error.

## Request and response example

GET

/insights/v1/{id}/predictions

cURL `1 curl --location 'https://api.reflexivity.com/insights/v1/8dde260d-5bbd-447a-a04f-c8ea948e600c/predictions' \` Try in API Explorer
### Response
200 404 500 `[ { "relative_idx" : 1 , "horizon" : "8d" , "mean" : 0.056 , "median" : -0.13 , "count" : 13 , "percentiles" : { "10" : -0.3186064501496503 , "20" : -0.2822449827786991 , "30" : -0.25098247887638236 , "40" : -0.1666066589604137 , "60" : -0.04937651612414782 , "70" : -0.01532322426177172 , "80" : 0.03736263736263745 , "90" : 0.11762662624731607 } , "high" : 0.037 , "low" : -0.28 , "std_dev" : 0.72 , "min" : -0.36 , "max" : 2.39 , "date" : "2024-03-19T16:58:00" } ]` Show more
