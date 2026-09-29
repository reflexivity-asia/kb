<!--
id: RX-PRODUCT-1047
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a22f06e86cc56670d2188f5
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: earnings-insights/v3-get-earnings-insights-list
-->
# V3 Get earnings insights list

Returns a paginated list of earnings insights with basic company information. Supports filtering by type and date range. Mirrors the v2 list endpoint.

#### Query Parameters

type string Filter by insight type.

Enum values: `preview``recap` from string (date-time) Start date for filtering insights (inclusive, RFC3339 format).

to string (date-time) End date for filtering insights (inclusive, RFC3339 format).

page integer Page number for pagination.

Minimum 1 page_size integer Number of results per page (max 1000).

Minimum 1 Maximum 1000
### Response Expand all

200 Object Successful response with earnings insights list

#### Response Attributes

id string (uuid) type string Enum values: `preview``recap` title string company object Show child attributes

created_at string (date-time)

---

[← Documentation](../../README.md)
