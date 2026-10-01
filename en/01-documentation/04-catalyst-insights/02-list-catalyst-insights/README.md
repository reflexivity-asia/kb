<!--
id: RX-PRODUCT-1044
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f233538
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: catalyst-insights/list-catalyst-insights
-->
# List catalyst insights

Returns a paginated list of catalyst insights. Supports filtering by category, sub-category, and date range.

#### Header Parameters

Accept-Language string An IETF BCP 47 language tag specifying the language preference for the response content. When provided, the API will return insight text (titles, descriptions, section content, themes, etc.) in the requested language. Defaults to `en` if the header is omitted. Returns `404` if the requested language is not yet available for the insight.
Currently supported languages: `ar`, `de`, `en`, `fr`, `he`, `hu`, `it`, `ja`, `ko`, `nl`, `pt`, `ru`, `es`, `zh-Hans`, `zh-Hant`.

#### Query Parameters

categories string Comma-separated list of categories to filter by. Valid values: `company`, `market_wide`.

sub_categories string Comma-separated list of sub-categories to filter by. Valid values: `corporate_actions_strategic_announcements`, `management_leadership_changes`, `financial_operational_updates`, `legal_regulatory_events`, `thematic`, `macroeconomic_policy_changes`, `geopolitical_global_events`.

from string (date-time) Start of the date range (inclusive, RFC3339 format).

to string (date-time) End of the date range (inclusive, RFC3339 format).

page integer Page number for pagination (1-based).

Minimum 1 page_size integer Number of results per page (max 1000).

Minimum 1 Maximum 1000
### Response Expand all

200 Object Paginated list of catalyst insights.

#### Response Attributes

id string (uuid) title string category string Top-level category of the insight.

- `company` – insight is attributed to a specific company/entity * `market_wide` – insight covers a broader market or macroeconomic event

Enum values: `company``market_wide` sub_category string Sub-category refining the insight type.
Company sub-categories:

- `corporate_actions_strategic_announcements` – M&A, buybacks, spin-offs, major strategic shifts * `management_leadership_changes` – CEO/CFO appointments, board changes * `financial_operational_updates` – earnings beats/misses, guidance revisions, cost cuts * `legal_regulatory_events` – lawsuits, regulatory investigations, fines
Market-wide sub-categories:

- `thematic` – insights driven by a named investment theme ...

Enum values: `corporate_actions_strategic_announcements``management_leadership_changes``financial_operational_updates``legal_regulatory_events``thematic``macroeconomic_policy_changes``geopolitical_global_events` company object Present when `category` is `company`. Omitted for `market_wide` insights.

Show child attributes

theme object Present when `sub_category` is `thematic`. Omitted otherwise.

Show child attributes

created_at string (date-time) Time at which the insight was published. RFC3339 format.

400 Object Invalid query parameter value.

401 Object Unauthorized – missing or invalid authentication.

500 Object Internal server error.

---

[← Documentation](../../README.md)
