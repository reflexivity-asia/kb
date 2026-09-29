<!--
id: RX-PRODUCT-1103
type: product
language: en
locale: en
author: Reflexivity GTM Team
kb_imported: 2026-09-29
status: published
translation_status: canonical
resource: Reflexivity Documentation
-->
# MCP tool reference

[Reference](../README.md) · [Documentation](../../../README.md)

---

Reference for developers configuring the Reflexivity connection or handling its responses. All seven tools are read-only. For installation, use [Connect](../../connect/README.md).

---

## Connection

| Item | Value |
| --- | --- |
| Production endpoint | `https://api.reflexivity.com/external-research-mcp/mcp` |
| Transport | MCP over Streamable HTTP |
| Plugin server name | `reflexivity-research` |
| Plugin authentication | Browser OAuth with PKCE through `identity.reflexivity.com`; the host handles client registration and token storage |
| Account requirement | Full Reflexivity user with their own account |
| Scope | Read published research and Knowledge Graph data; use authorized saved lists |

The [plugin repository](https://github.com/toggleglobal/reflexivity-ai-plugins) packages the connection for Claude Code, Codex and Cursor. Other hosts may require their own OAuth registration. Do not assume the plugin's dynamic-registration flow applies to an administrator-created Microsoft 365 connection.

---

## References and inputs

Use references returned by the service rather than constructing theme or relationship identifiers.

| Kind | Format | Used by |
| --- | --- | --- |
| Company | `entity:<ticker>_<exchange>`, lowercase | Research and company lookups |
| Theme | `theme:<uuid>` | Research subjects and theme lookups |
| Research | `kg:<uuid>` or `scenario:<uuid>` | Read full research |
| Relationship | `rel:<opaque>` | Relationship evidence |
| Saved list | Bare UUID plus `watchlist` or `basket` | Search and lookup filters |
| Other targets | `country:<ISO-2>`, `region:<name>`, `product:<id>` | Relationship outputs |

A subject or security object can contain `query`, `ref`, `kind`, `exchange` and `asset_class`. `ref` takes precedence over `query`. `kind` defaults to `entity`; use `theme` for a theme query. Exchange hints use codes such as `NASD`. Asset classes are `stock`, `equity`, `etf`, `bond`, `future`, `fx`, `commodity`, `credit` and `mutual_fund`; accepting an input value does not establish research coverage for that asset class.

Saved-list filters use `saved_universe_id` and `saved_universe_type`. List the available identifiers with `list_saved_universes`. Research detail and relationship evidence accept references, not saved-list filters.

---

## Common response fields

| Field | Meaning |
| --- | --- |
| `schema_version` | Response contract version. Read the value returned by the service and interpret the response using the matching contract. This is separate from the plugin or application version. |
| `data_as_of` | UTC timestamp indicating when the response was assembled. It is not the research publication date, reporting period, or proof that the underlying source data was refreshed at that time. |
| `coverage` | Counts of `requested`, `resolved`, `authorized` and `executed`. Units differ by tool. |
| `source_status` | Backend sources and their status, including `ok`, `skipped` and `unavailable`; `detail` may explain a problem. |
| `interpretations` | Input resolution: `input`, `status`, `selected`, ambiguity `candidates`, and `resolver_version`, where applicable. |
| `page` | Paged tools: `requested_limit`, `effective_limit`, `has_more`, and `next_cursor` when another page exists. |
| `window` | Applied `from` and `to`, for research search. |
| `omitted_refs` | Missing items with a `ref` and `reason`, where partial retrieval supports them. |

Resolution statuses include `resolved`, `ambiguous` and `not_found`. Query resolutions identify the selected company or theme; company queries can include ticker and exchange. Read the selected label, especially for theme queries, which may match a related name.

An unresolved input can produce a normal response with no results. A company outside graph coverage can be skipped while the remaining companies execute. Source status can omit an `ok` row even when some companies execute. Inspect `interpretations`, `coverage`, results and `source_status` together; an empty result alone does not explain what happened. Behavior for mixed ambiguous and resolved inputs needs verification per tool.

For pagination, pass `page.next_cursor` unchanged with the original filters. A zero `requested_limit` can mean the caller omitted the limit; use `effective_limit` to see what was applied.

---

## Find research

`search_insights` returns compact research summaries, newest first by publication date.

| Input | Default or limit |
| --- | --- |
| `subjects` | Optional array of subject objects; matches research about any specified subject |
| `types` | All types; choose `company_catalyst`, `market_catalyst`, `earnings_preview`, `earnings_recap`, `scenario` |
| `from`, `to` | `from`: 30 days before `to`; `to`: now. RFC 3339 timestamps or dates. |
| `saved_universe_id`, `saved_universe_type` | Optional saved-list filter |
| `limit` | 20; maximum 50 |
| `cursor` | Previous `page.next_cursor` |
| `language` | Optional BCP-47 code |
| `partial_ok` | `false`; `true` requests results from subjects and sources that can answer |

Date-only `from` starts at 00:00 UTC; date-only `to` includes the end of that day.

`{"subjects": [{"ref": "entity:nvda_nasd"}], "types": ["earnings_recap"], "limit": 5}`

The result array is `insights`. Items contain `ref`, `type`, `title`, `published_at`, and, where applicable, `subtitle`, `sentiment` and `subject_ref`. Scenario summaries have no subtitle or sentiment. Some market catalysts have no subject. Research sentiments include `positive`, `neutral` and `negative`.

Coverage counts each explicit subject once and each saved list once. Theme subjects do not apply to company-specific scenarios; that source is reported as skipped. No matching research with available sources is distinct from unavailable sources.

### Star ratings

The documented `search_insights` inputs do not include a star-rating filter, and the documented search and detail responses do not expose a star-rating field. Do not translate a request such as “7+ stars” into an unsupported parameter or claim to have filtered results by stars. Separate product API filters do not establish support in this MCP interface.

---

## Read full research

`get_insights` retrieves selected research from references returned by search.

| Input | Default or limit |
| --- | --- |
| `refs` | Required; up to 5 `kg:` or `scenario:` references |
| `include` | Applicable groups; choose `summary`, `sections`, `statistics` |
| `language` | Optional BCP-47 code |
| `partial_ok` | `false`; `true` reports missing items in `omitted_refs` |

`{"refs": ["kg:<reference-from-search>"], "include": ["summary", "sections"]}`

The `insights` items repeat summary fields and add `included_field_groups`. Card-based research adds `updated_at` and `sections`; section types include `hero`, `takeaway`, `quotes`, `details_grid`, `graph` and `geo`. Their content can include badges, takeaways, theme tags, key figures, ranked peer tables and country cards. Sections and counts vary by research type; do not require every section or assume an empty section is a rights restriction.

Scenario items instead add `scenario`, including `entity_tag`, `best_horizon` and, when requested, `forecasts` with `date`, `median`, `low` and `high`. The captured values resemble price levels; units and currency remain unconfirmed. Scenario items have no `updated_at` field. Full-content sentiment values can also include `mixed` and `warning` on country cards, or be blank; do not assume every card uses the summary sentiment values.

Coverage counts references. There is no pagination; batch requests above five references. An unknown reference fails with `SUBJECT_NOT_FOUND` by default. With partial retrieval, reasons can include `not_found` and `upstream_unavailable`. A non-applicable field group can be absent without an omission note; the precise behavior for rights or response-budget restrictions remains unverified.

The earnings reporting period appears in the title or text, not a separate field. Preserve it separately from `published_at` and `updated_at`.

### Scenario direction and sentiment

The current documented scenario detail contains the security identifier, best horizon, and available forecast points. It does not define a dedicated bullish/bearish direction field.

Sentiment is a separate optional insight field. Do not assume it is present on every scenario or that it is interchangeable with scenario direction.

If the response does not provide the requested direction, report it as unavailable. Do not infer a bullish or bearish label from the title alone.

Knowledge Graph `exposure_direction` describes a different concept and should not be substituted.

---

## Company profile and exposures

`get_company_relationships` returns relationships for one or more companies.

| Input | Default or limit |
| --- | --- |
| `securities` | Optional array of security objects; alternative to a saved list |
| `saved_universe_id`, `saved_universe_type` | Optional saved-list filter |
| `relationship_types` | All six: `theme`, `macro_theme`, `financial_theme`, `product`, `country`, `region` |
| `limit` | 20 edges; maximum 50 |
| `cursor`, `language` | Optional |
| `partial_ok` | `false`; server description says unresolved inputs block execution and return candidates |

`{"securities": [{"query": "NVIDIA", "exchange": "NASD"}], "relationship_types": ["theme"]}`

The `relationships` array contains `ref`, `type`, `source`, `target` and `rank`. Source identifies the company with its reference, label, ticker and exchange; target identifies the related theme, product or geography. Financial and macro themes add `exposure_direction`: `positive`, `negative` or `neutral`.

Rank starts at 1 within each company's relationship type. Results are ordered by company, type and rank; use a type filter to focus the answer. Descriptions and evidence require a separate request with the returned `rel:` references. Suppliers and customers are not separate relationship types in this interface.

Coverage counts securities, including each member of a saved list. A company outside graph coverage can be marked skipped without blocking other companies.

---

## Competitors

`get_company_competitors` returns ranked competitors for one or more companies.

| Input | Default or limit |
| --- | --- |
| `securities` | Optional array of security objects |
| `saved_universe_id`, `saved_universe_type` | Optional saved-list filter |
| `limit` | 20 competitors; maximum 50 |
| `cursor` | Optional |
| `partial_ok` | `false` |

`{"securities": [{"ref": "entity:nvda_nasd"}, {"ref": "entity:amd_nasd"}], "limit": 10}`

The `competitors` array contains company `ref`, `label`, `ticker`, `exchange`, `rank`, `competitor_of` and `refs`. `competitor_of` identifies the requested companies using bare company tags. `refs` contains the relationship references used to request evidence.

Shared competitors appear once. Their combined-list rank is not necessarily their rank against every requested company; evidence responses carry the individual relationship ranks. Results contain no description or theme list.

Coverage counts securities, including saved-list members. Outside-coverage companies can be skipped. The behavior for ambiguous inputs or combining explicit securities with a saved list needs verification. This tool has no `language` parameter.

---

## Companies in a theme

`find_theme_companies` returns companies associated with a selected theme.

| Input | Default or limit |
| --- | --- |
| `theme` | Required subject object: theme query or exact `theme:` reference |
| `securities` | Optional filter to selected companies |
| `saved_universe_id`, `saved_universe_type` | Optional saved-list filter; this route still needs verification |
| `limit` | 20 companies; maximum 50 |
| `cursor`, `language` | Optional |
| `partial_ok` | `false` |

`{"theme": {"query": "Artificial Intelligence", "kind": "theme"}, "limit": 20}`

The `relationships` array uses the edge shape above, with the theme as `source` and company as `target`. The selected theme is reported in `interpretations`. Its matching `score` is an internal match score, not an exposure measure.

Filtering a company list preserves the companies' ranks in the full theme ranking. A company may resolve successfully but have no returned relationship; do not convert that absence into a measured exposure of zero. Coverage counts the theme plus each filter security. Financial-theme responses can also include `exposure_direction`.

The underlying industry methodology distinguishes a company's strongest themes from companies' importance to a theme. The exact mapping from that methodology to each deployed response still needs confirmation; see [Coverage and sources](../../research/coverage-and-sources/README.md).

---

## Evidence behind a relationship

`get_relationship_evidence` expands relationship references returned by company, competitor or theme lookups.

| Input | Default or limit |
| --- | --- |
| `refs` | Required; up to 10 service-issued `rel:` references |
| `language` | Optional |
| `partial_ok` | `false`; the server describes omitted-reference reporting when `true` |

`{"refs": ["rel:<reference-from-a-lookup>"]}`

The `evidence` array repeats the edge's identifiers, type, rank and any exposure direction, then adds `description`. `source_evidence` and `document_ids` may also be present. Competitor relationships can return a description without those supporting fields. Document identifiers are opaque; this connection provides no tool to turn them into a source title or URL.

Coverage counts references. There is no pagination. More than ten references or a reference not issued by the service fails with `INVALID_INPUT`; `partial_ok` does not make an invalid reference acceptable. Stale-reference and upstream-failure behavior still needs verification.

---

## Watchlists and baskets

Omitting types requests both watchlists and baskets. To return only personal watchlists, set types to ["watchlist"]. To return only shared baskets, set types to ["basket"]. Present the two categories separately when reporting totals.

| Input | Default or limit |
| --- | --- |
| `types` | Both `watchlist` and `basket`; optionally restrict the array |
| `limit` | 25; maximum 100; zero selects the default |
| `cursor` | Optional |
| `partial_ok` | `false`; `true` requests available families if one source fails |

The `universes` array contains `type`, `id`, `name` and `count`. This listing does not return member securities. Pass its ID and type to another tool to request research across the list; those results can identify the companies researched.

Coverage counts list families: one for watchlists, one for baskets. This tool has no `language` parameter. An empty list with a normal response is not itself a sign-in failure. Inspect source status before claiming all lists were available.

---

## Errors and partial results

Errors are MCP tool errors rather than normal response envelopes. They use text of the form `[CODE] message`. Recorded validation cases include:

| Code | Cause |
| --- | --- |
| `INVALID_INPUT` | Too many detail/evidence references, invalid relationship references, or a date window whose start follows its end |
| `SUBJECT_NOT_FOUND` | Unknown research reference with partial retrieval disabled |
| `UNAUTHORIZED` / HTTP 401 | Plugin setup describes this as missing or expired sign-in |
| `FORBIDDEN` / HTTP 403 | Plugin setup describes this as an account without research access |

The last two outcomes come from plugin guidance and still need a recorded production account test. Rate-limit, expiry, rights-restriction and response-budget error behavior is not yet established. Do not infer the cause of a missing item from an error code that was not returned.

### Authentication and connection recovery

A successful browser authentication does not establish that the host has discovered the tools or can execute a tool call. Verify discovery and a successful call separately. A normal empty `list_saved_universes` response can confirm a successful call; a timeout or unavailable source cannot.

Testing has surfaced invalidated connections, missing tools after authentication, and expiry-related reconnection failures. A reported Cursor diagnostic included “refresh_token grant not yet implemented”; the cause and scope require engineering verification. Do not treat all timeouts as network failures or assume automatic token refresh is reliable across hosts.

For user recovery steps, see Troubleshooting. Record the host version, installation route, exact error, and whether reauthentication restores tool calls when investigating failures.

---

## Languages and limits

`language` is best effort on the five tools that accept it. Content without a translation may remain in English, without a fallback flag. Supported languages and coverage need product confirmation.

Pagination limits count the tool's result objects, not universally companies. Detail batching, pagination and source availability are separate concerns. Rate limits, quotas, token lifetimes and maximum response sizes remain unconfirmed.

---

← [Reference](../README.md)
