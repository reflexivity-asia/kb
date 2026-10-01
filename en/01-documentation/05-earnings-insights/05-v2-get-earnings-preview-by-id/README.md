<!--
id: RX-PRODUCT-1051
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f233540
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: earnings-insights/v2-get-earnings-preview-by-id
-->
# V2 Get earnings preview by ID

Returns detailed preview for a specific earnings insight including scenarios, price targets, KPIs, themes, and impacted companies. Generated before earnings are reported.

#### Header Parameters

Accept-Language string An IETF BCP 47 language tag specifying the language preference for the response content. When provided, the API will return insight text (titles, descriptions, KPIs, themes, etc.) in the requested language. Defaults to `en` if the header is omitted. Returns `404` if the requested language is not available for the insight.
Currently supported languages: `ar`, `de`, `en`, `fr`, `he`, `hu`, `it`, `ja`, `ko`, `nl`, `pt`, `ru`, `es`, `zh-Hans`, `zh-Hant`.

#### Path Parameters

id string (uuid) Required The unique ID of the earnings insight preview.

### Response Expand all

200 Object Successful response with detailed earnings preview

#### Response Attributes

id string (uuid) type string Enum values: `preview` title string company object Show child attributes

earnings object Show child attributes

price_targets object Show child attributes

beats_scenario object Show child attributes

misses_scenario object Show child attributes

sentiment_expectations array Show child attributes

seasonality array Show child attributes

kpis array Show child attributes

key_items_to_watch array Show child attributes

investment_outlook object Show child attributes

themes array Show child attributes

other_themes array Show child attributes

impacted_companies array Show child attributes

created_at string (date-time) 404 Object Insight not found, or the requested language is not available for this insight.

---

[← Documentation](../../README.md)
