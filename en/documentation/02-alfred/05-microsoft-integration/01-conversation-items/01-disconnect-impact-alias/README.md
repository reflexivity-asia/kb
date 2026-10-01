<!--
id: RX-PRODUCT-1029
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a7468d91ccf0d45acdd1909
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: alfred/microsoft-integration/conversation-items/disconnect-impact-alias
-->
# Disconnect impact (alias)

#### Header Parameters

Authorization-User-Id string
#### Path Parameters

provider string Required Integration provider.

Enum values: `microsoft` service string Required Provider-scoped service identifier.

### Response Expand all

200 Object Disconnect impact counts.

#### Response Attributes

documentCount integer Total pinned items for (user, provider, service). Equals the sum of `fileCount`.

conversationCount integer Number of entries in `conversations`.

conversations array Show child attributes

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

500 Object Internal error.

#### Response Attributes

error string Required Machine-readable error code.

message string Human-readable text (optional).

details string Debug info (optional).

---

[← Documentation](../../../../README.md)
