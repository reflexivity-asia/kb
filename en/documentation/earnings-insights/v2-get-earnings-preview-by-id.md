<!--
id: RX-PRODUCT-1051
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# V2 Get earnings preview by ID

[← Documentation](../README.md)
Returns detailed preview for a specific earnings insight including scenarios, price targets, KPIs, themes, and impacted companies. Generated before earnings are reported.

### Header Parameters
Accept-Language string An IETF BCP 47 language tag specifying the language preference for the response content. When provided, the API will return insight text (titles, descriptions, KPIs, themes, etc.) in the requested language. Defaults to `en` if the header is omitted. Returns `404` if the requested language is not available for the insight.
Currently supported languages: `ar`, `de`, `en`, `fr`, `he`, `hu`, `it`, `ja`, `ko`, `nl`, `pt`, `ru`, `es`, `zh-Hans`, `zh-Hant`.

### Path Parameters
id string (uuid) Required The unique ID of the earnings insight preview.

## Response Expand all
200 Object Successful response with detailed earnings preview

### Response Attributes
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

## Request and response example

GET

/earnings-insights/v2/preview/{id}

cURL `1 curl --location --globoff 'https://api.reflexivity.com/earnings-insights/v2/preview/{id}' \` Try in API Explorer
### Response
200 404 `{ "id" : "d54f6a89-0969-4e86-a90e-0cca8dd1833e" , "type" : "preview" , "title" : "Micron Technology Q1 2026 Earnings: AI-Driven Demand Drives Record Revenue, HBM Momentum and $18B Capex Guidance in Focus" , "company" : { "name" : "MICRON TECHNOLOGY" , "ticker" : "mu" , "isin" : "US5951121038" , "exchange" : "nasd" } , "earnings" : { "fiscal_year" : "2026" , "fiscal_period" : "Q1" , "reporting_date" : "2025-12-17T21:01:00Z" , "estimated_eps" : 3.82 , "estimated_eps_yoy" : 117.05 , "actual_eps" : 4.78 , "actual_eps_yoy" : 167.04 , "estimated_revenue" : 12811151742 , "estimated_revenue_yoy" : 46.92 , "actual_revenue" : 13643000000 , "actual_revenue_yoy" : 56.65 , "surprise_eps" : 0.96 , "surprise_eps_yoy" : 25.13 , "surprise_revenue" : 831848256 , "surprise_revenue_yoy" : 6.49 } , "price_targets" : { "low" : 86.28 , "avg" : 249.37 , "high" : 362 } , "beats_scenario" : { "episodes" : 47 , "data" : [ { "index" : -2 , "low" : -0.02660409513058055 , "median" : -0.02309574009815022 , "high" : 0.017472362332425728 } , { "index" : -1 , "low" : -0.01857184218363539 , "median" : -0.011527967741193348 , "high" : 0.01905837642452313 } , { "index" : 0 , "low" : 0 , "median" : 0 , "high" : 0 } ] } , "misses_scenario" : { "episodes" : 7 , "data" : [ { "index" : -2 , "low" : 0.011275386450848846 , "median" : 0.014040791749869452 , "high" : 0.029284525603382603 } , { "index" : -1 , "low" : -0.007637250913683145 , "median" : -0.0006603535277546445 , "high" : 0.022889335755638753 } , { "index" : 0 , "low" : 0 , "median" : 0 , "high" : 0 } ] } , "sentiment_expectations" : [ "Expectations appear stretched due to a 190% year-to-date stock rally, 85% rise in the last three months, and upward EPS estimate revision of +3.65% in the past 30 days." , "Heightened expectations stem from surging demand for HBM and DRAM, tight supply, favorable pricing, and a streak of four consecutive EPS beats, including a +9.39% surprise in Q4 2025." ] , "seasonality" : [ "Fiscal year 2026 will be a 53-week year compared to 52 weeks in 2025." , "Q1 2026 is expected to show record revenue, strong gross margins, and significantly higher free cash flow year-over-year." ] , "kpis" : [ { "title" : "Revenue" , "description" : "Indicates overall demand for memory and storage products, particularly driven by AI applications, and is a primary growth driver" , "value" : "$12.54B - $12.82B (+44% YoY)" } , { "title" : "Non-GAAP Diluted EPS" , "description" : "Measures profitability and operational efficiency, reflecting pricing power and investor confidence" , "value" : "$3.75 - $3.93 (+114% YoY)" } ] , "key_items_to_watch" : [ "Q1 2026 guidance includes revenue of $12.50 billion ± $300 million and non-GAAP diluted EPS of $3.75 ± $0.15." , "Gross margin guidance for Q1 2026 is 51.5% ± 1.0%." ] , "investment_outlook" : { "base_case" : "Meets or slightly exceeds Q1 2026 guidance, driven by strong execution in AI memory, with HBM and DRAM as key growth drivers. Shares trade flat to +5% as confidence in strategic positioning and memory supercycle continues." , "bear_case" : "Misses Q1 2026 guidance due to softer memory demand, competition, or production issues, with a cautious outlook raising concerns about the memory upcycle. Stock drops 10-20%, testing recent gains if guidance falls below $18B." , "bull_case" : "Surpasses elevated Q1 2026 guidance due to strong HBM demand and pricing, with FY2026 capex reaffirmed at $18B, signaling AI-driven growth and margin expansion. Stock rallies 10-15%, potentially reaching $300+ as DRAM tightness persists." } , "themes" : [ { "id" : "2909994c-f29d-43cb-b385-e55bd033e3aa" , "type" : "industry" , "name" : "AI Chips" , "description" : "Specially designed microchips optimized for executing artificial intelligence algorithms, critical for enhancing computational efficiency and processing power in AI applications." , "rating" : "positive" , "relationship" : "AI-driven HBM demand is pulling capacity away from standard DRAM, tightening supply and lifting prices, with HBM capacity constraints supporting pricing power." } , { "id" : "6d952a1a-e964-44d3-b05b-e4b2e0b1c8bf" , "type" : "industry" , "name" : "Data Centers" , "description" : "Centralized facilities housing computing resources, networking equipment, and storage systems for large-scale data processing." , "rating" : "positive" , "relationship" : "Ongoing global build-out of data centers to support AI applications is a multi-year driver for memory and storage demand, with Micron's data center business reaching 56% of total revenue in fiscal 2025." } ] , "other_themes" : [ { "name" : "Margin Expansion" , "type" : "Financial" , "rating" : "positive" , "relationship" : "Strong demand for high-value AI products, particularly HBM, drove Q4 2025 gross margin expansion by 17 percentage points to 41%, with Q1 2026 guidance at over 50%." } ] , "impacted_companies" : [ { "name" : "NVIDIA Corporation" , "ticker" : "nvda" , "isin" : "US67066G1040" , "exchange" : "nasd" , "rating" : "positive" , "impact_description" : "GPUs drive HBM demand for AI. Strong Micron results, especially in HBM, confirm high AI infrastructure demand, benefiting NVIDIA via continued AI accelerator sales." , "company_relationship" : "Customer/Partner" } , { "name" : "Advanced Micro Devices Inc." , "ticker" : "amd" , "isin" : "US0079031078" , "exchange" : "nasd" , "rating" : "positive" , "impact_description" : "Data center GPUs rely on Micron DRAM/HBM. Q4-2025 Micron beats correlate with AMD's +3% reaction on shared AI tailwinds." , "company_relationship" : "Customer" } ] , "created_at" : "2025-12-14T05:05:08Z" }` Show more
