<!--
id: RX-PRODUCT-1081
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a269de10d17aeec4a2fa30c
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: price-history/get-latest-delayed-price
-->

# Get latest delayed price

**Method:** `GET`

**Endpoint:** `/price-history/v1/delayed/last?ticker=STLA&entity_tag=stla_nyse&datasource=nasdaq`

Returns a list of prices according to the parameters.

Time range for returned price is 24 hours and 15 minutes ago to 15 minutes ago.

#### Query Parameters

tickerstring Required

The security subscribable ticker.

entity_tagstring Required

The unique identifier for an entity.

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
