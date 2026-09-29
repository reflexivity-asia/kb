<!--
id: RX-PRODUCT-1071
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# 🛍️ Company → Product

[← Documentation](../README.md)
Returns products, brands, or services a company is associated with, based on:

- Revenue Attribution : Measures how much of the company’s top line is driven by this product
- Product/Brand Significance : How integral is this product to the company’s overall brand image, consumer perception, or portfolio identity
- Strategic Importance : Assessment of whether the product is central to company strategy or future roadmaps
- Capital/Resource Investment : Spending on R&D, capex, or marketing budget directly tied to the product
- Uniqueness : Patents, proprietary positioning, or technological first-mover advantage
- Headcount / Teams : Employee allocation and team announcements devoted to this product’s development or expansion
### Query Parameters
limit integer Limit the number of results returned

### Path Parameters
tag string Required The tag of the company

## Response Expand all
200 Object Products the company is exposed to with enhanced metadata

### Response Attributes
product string The product name

relationship object Enhanced relationship metadata

Show child attributes

400 Object Bad request

404 Object Not found

500 Object Internal server error

## Request and response example

GET

/ontology/v3/company/{tag}/products?limit=

cURL `1 curl --location 'https://api.reflexivity.com/ontology/v3/company/msft_nasd/products' \` Try in API Explorer
### Response
200 400 404 500 `[ { "product" : "" , "relationship" : { "id" : "" , "description" : "" , "rank" : null , "rank_change" : null , "source_evidence" : "" , "evidence" : [ "" ] } } ]`
