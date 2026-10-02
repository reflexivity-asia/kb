<!--
id: RX-PRODUCT-1082
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Get market-close price

[← Documentation](../README.md)
MarketClose returns the close price according to the parameters. Only valid for 1min candles.

### Query Parameters
ticker string Required The security ticker. Ticker must be upper case.

datasource string Default value nasdaq Enum values: `nasdaq``cboe`
## Response
200 Object The price is returned successfully.

### Response Attributes
time string (date-time) Required The timestamp of the candle.

close number Required The close price value.

400 Object Missing parameter.

401 Object User not authorized.

404 Object Market close price for the provided ticker not found.

500 Object Internal Server Error.

## Request and response example

GET

/price-history/v1/market-close?ticker=STLA&datasource=nasdaq

cURL `1 curl --location 'https://api.reflexivity.com/price-history/v1/market-close?ticker=STLA&datasource=nasdaq' \` Try in API Explorer
### Response
200 400 401 404 500 `{ "time" : "2001-08-14T00:00:00Z" , "close" : 4.8002 }`
