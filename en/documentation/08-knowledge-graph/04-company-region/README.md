<!--
id: RX-PRODUCT-1069
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f23355e
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: knowledge-graph/company-region
-->

# 🌍 Company → Region

**Method:** `GET`

**Endpoint:** `/ontology/v3/company/{tag}/region-exposure?limit=`

Returns broader regional exposure based on:

1. **Revenue Attribution**: Measures the portion of the company’s total revenue attributable to a specific country or region
2. **Strategic Importance**: Evaluates how integral the particular country or region is to the company’s future vision
3. **Supply Chain Dependencies**: Geographic supply chain presence and dependencies
4. **Capital Investments**: Region-specific investments for Capex, R&D spending, marketing budget, or other resources commitments

#### Query Parameters

limitinteger

Limit the number of results returned

#### Path Parameters

tagstring Required

The tag of the company

### Response

200

Object

Regions the company is exposed to with exposure details

#### Response Attributes

codestring

The region code

namestring

The region name

icon_urlstring

The URL of the region's icon

relationshipobject

Enhanced relationship metadata

400

Object

Bad request

404

Object

Not found

500

Object

Internal server error

---

[← Documentation](../../README.md)
