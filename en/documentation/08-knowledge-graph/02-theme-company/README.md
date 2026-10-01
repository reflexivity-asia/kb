<!--
id: RX-PRODUCT-1067
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f233558
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: knowledge-graph/theme-company
-->

# 🎯 Theme → Company

**Method:** `GET`

**Endpoint:** `/ontology/v3/theme/{theme_id}/company-exposure?limit=`

Returns a universe of companies, ranked by their importance to the theme. Companies must have a market cap greater than US $1B to be eligible for inclusion.

1. **Revenue Contribution**: Share of the theme's total global revenues contributed by the company
2. **Products and Services**: Measures how central and defining this company's products, services, and brands are to the theme's identity
3. **Capital Investment**: Share of the theme's total R&D, capex, and infrastructure investment
4. **Strategic Importance**: Analyzes the company's market share, influence on industry standards, and ecosystem leadership within the theme
5. **Brand Significance**: Evaluates the company's brand recognition and association with the theme

#### Query Parameters

limitinteger

Limit the number of results returned

#### Path Parameters

theme_idstring Required

The ID of the theme

### Response

200

Object

Companies exposed to the theme with enhanced metadata

#### Response Attributes

companystring

The company tag

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
