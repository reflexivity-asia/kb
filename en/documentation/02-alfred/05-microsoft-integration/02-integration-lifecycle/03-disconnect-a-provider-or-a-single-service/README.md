<!--
id: RX-PRODUCT-1034
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a7468d91ccf0d45acdd1903
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: alfred/microsoft-integration/integration-lifecycle/disconnect-a-provider-or-a-single-service
-->
# Disconnect a provider or a single service

#### Header Parameters

Authorization-User-Id string
#### Query Parameters

service string Disconnect a single service. Omit to disconnect all services.

#### Path Parameters

provider string Required Integration provider.

Enum values: `microsoft`
### Response

204 Object Disconnected.

400 Object Unsupported provider or invalid service.

#### Response Attributes

error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

401 Object Missing user id.

#### Response Attributes

error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

404 Object No active integration found.

#### Response Attributes

error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

500 Object Internal error.

#### Response Attributes

error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

---

[← Documentation](../../../../README.md)
