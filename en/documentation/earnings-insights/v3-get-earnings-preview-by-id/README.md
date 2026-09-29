<!--
id: RX-PRODUCT-1048
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a22f0d78b402c5641fc8972
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: earnings-insights/v3-get-earnings-preview-by-id
-->

# V3 Get earnings preview by ID

**Method:** `GET`

**Endpoint:** `/earnings-insights/v3/preview/{id}`

Returns detailed preview for a specific earnings insight including scenarios, price targets, KPIs, themes, and impacted companies. Generated before earnings are reported. Unlike v2, all themes are returned in a single `themes` array (each catalog-backed with an `id`) and there is no `other_themes` field.

#### Header Parameters

Accept-Languagestring

An IETF BCP 47 language tag specifying the language preference for the response content. When provided, the API will return insight text (titles, descriptions, KPIs, themes, etc.) in the requested language. Defaults to `en` if the header is omitted. Returns `404` if the requested language is not available for the insight.
Currently supported languages: `ar`, `de`, `en`, `fr`, `he`, `hu`, `it`, `ja`, `ko`, `nl`, `pt`, `ru`, `es`, `zh-Hans`, `zh-Hant`.

#### Path Parameters

idstring (uuid)Required

The unique ID of the earnings insight preview.

### Response

200

Object

Successful response with detailed earnings preview

#### Response Attributes

idstring (uuid)

typestring

Enum values:

`preview`

titlestring

companyobject

Show child attributes

earningsobject

Show child attributes

price_targetsobject

Show child attributes

beats_scenarioobject

Show child attributes

misses_scenarioobject

Show child attributes

sentiment_expectationsarray

Show child attributes

seasonalityarray

Show child attributes

kpisarray

Show child attributes

key_items_to_watcharray

Show child attributes

investment_outlookobject

Show child attributes

themesarray

Show child attributes

impacted_companiesarray

Show child attributes

created_atstring (date-time)

404

Object

Insight not found, or the requested language is not available for this insight.

---

[← Documentation](../../README.md)
