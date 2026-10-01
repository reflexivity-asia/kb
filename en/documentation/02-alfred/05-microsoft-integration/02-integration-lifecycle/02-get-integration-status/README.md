<!--
id: RX-PRODUCT-1033
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a7468d91ccf0d45acdd1901
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: alfred/microsoft-integration/integration-lifecycle/get-integration-status
-->
# Get integration status

#### Header Parameters

Authorization-User-Id string
#### Path Parameters

provider string Required Integration provider.

Enum values: `microsoft`
### Response Expand all

200 Object Integration status.

#### Response Attributes

connected boolean email string Sourced from stored `username` or `mail` metadata. Omitted when not connected.

services array Omitted when not connected.

Show child attributes

400 Object Unsupported provider.

#### Response Attributes

error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

401 Object Missing user id.

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
