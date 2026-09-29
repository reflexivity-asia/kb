<!--
id: RX-PRODUCT-1066
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# 🏷️ Company → Theme

[← Documentation](../README.md)
Returns investment themes that a company has exposure to, ranked by:

- Revenue Attribution ​: Measures the portion of the company’s total revenue attributable to a specific theme
- Product/Brand Significance ​: Degree to which core offerings reflect or reinforce the theme
- Capital Investment ​: Tangible investments into the theme (e.g., R&D, factories, acquisitions)
- Strategic Importance ​: Relevance of the theme to company’s long-term vision
- Theme Uniqueness ​: Degree to which the company has exclusive positioning within the theme
- Headcount ​: Presence of dedicated teams, hiring initiatives, or employee structure tied to the theme
### Query Parameters
limit integer Limit the number of results returned

### Path Parameters
tag string Required The tag of the company

## Response Expand all
200 Object Themes the company is exposed to with enhanced metadata

### Response Attributes
theme object Enhanced theme information, including parent theme

Show child attributes

relationship object Enhanced relationship metadata

Show child attributes

400 Object Bad request

404 Object Not found

500 Object Internal server error

## Request and response example

GET

/ontology/v3/company/{tag}/theme-exposure?limit=

cURL `1 curl --location 'https://api.reflexivity.com/ontology/v3/company/msft_nasd/theme-exposure' \` Try in API Explorer
### Response
200 400 404 500 `[ { "theme" : { "id" : "" , "name" : "" , "description" : "" , "logo_url" : "" , "parent" : { "id" : "" , "name" : "" , "logo_url" : "" } } , "relationship" : { "id" : "" , "description" : "" , "rank" : null , "rank_change" : null , "source_evidence" : "" , "evidence" : [ "" ] } } ]` Show more
