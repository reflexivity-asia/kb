<!--
id: RX-PRODUCT-1047
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# V3 Get earnings insights list

[← Documentation](../README.md)
Returns a paginated list of earnings insights with basic company information. Supports filtering by type and date range. Mirrors the v2 list endpoint.

### Query Parameters
type string Filter by insight type.

Enum values: `preview``recap` from string (date-time) Start date for filtering insights (inclusive, RFC3339 format).

to string (date-time) End date for filtering insights (inclusive, RFC3339 format).

page integer Page number for pagination.

Minimum 1 page_size integer Number of results per page (max 1000).

Minimum 1 Maximum 1000
## Response Expand all
200 Object Successful response with earnings insights list

### Response Attributes
id string (uuid) type string Enum values: `preview``recap` title string company object Show child attributes

created_at string (date-time)

## Request and response example

GET

/earnings-insights/v3?type=preview&from=&to=&page=&page_size=

cURL `1 curl --location 'https://api.reflexivity.com/earnings-insights/v3?type=preview' \` Try in API Explorer
### Response
200 `[ { "id" : "efeda7b8-4c8f-425f-bbd5-39042e061908" , "type" : "recap" , "title" : "Micron Technology Q1-2026 Earnings: Record Revenue and EPS Driven by AI Data Center Demand, Strong Guidance Validates Momentum" , "company" : { "name" : "MICRON TECHNOLOGY" , "ticker" : "mu" , "isin" : "US5951121038" , "exchange" : "nasd" } , "created_at" : "2025-12-17T21:22:21Z" } , { "id" : "d54f6a89-0969-4e86-a90e-0cca8dd1833e" , "type" : "preview" , "title" : "Micron Technology Q1 2026 Earnings: AI-Driven Demand Drives Record Revenue, HBM Momentum and $18B Capex Guidance in Focus" , "company" : { "name" : "MICRON TECHNOLOGY" , "ticker" : "mu" , "isin" : "US5951121038" , "exchange" : "nasd" } , "created_at" : "2025-12-14T05:05:08Z" } ]` Show more
