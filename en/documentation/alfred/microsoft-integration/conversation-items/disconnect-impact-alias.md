<!--
id: RX-PRODUCT-1029
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Disconnect impact (alias)

[← Documentation](../../../README.md)

### Header Parameters
Authorization-User-Id string
### Path Parameters
provider string Required Integration provider.

Enum values: `microsoft` service string Required Provider-scoped service identifier.

## Response Expand all
200 Object Disconnect impact counts.

### Response Attributes
documentCount integer Total pinned items for (user, provider, service). Equals the sum of `fileCount`.

conversationCount integer Number of entries in `conversations`.

conversations array Show child attributes

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

500 Object Internal error.

### Response Attributes
error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

## Request and response example

GET

/alfred-integrations/v1/integrations/{provider}/services/{service}/connected-convos

cURL `1 curl --location 'https://api.reflexivity.com/alfred-integrations/v1/integrations/microsoft/services/onedrive/connected-convos' \` Try in API Explorer
### Response
200 400 401 500 `{ "documentCount" : 100 , "conversationCount" : 10 , "conversations" : [ { "id" : "conv-1" , "fileCount" : 8 } ] }`
