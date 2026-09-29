<!--
id: RX-PRODUCT-1034
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Disconnect a provider or a single service

[← Documentation](../../../README.md)

### Header Parameters
Authorization-User-Id string
### Query Parameters
service string Disconnect a single service. Omit to disconnect all services.

### Path Parameters
provider string Required Integration provider.

Enum values: `microsoft`
## Response
204 Object Disconnected.

400 Object Unsupported provider or invalid service.

### Response Attributes
error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

401 Object Missing user id.

### Response Attributes
error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

404 Object No active integration found.

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

DELETE

/alfred-integrations/v1/integrations/{provider}/disconnect?service=onedrive

cURL `1 curl --location --request DELETE 'https://api.reflexivity.com/alfred-integrations/v1/integrations/microsoft/disconnect?service=onedrive' \` Try in API Explorer
### Response
204 400 401 404 500 `Disconnected.`
