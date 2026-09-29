<!--
id: RX-PRODUCT-1070
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f233556
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: knowledge-graph/company-company-competitors
-->
# 🏢 Company → Company (Competitors)

Returns competitors with three top intersecting themes, based on:

- Competitive Product or Service Offerings : Degree of overlap in core products/services that drive primary revenue streams

- Intersecting Thematic Exposure, GICS Sector, or Industry Classifications : Shared industry classifications and thematic exposure in main business segments

- Similar Customer Bases : Extent to which both companies target and serve overlapping customer segments in their primary markets

- Parallel Technology or Patent Portfolios : Similarity in IP portfolios, innovation areas, and R&D focus critical to competitive advantages

- Similar Business Models : Comparable business models, revenue structures, and go-to-market strategies in overlapping segments

- Other Competitive Indicators : Geographic overlap, strategic positioning, management commentary, and market analyst comparisons

#### Query Parameters

limit integer Limit the number of results returned

#### Path Parameters

tag string Required The tag of the company

### Response Expand all

200 Object A list of company competitors with relationship details and competing themes

#### Response Attributes

company string The competitor company tag

relationship object Enhanced relationship metadata

Show child attributes

competing_themes array List of intersecting themes where companies compete with each other

Show child attributes

400 Object Bad request

404 Object Not found

500 Object Internal server error

---

[← Documentation](../../README.md)
