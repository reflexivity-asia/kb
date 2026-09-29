<!--
id: RX-PRODUCT-1020
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a27deeaefde700c1f40687f
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: alfred/conversation/search/search-conversations
-->
# Search conversations

Full-text search across the user's conversations. Returns matching conversations with a representative state record for each result.

#### Header Parameters

Authorization string
#### Query Parameters

q string Required Search query string.

page integer Page number (1-indexed, default 1).

Minimum 1 Default value 1 page_size integer Number of items per page (default 10).

Minimum 1 Default value 10
### Response Expand all

200 Object Successfully retrieved search results.

#### Response Attributes

results array Show child attributes

400 Object Bad request — invalid pagination parameters.

401 Object Unauthorized.

500 Object Internal server error.

---

[← Documentation](../../../../README.md)
