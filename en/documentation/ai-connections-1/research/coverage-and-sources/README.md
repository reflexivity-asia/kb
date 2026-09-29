<!--
id: RX-PRODUCT-1098
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6aac3a4650675fa0b9e89755
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: ai-connections-1/research/coverage-and-sources
-->
# Coverage and Sources

---

### Available research

Insights contains earnings recaps, earnings previews, company catalysts, market catalysts and scenario insights. Knowledge Graph covers company relationships, including themes, products, countries, regions and competitors. Availability varies by company, theme, research type and period.

Searches default to the last 30 days. Specify a longer period to find older research. Add an exchange when a company name or ticker is ambiguous. Theme searches match Reflexivity's defined themes, so check the theme selected in the answer.

### Filters and output limitations

The documented research MCP interface supports filtering by subject, research type, saved watchlist or basket, and date range. It does not expose a star-rating filter or a returned star-rating field. A request such as “7+ star insights” therefore cannot be reliably filtered through this connection.

The MCP interface and separate Reflexivity product APIs do not necessarily expose the same fields or filters. Use the [MCP tool reference](../../reference/mcp-tool-reference/README.md) for this connection’s supported inputs.

Your AI application controls how it presents the returned information. Answer length, tables, and visual output can vary. Ask for the format and level of detail you need, and keep unavailable evidence or unsupported visual formats explicit.

---

### Three kinds of themes

Title Description Title Theme

What it describes

Examples

Industry

What a company does: its products, services, capabilities and role in the economy.

AI Chips, Renewable Energy

Financial

The company's financial condition, operating performance and management decisions.

Revenue Growth, Capital Allocation

Macro

External forces affecting the company.

Interest Rate Changes, Tariff Implementations

A theme relationship indicates documented exposure. It does not establish that a company is an attractive investment.

---

### Rankings and direction

A company's theme ranking asks which themes matter most to this company? Rank 1 is its strongest relationship within that theme group.

The industry-theme company ranking asks which companies matter most to this theme? These rankings are assessed independently. A theme can be central to a small company's business while that company plays a smaller role in the theme overall. Do not treat the two rankings as interchangeable.

Ranks describe relative relationships. They are not revenue percentages, probabilities or return forecasts. The connection's documented results provide ranks, not the numeric weights described in the underlying methodology.

Financial and macro exposures also have a direction:

- Positive: the evidence indicates a favourable effect on the company.

- Negative: the evidence indicates an unfavourable effect.

- Neutral: effects are mixed, offsetting, non-directional or unclear.
Direction depends on the company. Industry themes have no positive or negative direction.

---

### Where the evidence comes from

Company-theme relationships are established from primary company disclosures, including annual and quarterly filings, earnings-call transcripts, reports and presentations. Relationships reflect supporting evidence across disclosures, with greater influence from recent material.

The connection can return relationship descriptions, supporting text and document identifiers. Available detail varies; some relationships return a description only. Document identifiers are not clickable source links. Published research carries a Reflexivity reference and dates; an original source document is not guaranteed in the answer.

---

### Dates and missing results

Keep three dates separate: the reporting period covered by an earnings report, its publication date , and its last-updated date . The reporting period appears in the title or text. A recent update does not make a report the latest quarter. The response's as-of timestamp is not a research publication date or a guarantee that the underlying content has just refreshed.

An empty search with all sources available means no matching research was returned for that search. An unavailable source or omitted item means part of the request could not be completed. Ask for missing results to be identified before drawing conclusions.

See [Research examples](..//README.md), [Troubleshooting](../../help/troubleshooting/README.md) or the [MCP tool reference](../../reference/mcp-tool-reference/README.md).

---

[← Documentation](../../../README.md)
