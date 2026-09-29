<!--
id: RX-PRODUCT-1071
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f23355a
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: knowledge-graph/company-product
-->
# 🛍️ Company → Product

Returns products, brands, or services a company is associated with, based on:

- Revenue Attribution : Measures how much of the company’s top line is driven by this product

- Product/Brand Significance : How integral is this product to the company’s overall brand image, consumer perception, or portfolio identity

- Strategic Importance : Assessment of whether the product is central to company strategy or future roadmaps

- Capital/Resource Investment : Spending on R&D, capex, or marketing budget directly tied to the product

- Uniqueness : Patents, proprietary positioning, or technological first-mover advantage

- Headcount / Teams : Employee allocation and team announcements devoted to this product’s development or expansion

#### Query Parameters

limit integer Limit the number of results returned

#### Path Parameters

tag string Required The tag of the company

### Response Expand all

200 Object Products the company is exposed to with enhanced metadata

#### Response Attributes

product string The product name

relationship object Enhanced relationship metadata

Show child attributes

400 Object Bad request

404 Object Not found

500 Object Internal server error

---

[← Documentation](../../README.md)
