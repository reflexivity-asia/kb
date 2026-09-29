<!--
id: RX-PRODUCT-1032
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Connect a provider

[← Documentation](../../../README.md)

### Header Parameters
Authorization-User-Id string
### Path Parameters
provider string Required Integration provider.

Enum values: `microsoft`
### Body Parameters Expand all
accessToken string Required Token acquired from the provider by the frontend.

services array Subset of the provider's services. Defaults to all services.

Show child attributes

extra object Required Provider-specific extras. Microsoft requires `tenantId`;
`homeAccountId` and `username` are stored in integration metadata
when present.

Show child attributes

## Response Expand all
200 Object Provider connected.

### Response Attributes
connected boolean services array Show child attributes

400 Object Unsupported provider, invalid request body, invalid service,
`invalid_extras`, or `invalid_provider_token` (provider token is
invalid/expired, wrong audience, or requires re-authentication).

### Response Attributes
error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

401 Object Missing user id.

### Response Attributes
error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

403 Object `consent_required` — tenant admin consent required.

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

POST

/alfred-integrations/v1/integrations/{provider}/connect

cURL `1 curl --location 'https://api.reflexivity.com/alfred-integrations/v1/integrations/microsoft/connect' \ 2 --data '{ 3 "accessToken": "", 4 "services": [ 5 "onedrive", 6 "outlook", 7 "onenote" 8 ], 9 "extra": { 10 "tenantId": "aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee", 11 "homeAccountId": "", 12 "username": "" 13 } 14 }'` Try in API Explorer
### Response
200 400 401 403 500 502 `{ "connected" : false , "services" : [ "onedrive" , "outlook" , "onenote" ] }`
