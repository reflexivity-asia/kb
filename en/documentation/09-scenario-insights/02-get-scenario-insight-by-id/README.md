<!--
id: RX-PRODUCT-1076
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f23354c
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: scenario-insights/get-insight-based-on-requested-id
-->

# Get scenario insight by ID

**Method:** `GET`

**Endpoint:** `/insights/v1/{id}`

#### Path Parameters

idstring Required

### Response

200

Object

Return insight.

#### Response Attributes

conditionsarray

episodesarray

hit_ratioobject

metadataobject

idstring

titlestring

contentarray

disclaimerstring

cardobject

created_atstring (date-time)

chartsarray

404

Object

Not found.

500

Object

Internal server error.

---

[← Documentation](../../README.md)
