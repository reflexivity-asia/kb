<!--
id: RX-PRODUCT-1073
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# 🧲 Company → Company (Proximity)

[← Documentation](../../README.md)

### Body Parameters
entity string the entity tag

## Response
200 Object Successful request

### Response Attributes
googl_nasd string snap_nyse string 400 Object Bad request

500 Object Something went wrong!

## Request and response example

POST

/kg/v1/connected-entities/proximity

cURL `1 curl --location 'https://api.reflexivity.com/kg/v1/connected-entities/proximity' \ 2 --data '{ 3 "entity": "amzn_nasd" 4 }'` Try in API Explorer
### Response
200 400 500 `[ "googl_nasd" , "snap_nyse" ]`
