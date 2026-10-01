<!--
id: RX-PRODUCT-1032
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a7468d91ccf0d45acdd18ff
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: alfred/microsoft-integration/integration-lifecycle/connect-a-provider
-->
# Connect a provider

#### Header Parameters

Authorization-User-Id string
#### Path Parameters

provider string Required Integration provider.

Enum values: `microsoft`
#### Body Parameters Expand all

accessToken string Required Token acquired from the provider by the frontend.

services array Subset of the provider's services. Defaults to all services.

Show child attributes

extra object Required Provider-specific extras. Microsoft requires `tenantId`;
`homeAccountId` and `username` are stored in integration metadata
when present.

Show child attributes

### Response Expand all

200 Object Provider connected.

#### Response Attributes

connected boolean services array Show child attributes

400 Object Unsupported provider, invalid request body, invalid service,
`invalid_extras`, or `invalid_provider_token` (provider token is
invalid/expired, wrong audience, or requires re-authentication).

#### Response Attributes

error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

401 Object Missing user id.

#### Response Attributes

error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

403 Object `consent_required` — tenant admin consent required.

#### Response Attributes

error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

500 Object Internal error.

#### Response Attributes

error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

502 Object `provider_unavailable` — upstream provider unreachable.

#### Response Attributes

error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

---

[← Documentation](../../../../README.md)
