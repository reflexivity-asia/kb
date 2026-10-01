<!--
id: RX-PRODUCT-1082
type: product
language: en
locale: en
author: Reflexivity GTM Team
kb_imported: 2026-09-29
status: published
translation_status: canonical
resource: Reflexivity Documentation
-->
# Get market-close price

[Price History](../README.md) · [Documentation](../../README.md)

**Method:** `GET`

MarketClose returns the close price according to the parameters. Only valid for 1min candles.

#### Query Parameters

`ticker` — `string` — **Required**

The security ticker. Ticker must be upper case.

`datasource` — `string`

### Response

**200** — Object: The price is returned successfully.

#### Response Attributes

`time` — `string (date-time)` — **Required**

The timestamp of the candle.

`close` — `number` — **Required**

The close price value.

**400** — Object: Missing parameter.

**401** — Object: User not authorized.

**404** — Object: Market close price for the provided ticker not found.

**500** — Object: Internal Server Error.

**Endpoint:** `GET /price-history/v1/market-close?ticker=STLA&datasource=nasdaq`

## Request example

```bash
curl --location 'https://api.reflexivity.com/price-history/v1/market-close?ticker=STLA&datasource=nasdaq' \
```

## Response example

```json
{
  "time": "2001-08-14T00:00:00Z",
  "close": 4.8002
}
```

---

← [Price History](../README.md) · [AI Connections](../../11-ai-connections/README.md) →
