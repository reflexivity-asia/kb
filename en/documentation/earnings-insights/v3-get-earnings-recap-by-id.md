<!--
id: RX-PRODUCT-1049
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# V3 Get earnings recap by ID

[← Documentation](../README.md)
Returns detailed recap for a specific earnings insight including actual results, KPIs, peer comparisons, risk assessments, themes, and citations. Generated after earnings are reported. Unlike v2, all themes are returned in a single `themes` array (each catalog-backed with an `id`) and there is no `other_themes` field.

### Header Parameters
Accept-Language string An IETF BCP 47 language tag specifying the language preference for the response content. When provided, the API will return insight text (titles, descriptions, KPIs, themes, etc.) in the requested language. Defaults to `en` if the header is omitted. Returns `404` if the requested language is not available for the insight.
Currently supported languages: `ar`, `de`, `en`, `fr`, `he`, `hu`, `it`, `ja`, `ko`, `nl`, `pt`, `ru`, `es`, `zh-Hans`, `zh-Hant`.

### Path Parameters
id string (uuid) Required The unique ID of the earnings insight recap.

## Response Expand all
200 Object Successful response with detailed earnings recap

### Response Attributes
id string (uuid) type string Enum values: `recap` title string company object Show child attributes

earnings object Show child attributes

key_metrics string guidance_update string price_scenario object Show child attributes

kpis array Show child attributes

peer_comparison_sector_context array Show child attributes

risk_assessment_update array Show child attributes

themes array Show child attributes

impacted_companies array Show child attributes

citations array Show child attributes

created_at string (date-time) 404 Object Insight not found, or the requested language is not available for this insight.

## Request and response example

GET

/earnings-insights/v3/recap/{id}

cURL `1 curl --location --globoff 'https://api.reflexivity.com/earnings-insights/v3/recap/{id}' \` Try in API Explorer
### Response
200 404 `{ "id" : "efeda7b8-4c8f-425f-bbd5-39042e061908" , "type" : "recap" , "title" : "Micron Technology Q1-2026 Earnings: Record Revenue and EPS Driven by AI Data Center Demand, Strong Guidance Validates Momentum" , "company" : { "name" : "MICRON TECHNOLOGY" , "ticker" : "mu" , "isin" : "US5951121038" , "exchange" : "nasd" } , "earnings" : { "fiscal_year" : "2026" , "fiscal_period" : "Q1" , "reporting_date" : "2025-12-17T21:01:00Z" , "estimated_eps" : 3.82 , "estimated_eps_yoy" : 117.05 , "actual_eps" : 4.78 , "actual_eps_yoy" : 167.04 , "estimated_revenue" : 12811151742 , "estimated_revenue_yoy" : 46.92 , "actual_revenue" : 13643000000 , "actual_revenue_yoy" : 56.65 , "surprise_eps" : 0.96 , "surprise_eps_yoy" : 25.13 , "surprise_revenue" : 831848256 , "surprise_revenue_yoy" : 6.49 } , "key_metrics" : "Revenue reached a record $13.64 billion in Q1 2026, representing a 56.6% year-over-year increase and surpassing analyst expectations of $12.8-$12.9 billion. Non-GAAP diluted EPS came in at $4.78, significantly exceeding consensus estimates of $3.8-$3.96 and the prior quarter's $3.03. Operating cash flow also saw a sharp rise, reaching $8.41 billion compared to $5.73 billion in the prior quarter." , "guidance_update" : "Q2 fiscal 2025 revenue is forecasted at $7.90 billion (± $200 million) with EPS at $1.43 (± $0.10), reflecting expected declines in DRAM and NAND revenue driven by oversupply and weak consumer demand. In contrast, fiscal Q2 2026 revenue guidance is set at $18.7 billion (± $400 million), supported by robust AI and data-center memory demand." , "price_scenario" : { "episodes" : 1 , "data" : [ { "index" : -2 , "low" : 0.053121674352607284 , "median" : 0.053121674352607284 , "high" : 0.053121674352607284 } , { "index" : -1 , "low" : 0.030995033699893426 , "median" : 0.030995033699893426 , "high" : 0.030995033699893426 } , { "index" : 0 , "low" : 0 , "median" : 0 , "high" : 0 } ] } , "kpis" : [ { "title" : "Revenue" , "description" : "Outperformed analyst estimates of $12.8-$12.9 billion and set a new record, driven by AI/data-center demand and higher DRAM/HBM pricing. Outperformed sector peers reporting weaker memory prints." , "rating" : "positive" , "value" : "$13.64 billion (56.6% YoY growth)" } , { "title" : "Non-GAAP Diluted EPS" , "description" : "Reflects strong operational efficiency, favorable product mix, and high-margin AI-centric memory. Significantly outperformed consensus." , "rating" : "positive" , "value" : "$4.78 (exceeded expectations of $3.8-$3.96)" } ] , "peer_comparison_sector_context" : [ "Micron's revenue, EPS, and cash flow are among the strongest in the semiconductor memory sector this earnings season, outpacing peers in margin expansion." , "Gross margin guidance exceeding 50% highlights superior pricing and product mix, particularly in the high-value HBM segment." ] , "risk_assessment_update" : [ "Increasing capital expenditure plans for fiscal 2026 could pose a risk if demand softens or execution challenges arise in ramping up new facilities." , "Execution risk on rapid capacity scaling for HBM/advanced DRAM and elevated capex requirements could pressure returns if demand growth slows." , "Upcoming Catalysts: Successful ramp of HBM4 in 2026 and HBM4E in 2027/2028 is a critical catalyst for maintaining competitiveness and market share." ] , "themes" : [ { "id" : "6d952a1a-e964-44d3-b05b-e4b2e0b1c8bf" , "type" : "industry" , "name" : "Data Centers" , "description" : "Centralized facilities housing computing resources, networking equipment, and storage systems for large-scale data processing." , "rating" : "positive" , "relationship" : "Micron's record Q1 2026 revenue and strong guidance are primarily driven by accelerated demand from AI data centers, with the data center business accounting for a significant portion of total revenue." } , { "id" : "a1b2c3d4-e5f6-7890-abcd-ef1234567890" , "type" : "financial" , "name" : "Margin Expansion" , "description" : "Sustained improvement in profit margins driven by favorable product mix, pricing power, and operating leverage." , "rating" : "positive" , "relationship" : "Gross margins are guided to exceed 50% in Q2 2026, indicating strong pricing power and a favorable product mix, especially in high-value memory." } , { "id" : "f1e2d3c4-b5a6-7890-cdef-1234567890ab" , "type" : "macro" , "name" : "Semiconductor Supply Cycle" , "description" : "The cyclical pattern of supply and demand imbalances across the semiconductor industry that drives pricing and capacity decisions." , "rating" : "positive" , "relationship" : "Tight memory supply and recovering demand across DRAM and NAND are pushing pricing higher, with analysts expecting strength to persist for multiple quarters." } ] , "impacted_companies" : [ { "name" : "NVIDIA Corporation" , "ticker" : "nvda" , "isin" : "US67066G1040" , "exchange" : "nasd" , "rating" : "positive" , "impact_description" : "Revenue from largest data center customer accounted for approximately 13% of total company revenue, driven by HBM supply for AI training" , "company_relationship" : "Direct customer/AI infrastructure partner" } , { "name" : "Advanced Micro Devices Inc." , "ticker" : "amd" , "isin" : "US0079031078" , "exchange" : "nasd" , "rating" : "positive" , "impact_description" : "Gains from Micron's HBM and data center DRAM, supporting AI accelerators competing with NVIDIA" , "company_relationship" : "Direct customer/AI chip competitor" } ] , "citations" : [ { "title" : "247wallst.com" , "url" : "https://247wallst.com/investing/2025/12/17/why-wall-street-expects-micron-to-crush-earnings-today-and-its-stock-to-surge-again/" } , { "title" : "Events & Presentations - Micron Investor Relations" , "url" : "https://investors.micron.com/events-and-presentations" } , { "title" : "Micron Technology (MU) Q1 2025 Earnings Call Transcript @themotleyfool #stocks $MU" , "url" : "https://www.fool.com/earnings/call-transcripts/2024/12/18/micron-technology-mu-q1-2025-earnings-call-transcr/" } ] , "created_at" : "2025-12-17T21:22:21Z" }` Show more
