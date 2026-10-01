<!--
id: RX-PRODUCT-1050
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f23353e
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: earnings-insights/v2-get-earnings-insights-list
-->

# V2 Get earnings insights list

**Method:** `GET`

**Endpoint:** `/earnings-insights/v2?type=preview&from=2026-01-01T00:00:00Z&to=2026-12-31T23:59:59Z&page=&page_size=`

Returns a paginated list of earnings insights with basic company information. Supports filtering by type and date range.

#### Query Parameters

typestring

Filter by insight type.

Enum values:

`preview``recap`

fromstring (date-time)

Start date for filtering insights (inclusive, RFC3339 format).

tostring (date-time)

End date for filtering insights (inclusive, RFC3339 format).

pageinteger

Page number for pagination.

Minimum

1

page_sizeinteger

Number of results per page (max 1000).

Minimum

1

Maximum

1000

### Response

200

Object

Successful response with earnings insights list

#### Response Attributes

idstring (uuid)

typestring

Enum values:

`preview``recap`

titlestring

companyobject

Show child attributes

created_atstring (date-time)

---

[← Documentation](../../README.md)
