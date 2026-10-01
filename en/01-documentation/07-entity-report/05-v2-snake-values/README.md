<!--
id: RX-PRODUCT-1063
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a269892d24bb0f7bf0bc14b
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: entity-report/v2-snake-values
-->
# V2 Snake Values

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

#### Path Parameters

entity_tag string Required The unique identifier for an entity.

### Response Expand all

200 Object OK

#### Response Attributes

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

---

[← Documentation](../../README.md)
