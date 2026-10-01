<!--
id: RX-PRODUCT-1075
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f23354e
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: scenario-insights/get-filtered-insights
-->

# Get filtered scenario insights

**Method:** `POST`

**Endpoint:** `/insights/v1/filter`

All body fields are optional. Omit a field, send `null`, or send an empty array `[]` to skip a filter.

Include at least one narrowing filter (e.g. entity). Queries with no filters can be slow and may time out.

Do not send empty strings or empty-string placeholders. Both of these return `400`:

- `""` on `from_date` / `to_date` / `direction`
- `[""]` inside numeric arrays (`class`, `asset_cls`, `stars`, `sub_cls`)

Filters are cumulative, so over-constraining returns no results. For example:
- `entity: ["tsla_nasd"]` (a stock) combined with `class: [2, 5]` (commodity/ETF)
- `[""]` inside a text array, which filters for an empty value

#### Body Parameters

topicarray

Return insights that match any of the topics in the list.

asset_clsarray

Return insights that match any of the asset classes in the list.

Enum values:

`0``1``2``3``4``5`

classarray

Return insights that match any of the classes in the list.

directioninteger

Return insights that with matching direction.

- 1 - Up
- 2 - Down

Enum values:

`1``2`

ecoarray

Return insights that match any of the economies in the list.

entityarray

Return insights that match any of the entity tags in the list.

eventarray

Return insights that match any of the events in the list.

horizonarray

Return insights that match any of the horizons in the list.

last_value__ltenumber

Return insights with last value less than or equal to last_value__lte.

market_cap_usd_bn__gtenumber

Return insights with market cap greater than or equal to market_cap_usd_bn__gte.

market_cap_usd_bn__ltnumber

Return insights with market cap less than market_cap_usd_bn__lt.

median_return__gtenumber

Return insights with median greater than or equal to median_return__gte.

median_return__ltnumber

Return insights with median less than median_return__lt.

sectorarray

Return insights that match any of the sectors in the list.

starsarray

Return insights that have number of stars defined in the list.

sub_classarray

Return insights that match any of the sub classes in the list.

from_datestring (date-time)

Return insights that were created after the defined date.

to_datestring (date-time)

Return insights that were created before the defined date.

pageinteger

Page number.

limitinteger

Limit for the number of results.

### Response

200

Object

Return list of insights.

#### Response Attributes

resultarray

400

Object

Bad request.

500

Object

Internal server error.

---

[← Documentation](../../README.md)
