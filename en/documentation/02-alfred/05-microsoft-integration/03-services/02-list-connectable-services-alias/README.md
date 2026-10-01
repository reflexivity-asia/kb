<!--
id: RX-PRODUCT-1037
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a7468d91ccf0d45acdd18fb
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: alfred/microsoft-integration/services/list-connectable-services-alias
-->
# List connectable services (alias)

#### Header Parameters

Authorization-User-Id string
### Response Expand all

200 Object Service catalog grouped by provider.

#### Response Attributes

provider string services array Show child attributes

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
