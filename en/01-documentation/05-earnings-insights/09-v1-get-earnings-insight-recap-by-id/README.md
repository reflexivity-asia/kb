<!--
id: RX-PRODUCT-1055
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f233548
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: earnings-insights/v1-get-earnings-insight-recap-by-id
-->
# V1 Get earnings insight recap by ID

Returns a detailed recap for a specific earnings insight.

#### Header Parameters

Accept-Language string An IETF BCP 47 language tag specifying the language preference for the response content. When provided, the API will return insight text (titles, descriptions, KPIs, themes, etc.) in the requested language. Defaults to `en` if the header is omitted. Returns `404` if the requested language is not available for the insight.
Currently supported languages: `ar`, `de`, `en`, `fr`, `he`, `hu`, `it`, `ja`, `ko`, `nl`, `pt`, `ru`, `es`, `zh-Hans`, `zh-Hant`.

#### Path Parameters

id string (uuid) Required The unique ID of the earnings insight recap.

### Response Expand all

200 Object Successful response with detailed earnings insight recap

#### Response Attributes

id string (uuid) type string Enum values: `recap` entity_tag string earnings_id string title string created_at string (date-time) updated_at string (date-time) key_metrics string guidance_update string reaction_desc string kpis array Show child attributes

insights array Show child attributes

quotes array Show child attributes

themes array Show child attributes

other_themes array Show child attributes

impacted_companies array Show child attributes

peer_comparison_sector_context array Show child attributes

analyst_and_street_reaction object Show child attributes

risk_assessment_update object Show child attributes

citations array Show child attributes

documents array Show child attributes

404 Object Insight not found, or the requested language is not available for this insight.

---

[← Documentation](../../README.md)
