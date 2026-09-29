<!--
id: RX-PRODUCT-1066
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f233554
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: knowledge-graph/company-theme
-->
# 🏷️ Company → Theme

Returns investment themes that a company has exposure to, ranked by:

- Revenue Attribution ​: Measures the portion of the company’s total revenue attributable to a specific theme

- Product/Brand Significance ​: Degree to which core offerings reflect or reinforce the theme

- Capital Investment ​: Tangible investments into the theme (e.g., R&D, factories, acquisitions)

- Strategic Importance ​: Relevance of the theme to company’s long-term vision

- Theme Uniqueness ​: Degree to which the company has exclusive positioning within the theme

- Headcount ​: Presence of dedicated teams, hiring initiatives, or employee structure tied to the theme

#### Query Parameters

limit integer Limit the number of results returned

#### Path Parameters

tag string Required The tag of the company

### Response Expand all

200 Object Themes the company is exposed to with enhanced metadata

#### Response Attributes

theme object Enhanced theme information, including parent theme

Show child attributes

relationship object Enhanced relationship metadata

Show child attributes

400 Object Bad request

404 Object Not found

500 Object Internal server error

---

[← Documentation](../../README.md)
