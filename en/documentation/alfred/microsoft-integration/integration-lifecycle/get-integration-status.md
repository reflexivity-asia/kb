<!--
id: RX-PRODUCT-1033
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Get integration status

[← Documentation](../../../README.md)

### Header Parameters
Authorization-User-Id string
### Path Parameters
provider string Required Integration provider.

Enum values: `microsoft`
## Response Expand all
200 Object Integration status.

### Response Attributes
connected boolean email string Sourced from stored `username` or `mail` metadata. Omitted when not connected.

services array Omitted when not connected.

Show child attributes

400 Object Unsupported provider.

### Response Attributes
error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

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

/alfred-integrations/v1/integrations/{provider}/status

cURL `1 curl --location 'https://api.reflexivity.com/alfred-integrations/v1/integrations/microsoft/status' \` Try in API Explorer
### Response
200 400 401 500 `{ "connected" : false , "email" : "user@example.com" , "services" : [ "onedrive" ] }`
