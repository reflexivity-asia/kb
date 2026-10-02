<!--
id: RX-PRODUCT-1030
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Resolve an attached item into a browser URL

[← Documentation](../../../README.md)

### Header Parameters
Germ-Conversation-Id string Alternative way to pass the conversation context (MCP parity).
Ignored when the `conversation_id` query parameter is set.

Authorization-User-Id string
### Query Parameters
conversation_id string Conversation context enabling lazy-pin for shared conversations.
Takes precedence over the `Germ-Conversation-Id` header.

### Path Parameters
provider string Required Integration provider.

Enum values: `microsoft` service string Required Provider-scoped service identifier.

external_id string Required Provider-side item id returned in attached item listings.

## Response
200 Object Resolved browser URL.

### Response Attributes
url string 400 Object Unsupported provider, invalid service, or `capability_not_supported`.

### Response Attributes
error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

401 Object Missing user id.

### Response Attributes
error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

403 Object `service_not_connected` (no active integration / service removed),
`item_not_accessible` (provider denied access to the item), or
`provider_reconnect_required` (integration disconnected, token
invalid, or consent required).

### Response Attributes
error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

404 Object Item not found (never attached, deleted, or no longer accessible).

### Response Attributes
error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

500 Object Internal error.

### Response Attributes
error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

502 Object `provider_unavailable` — upstream provider unreachable.

### Response Attributes
error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

## Request and response example

GET

/alfred-integrations/v1/integrations/{provider}/services/{service}/items/{external_id}?conversation_id=

cURL `1 curl --location --globoff 'https://api.reflexivity.com/alfred-integrations/v1/integrations/microsoft/services/onedrive/items/{external_id}' \` Try in API Explorer
### Response
200 400 401 403 404 500 502 `{ "url" : "https://contoso.sharepoint.com/path/file.docx" }`
