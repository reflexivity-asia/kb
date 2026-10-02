<!--
id: RX-PRODUCT-1037
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# List connectable services (alias)

[← Documentation](../../../README.md)

### Header Parameters
Authorization-User-Id string
## Response Expand all
200 Object Service catalog grouped by provider.

### Response Attributes
provider string services array Show child attributes

401 Object Missing user id.

### Response Attributes
error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

500 Object Internal error.

### Response Attributes
error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

## Request and response example

GET

/alfred-integrations/v1/integrations/status

cURL `1 curl --location 'https://api.reflexivity.com/alfred-integrations/v1/integrations/status' \` Try in API Explorer
### Response
200 401 500 `[ { "provider" : "microsoft" , "services" : [ { "type" : "onedrive" , "connected" : false } ] } ]`
