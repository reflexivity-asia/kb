<!--
id: RX-PRODUCT-1054
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f233546
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: earnings-insights/v1-get-earnings-insight-preview-by-id
-->
# V1 Get earnings insight preview by ID

Returns a detailed preview for a specific earnings insight.

#### Header Parameters

Accept-Language string An IETF BCP 47 language tag specifying the language preference for the response content. When provided, the API will return insight text (titles, descriptions, KPIs, themes, etc.) in the requested language. Defaults to `en` if the header is omitted. Returns `404` if the requested language is not available for the insight.
Currently supported languages: `ar`, `de`, `en`, `fr`, `he`, `hu`, `it`, `ja`, `ko`, `nl`, `pt`, `ru`, `es`, `zh-Hans`, `zh-Hant`.

#### Path Parameters

id string (uuid) Required The unique ID of the earnings insight preview.

### Response Expand all

200 Object Successful response with detailed earnings insight preview

#### Response Attributes

id string (uuid) type string Enum values: `preview` entity_tag string earnings_id string title string created_at string (date-time) updated_at string (date-time) expectation string historical_context array Show child attributes

seasonality array Show child attributes

kpis array Show child attributes

themes array Show child attributes

other_themes array Show child attributes

key_items array Show child attributes

investment_outlook object Show child attributes

impacted_companies array Show child attributes

citations array Show child attributes

404 Object Insight not found, or the requested language is not available for this insight.

---

[← Documentation](../../README.md)
