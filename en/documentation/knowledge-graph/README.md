<!--
id: RX-PRODUCT-1065
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f233552
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: knowledge-graph
-->
# Knowledge Graph

🧠 Overview

Reflexivity is powered by our proprietary Knowledge Graph - a self-learning network that identifies and tracks the most important relationships in financial markets. The graph ingests and processes unstructured data from corporate filings, earnings transcripts, investor presentations, government databases, news, and other relevant sources. Textual data is augmented with relevant structured data that may impact an asset.

The core function of our graph is to provide the most comprehensive analysis of the exposure profile for a given company.

Six core relationship types are covered:

- Company → Theme (bottoms-up) : How companies are exposed to a universe of industry themes

- Theme → Company (top-down) : Which companies provide the most exposure to a given industry theme

- Company → Country : Evaluates a company’s country exposure

- Company → Region : Evaluates a company’s regional exposure

- Company → Company (Competitors) : Identifies the most important direct and indirect competitive relationships for a given company

- Company → Product/Brand : Measures the most important products, brands, and services associated with a given company
Each of these relationship sets is covered by its own API endpoint.

For all company outbound relationship types, the graph coverage consists of ~3500 US companies. All publicly traded global companies are eligible and supported in our theme-to-company relationship set.

Themes are granular business segments, product categories, technologies, and end-markets (i.e. "electric vehicles", "cloud infrastructure", and "rare earth elements") that represent specific revenue drivers and operational exposures across companies.

Our theme universe is dynamic and consists of ~500 industry themes. Each industry theme is classified into one of 19 parent categories.

All graph relations are supported by an underlying ranking which represents the statistical significance of a given relationship. An overview of the methodology used for each relationship set is provided below.

🔐 Authentication

To authenticate for the respective environment, refer to the [Authentication](../README.md) page of the docs. For any questions, please reach out to [support@reflexivity.com](mailto:support@reflexivity.com)

## Sections

- [🏷️ Company → Theme](company-theme/README.md) — `GET`
- [🎯 Theme → Company](theme-company/README.md) — `GET`
- [🌍 Company → Country](company-country/README.md) — `GET`
- [🌍 Company → Region](company-region/README.md) — `GET`
- [Company → Company (Competitors)](company-company-competitors/README.md) — `GET`
- [Company → Product/Brand](company-product/README.md) — `GET`
- [Legacy](legacy/README.md)

---

[← Documentation](../README.md)
