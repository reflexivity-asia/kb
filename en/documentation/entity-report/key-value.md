<!--
id: RX-PRODUCT-1062
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# V1 Key-value

[← Documentation](../README.md)
Retrieves a snake's fundamentals to show on a card.

### Path Parameters
entity_tag string Required The unique identifier for an entity.

## Response
200 Object OK

### Response Attributes
expression string The snake expression.

value_string string The value as a string.

label string The value's label.

explanation string An explanation for the fundamental card.

group_code string The code of the group this card belongs to.

group_name string The name of the group this card belongs to.

group_icon_url string The URL of the group's icon this card belongs to.

400 Object Invalid entity tag

404 Object Entity tag not found

## Request and response example

GET

/entity-report/v1/entity/{entity_tag}/key-values

cURL `1 curl --location 'https://api.reflexivity.com/entity-report/v1/entity/tsla_nasd/key-values' \` Try in API Explorer
### Response
200 400 404 `[ { "expression" : "tsla_nasd.ibes_eps_forward_12m_growth" , "value_string" : "5.51%" , "label" : "High" , "explanation" : "Earnings per share (EPS) is a company's net profit divided by the number of common shares it has outstanding." , "group_code" : "group_fundamental" , "group_name" : "Fundamentals" , "group_icon_url" : "https://img/toggle-images/chart-bar.png" } ]` Show more
