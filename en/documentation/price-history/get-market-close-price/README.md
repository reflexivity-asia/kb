<!--
id: RX-PRODUCT-1082
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a269df3361fc1a8957f8242
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: price-history/get-market-close-price
-->
# Get market-close price

MarketClose returns the close price according to the parameters. Only valid for 1min candles.

#### Query Parameters

ticker string Required The security ticker. Ticker must be upper case.

datasource string Default value nasdaq Enum values: `nasdaq``cboe`
### Response

200 Object The price is returned successfully.

#### Response Attributes

time string (date-time) Required The timestamp of the candle.

close number Required The close price value.

400 Object Missing parameter.

401 Object User not authorized.

404 Object Market close price for the provided ticker not found.

500 Object Internal Server Error.

---

[← Documentation](../../README.md)
