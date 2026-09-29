<!--
id: RX-PRODUCT-1042
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a26a01cefde700c1f3f8bab
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: calculator/get-theme-performance
-->
# Get theme performance

Returns the aggregate performance time series for the specified theme and period. It also includes the entities used in the calculation.

#### Body Parameters

theme_id string Required Theme identifier.

period string Required Period for performance calculation (e.g., "1D", "1W", "1M", "3M", "6M", "1Y").

### Response Expand all

200 Object Successful response

#### Response Attributes

entities array Show child attributes

aggregate array Show child attributes

request object Show child attributes

response object Show child attributes

400 Object Bad request.

404 Object Not found.

500 Object Internal server error.

---

[← Documentation](../../README.md)
