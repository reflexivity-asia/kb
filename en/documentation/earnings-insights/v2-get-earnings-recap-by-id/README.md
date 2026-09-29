<!--
id: RX-PRODUCT-1052
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f233542
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: earnings-insights/v2-get-earnings-recap-by-id
-->

# V2 Get earnings recap by ID

**Method:** `GET`

**Endpoint:** `/earnings-insights/v2/recap/{id}`

Returns detailed recap for a specific earnings insight including actual results, KPIs, peer comparisons, risk assessments, themes, and citations. Generated after earnings are reported.

#### Header Parameters

Accept-Languagestring

An IETF BCP 47 language tag specifying the language preference for the response content. When provided, the API will return insight text (titles, descriptions, KPIs, themes, etc.) in the requested language. Defaults to `en` if the header is omitted. Returns `404` if the requested language is not available for the insight.
Currently supported languages: `ar`, `de`, `en`, `fr`, `he`, `hu`, `it`, `ja`, `ko`, `nl`, `pt`, `ru`, `es`, `zh-Hans`, `zh-Hant`.

#### Path Parameters

idstring (uuid)Required

The unique ID of the earnings insight recap.

### Response

200

Object

Successful response with detailed earnings recap

#### Response Attributes

idstring (uuid)

typestring

Enum values:

`recap`

titlestring

companyobject

Show child attributes

earningsobject

Show child attributes

key_metricsstring

guidance_updatestring

price_scenarioobject

Show child attributes

kpisarray

Show child attributes

peer_comparison_sector_contextarray

Show child attributes

risk_assessment_updatearray

Show child attributes

themesarray

Show child attributes

other_themesarray

Show child attributes

impacted_companiesarray

Show child attributes

citationsarray

Show child attributes

created_atstring (date-time)

404

Object

Insight not found, or the requested language is not available for this insight.

---

[← Documentation](../../README.md)
