<!--
id: RX-PRODUCT-1062
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a1ea62c6906e44762737fb9
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: entity-report/key-value
-->
# V1 Key-value

Retrieves a snake's fundamentals to show on a card.

#### Path Parameters

entity_tag string Required The unique identifier for an entity.

### Response

200 Object OK

#### Response Attributes

expression string The snake expression.

value_string string The value as a string.

label string The value's label.

explanation string An explanation for the fundamental card.

group_code string The code of the group this card belongs to.

group_name string The name of the group this card belongs to.

group_icon_url string The URL of the group's icon this card belongs to.

400 Object Invalid entity tag

404 Object Entity tag not found

---

[← Documentation](../../README.md)
