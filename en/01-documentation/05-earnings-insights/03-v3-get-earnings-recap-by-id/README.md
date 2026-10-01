<!--
id: RX-PRODUCT-1049
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a22f0efb3c07fb860b58f57
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: earnings-insights/v3-get-earnings-recap-by-id
-->
# V3 Get earnings recap by ID

Returns detailed recap for a specific earnings insight including actual results, KPIs, peer comparisons, risk assessments, themes, and citations. Generated after earnings are reported. Unlike v2, all themes are returned in a single `themes` array (each catalog-backed with an `id`) and there is no `other_themes` field.

#### Header Parameters

Accept-Language string An IETF BCP 47 language tag specifying the language preference for the response content. When provided, the API will return insight text (titles, descriptions, KPIs, themes, etc.) in the requested language. Defaults to `en` if the header is omitted. Returns `404` if the requested language is not available for the insight.
Currently supported languages: `ar`, `de`, `en`, `fr`, `he`, `hu`, `it`, `ja`, `ko`, `nl`, `pt`, `ru`, `es`, `zh-Hans`, `zh-Hant`.

#### Path Parameters

id string (uuid) Required The unique ID of the earnings insight recap.

### Response Expand all

200 Object Successful response with detailed earnings recap

#### Response Attributes

id string (uuid) type string Enum values: `recap` title string company object Show child attributes

earnings object Show child attributes

key_metrics string guidance_update string price_scenario object Show child attributes

kpis array Show child attributes

peer_comparison_sector_context array Show child attributes

risk_assessment_update array Show child attributes

themes array Show child attributes

impacted_companies array Show child attributes

citations array Show child attributes

created_at string (date-time) 404 Object Insight not found, or the requested language is not available for this insight.

---

[← Documentation](../../README.md)
