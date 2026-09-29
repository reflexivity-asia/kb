<!--
id: RX-PRODUCT-1077
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f233550
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: scenario-insights/get-insight-predictions-based-on-requested-id
-->
# Get scenario insight predictions by ID

#### Path Parameters

id string Required
### Response Expand all

200 Object Return predictions for the requested insight.

#### Response Attributes

relative_idx integer horizon string mean number median number count integer percentiles object Show child attributes

high number low number std_dev number min number max number date string (date-time) 404 Object Not found.

500 Object Internal server error.

---

[← Documentation](../../README.md)
