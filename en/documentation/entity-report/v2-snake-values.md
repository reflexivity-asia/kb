<!--
id: RX-PRODUCT-1063
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# V2 Snake Values

[← Documentation](../README.md)
Retrieves the latest snake values for a given entity tag. If a snake is not found it is
omitted from the returned object, if no snakes are found an empty object is returned.

Title Description JSON Key

Mapping

mom(horiz=1d)

1D return

mom(horiz=1w)

1W return

mom(horiz=1m)

1M return

mom(horiz=3m)

3M return

mom(horiz=6m)

6M return

mom(horiz=12m)

1Y return

pe ibes forward_12m

P/E (forward)

pe ibes trailing_12m

P/E (trailing)

price_rsi(horiz=14d)

RSI

### Path Parameters
entity_tag string Required The unique identifier for an entity.

## Response Expand all
200 Object OK

### Response Attributes
mom(horiz=12m) object Show child attributes

mom(horiz=1d) object Show child attributes

mom(horiz=1m) object Show child attributes

mom(horiz=1w) object Show child attributes

mom(horiz=3m) object Show child attributes

mom(horiz=6m) object Show child attributes

pe_ibes_forward_12m object Show child attributes

pe_ibes_trailing_12m object Show child attributes

price_rsi(horiz=14d) object Show child attributes

400 Object Invalid entity tag

## Request and response example

GET

/entity-report/v2/entity/{entity_tag}/latest-values

cURL `1 curl --location 'https://api.reflexivity.com/entity-report/v2/entity/tsla_nasd/latest-values' \` Try in API Explorer
### Response
200 400 `{ "mom(horiz=12m)" : { "item" : { "last_value" : null , "last_value_formatted" : "" , "last_update" : "" } } , "mom(horiz=1d)" : { "item" : { "last_value" : null , "last_value_formatted" : "" , "last_update" : "" } } , "mom(horiz=1m)" : { "item" : { "last_value" : null , "last_value_formatted" : "" , "last_update" : "" } } , "mom(horiz=1w)" : { "item" : { "last_value" : null , "last_value_formatted" : "" , "last_update" : "" } } , "mom(horiz=3m)" : { "item" : { "last_value" : null , "last_value_formatted" : "" , "last_update" : "" } } , "mom(horiz=6m)" : { "item" : { "last_value" : null , "last_value_formatted" : "" , "last_update" : "" } } , "pe_ibes_forward_12m" : { "item" : { "last_value" : null , "last_value_formatted" : "" , "last_update" : "" } } , "pe_ibes_trailing_12m" : { "item" : { "last_value" : null , "last_value_formatted" : "" , "last_update" : "" } } , "price_rsi(horiz=14d)" : { "item" : { "last_value" : null , "last_value_formatted" : "" , "last_update" : "" } } }` Show more
