<!--
id: RX-PRODUCT-1060
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a1ea624d2cd820b12c29016
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: entity-report/relevance
-->

# V1 Relevance

**Method:** `GET`

**Endpoint:** `/entity-report/v1/entity/{entity_tag}/relevance`

Retrieves the relevant information to show on a card.

#### Path Parameters

entity_tagstring Required

The unique identifier for an entity.

### Response

200

Object

OK

#### Response Attributes

idinteger

The card ID.

expressionstring

The internal expression of the card.

last_valuenumber

The last value of the snake.

namestring

The card's name.

image_urlstring

The URL for the card's image.

explanationstring

An explanation for the card.

connected_article_titlestring

The title of the related article.

connected_article_urlstring

The URL of the related article.

scenario_conditionobject

Payload to send to the scenario tool.

group_codestring

The code of the group this card belongs to.

group_namestring

The name of the group this card belongs to.

group_icon_urlstring

The URL of the group's icon this card belongs to.

snake_last_datestring

The last date the snake was updated.

400

Object

Invalid entity tag

404

Object

Entity tag not found

---

[← Documentation](../../README.md)
