<!--
id: RX-PRODUCT-1061
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a2698f40d17aeec4a2f1d3e
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: entity-report/v3-key-value
-->

# V3 Key-value

**Method:** `GET`

**Endpoint:** `/entity-report/v3/entity/{entity_tag}/key-values`

Retrieves a snake's fundamentals to show on a card.

#### Path Parameters

entity_tagstring Required

The unique identifier for an entity.

### Response

200

Object

OK

#### Response Attributes

expressionstring

The snake expression.

value_stringstring

The value as a string.

labelstring

The value's label.

explanationstring

An explanation for the fundamental card.

group_codestring

The code of the group this card belongs to.

group_namestring

The name of the group this card belongs to.

group_icon_urlstring

The URL of the group's icon this card belongs to.

400

Object

Invalid entity tag

404

Object

Entity tag not found

---

[← Documentation](../../README.md)
