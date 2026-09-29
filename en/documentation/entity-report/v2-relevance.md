<!--
id: RX-PRODUCT-1059
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# V2 Relevance

[← Documentation](../README.md)
Retrieves the relevant information to show on a card.

### Path Parameters
entity_tag string Required The unique identifier for an entity.

## Response Expand all
200 Object OK

### Response Attributes
id integer The card ID.

expression string The internal expression of the card.

last_value number The last value of the snake.

name string The card's name.

image_url string The URL for the card's image.

explanation string An explanation for the card.

connected_article_title string The title of the related article.

connected_article_url string The URL of the related article.

scenario_condition object Payload to send to the scenario tool.

Show child attributes

group_code string The code of the group this card belongs to.

group_name string The name of the group this card belongs to.

group_icon_url string The URL of the group's icon this card belongs to.

snake_last_date string The last date the snake was updated.

400 Object Invalid entity tag

404 Object Entity tag not found

## Request and response example

GET

/entity-report/v2/entity/{entity_tag}/relevance

cURL `1 curl --location 'https://api.reflexivity.com/entity-report/v2/entity/tsla_nasd/relevance' \` Try in API Explorer
### Response
200 400 404 `[ { "id" : 5813313694984116000 , "expression" : "tsla_nasd.fair_value_seasonality(years=5,fcst_horiz=6m)" , "last_value" : 91.53989582773934 , "name" : "Bullish Seasonality over the next 6 months" , "image_url" : "https://img/toggle-images/bullish_seasonality.png" , "explanation" : "Seasonality is a characteristic of an asset in which the asset's returns see regular and predictable changes every calendar year during the same period." , "connected_article_title" : "Seasonality Indicator" , "connected_article_url" : "https://toggle.ai/investing/technical-indicators/seasonality-indicator" , "scenario_condition" : { "order" : 0 , "snake" : "tsla_nasd.fair_value_seasonality(years=5,fcst_horiz=6m)" , "value" : 91.53989582773934 , "condition" : "above" } , "group_code" : "group_fundamental" , "group_name" : "Fundamentals" , "group_icon_url" : "https://img/toggle-images/chart-bar.png" , "snake_last_date" : "2024-03-22T00:00:00Z" } ]` Show more
