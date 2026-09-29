<!--
id: RX-PRODUCT-1039
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Liveness probe

[← Documentation](../../../README.md)

## Response
200 Object Service is up.

### Response Attributes
status string

## Request and response example

GET

/alfred-integrations/v1/healthz

cURL `1 curl --location 'https://api.reflexivity.com/alfred-integrations/v1/healthz' \` Try in API Explorer
### Response
200 `{ "status" : "ok" }`
