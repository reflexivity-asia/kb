<!--
id: RX-PRODUCT-1059
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a26991b361fc1a8957ef55b
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: entity-report/v2-relevance
-->
# V2 Relevance

Retrieves the relevant information to show on a card.

#### Path Parameters

entity_tag string Required The unique identifier for an entity.

### Response Expand all

200 Object OK

#### Response Attributes

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

---

[← Documentation](../../README.md)
