<!--
id: RX-PRODUCT-1053
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f233544
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: earnings-insights/v1-filter-earnings-insights
-->

# V1 Filter earnings insights

**Method:** `POST`

**Endpoint:** `/earnings-insights/v1/filter`

Returns a list of filtered earnings insights based on filter criteria.

All body fields are optional.

Omit fields you aren't using rather than sending empty values.

- empty strings on `from`/`to` return `400`
- empty arrays (`[]`) on `entities`/`earnings_ids` match nothing and silently return zero results

#### Header Parameters

Accept-Languagestring

An IETF BCP 47 language tag specifying the language preference for the response content.

When provided, the API will return insight text (titles, descriptions, KPIs, themes, etc.) in the requested language. Defaults to `en` if the header is omitted. Returns `404` if the requested language is not available for the insight.

Currently supported languages: `ar`, `de`, `en`, `fr`, `he`, `hu`, `it`, `ja`, `ko`, `nl`, `pt`, `ru`, `es`, `zh-Hans`, `zh-Hant`.

#### Body Parameters

entitiesarray

List of entity tags to filter by. Omit if unused.

Show child attributes

earnings_idsarray

List of earnings IDs to filter by. Omit if unused.

typesarray

List of insight types to filter by.

Enum values:

`preview``recap`

fromstring (date-time)

Start date for filtering insights (inclusive). Omit if unused.

tostring (date-time)

End date for filtering insights (inclusive). Omit if unused

pageinteger

Page number for pagination.

page_sizeinteger

Number of results per page.

### Response

200

Object

Successful response with earnings insights

#### Response Attributes

idstring (uuid)

typestring

Enum values:

`recap``preview`

entity_tagstring

earnings_idstring (uuid)

titlestring

created_atstring (date-time)

updated_atstring (date-time)

---

[← Documentation](../../README.md)
