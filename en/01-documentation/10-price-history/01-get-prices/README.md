<!--
id: RX-PRODUCT-1079
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a269e4a0d17aeec4a2faa81
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: price-history/get-prices
-->

# Get prices

**Method:** `GET`

**Endpoint:** `/price-history/v1/prices?ticker=STLA&entity_tag=stla_nyse&resolution=1D&from=2018-03-13T18:53:00Z&to=2020-03-19T16:58:00Z&datasource=nasdaq`

Returns a list of prices according to the parameters.

#### Query Parameters

tickerstring Required

The security subscribable ticker.

entity_tagstring Required

The unique identifier for an entity.

resolutionstring

Default value

1m

fromstring (date-time)

Start date to query from. When not present, it will return from the first data point that exists.

tostring (date-time)

End date to query to. When not present, it will return until the last data point that exists.

datasourcestring

Default value

nasdaq

Enum values:

`nasdaq``cboe`

### Response

200

Object

The candles are returned successfully.

#### Response Attributes

timestring (date-time)Required

The timestamp of the candle.

opennumber Required

The open price value.

highnumber Required

The high price value.

lownumber Required

The low price value.

closenumber Required

The close price value.

400

Object

Missing parameter or invalid resolution.

401

Object

User not authorized.

500

Object

Internal Server Error.

---

[← Documentation](../../README.md)
