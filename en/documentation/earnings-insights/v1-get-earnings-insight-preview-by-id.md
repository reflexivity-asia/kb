<!--
id: RX-PRODUCT-1054
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# V1 Get earnings insight preview by ID

[← Documentation](../README.md)
Returns a detailed preview for a specific earnings insight.

### Header Parameters
Accept-Language string An IETF BCP 47 language tag specifying the language preference for the response content. When provided, the API will return insight text (titles, descriptions, KPIs, themes, etc.) in the requested language. Defaults to `en` if the header is omitted. Returns `404` if the requested language is not available for the insight.
Currently supported languages: `ar`, `de`, `en`, `fr`, `he`, `hu`, `it`, `ja`, `ko`, `nl`, `pt`, `ru`, `es`, `zh-Hans`, `zh-Hant`.

### Path Parameters
id string (uuid) Required The unique ID of the earnings insight preview.

## Response Expand all
200 Object Successful response with detailed earnings insight preview

### Response Attributes
id string (uuid) type string Enum values: `preview` entity_tag string earnings_id string title string created_at string (date-time) updated_at string (date-time) expectation string historical_context array Show child attributes

seasonality array Show child attributes

kpis array Show child attributes

themes array Show child attributes

other_themes array Show child attributes

key_items array Show child attributes

investment_outlook object Show child attributes

impacted_companies array Show child attributes

citations array Show child attributes

404 Object Insight not found, or the requested language is not available for this insight.

## Request and response example

GET

/earnings-insights/v1/preview/{id}

cURL `1 curl --location --globoff 'https://api.reflexivity.com/earnings-insights/v1/preview/{id}' \` Try in API Explorer
### Response
200 404 `{ "id" : "96325f3e-b899-432d-89b7-ef0aa86bb0e4" , "type" : "preview" , "entity_tag" : "cost_nasd" , "earnings_id" : "e8d43c75-2101-4701-a9b9-453d4bad31b4" , "title" : "Costco Wholesale Q4 Earnings: Continued Sales Momentum, Margin Expansion, Digital Growth, and Membership Fee Impact in Focus" , "created_at" : "2025-10-07T17:29:22Z" , "updated_at" : "2025-10-07T17:29:22Z" , "expectation" : "Current consensus EPS estimate: $5.79 to $5.81. Current consensus revenue estimate: $62.93B (range: $62.9B to $63.2B). Unique factors creating heightened expectations include tariff mitigation efforts, digital commerce innovations like buy now, pay later, and an expanding warehouse footprint." , "historical_context" : [ "Costco's Q3 FY2025 results exceeded EPS and revenue estimates" , " with diluted EPS of $4.28 and revenue of $63.21 billion." , "Comparable store sales grew 5.7% globally (8.0% adjusted for gasoline and FX)" , " and e-commerce sales surged 14.8%." ] , "seasonality" : [ "This quarter may be influenced by inflation trends" , " holiday season ramp-up" , " and additional warehouse openings" , "A significant factor for this release is the membership fee increase implemented on September 1" , " 2024" , " expected to boost FY25 operating profits" ] , "kpis" : [ { "title" : "Comparable Store Sales" , "description" : "Indicates organic demand and pricing power; reflects health of core retail business, customer traffic, and spending habits; impacts revenue and investor confidence." , "value" : "5.7% growth in Q4 2025 (8.0% in Q3 2025 excluding gas/FX); U.S. comps at 5.1%, Canada at 6.3%, and international markets at 8.6%" } , { "title" : "Membership Fee Income" , "description" : "High-margin, predictable revenue stream crucial to profitability; growth and high renewal rates underscore customer loyalty and earnings stability." , "value" : "$1.24 billion (10.4% YoY growth); global renewal rates at 90.2%; U.S. and Canada renewal rates at 92.7%" } , { "title" : "Gross Margin" , "description" : "Reflects efficiency in managing costs and pricing power; maintaining or expanding margins indicates profitability amidst inflation and competition." , "value" : "11.25% in Q3 2025 (up 41 basis points YoY, 29 basis points excluding gas deflation); 13.2% for fiscal year 2024" } ] , "themes" : [ { "theme_id" : "b7e6e2c2-1f2a-4c3b-9e7d-2a4b6e2c2f1a" , "rating" : "positive" , "relationship" : "Industry" } , { "theme_id" : "e8d43c75-2101-4701-a9b9-453d4bad31b4" , "rating" : "neutral" , "relationship" : "Industry" } , { "theme_id" : "96325f3e-b899-432d-89b7-ef0aa86bb0e4" , "rating" : "positive" , "relationship" : "Financial" } , { "theme_id" : "a1b2c3d4-e5f6-7890-abcd-ef1234567890" , "rating" : "neutral" , "relationship" : "Financial" } , { "theme_id" : "f1e2d3c4-b5a6-7890-cdef-1234567890ab" , "rating" : "neutral" , "relationship" : "Macro" } ] , "other_themes" : [ { "name" : "Digital Commerce Innovation" , "type" : "Technology" , "rating" : "positive" , "relationship" : "Industry" } , { "name" : "International Expansion" , "type" : "Strategic" , "rating" : "positive" , "relationship" : "Industry" } ] , "key_items" : [ "Q4 guidance on comparable sales" , " margin trends" , " and warehouse openings will be important." , "Potential new product categories" , " private-label expansion (Kirkland Signature)" , " or strategic partnerships could signal future growth opportunities." , "Updates on digital initiatives" , " including \"Buy Now" , " Pay Later\" adoption" , " personalization efforts" , " e-commerce sales figures" , " and international site growth" , " are anticipated." , "Oppenheimer projects EPS slightly below consensus due to higher costs from Executive Member extra hours and difficult comparisons in non-food categories." ] , "investment_outlook" : { "base_case" : "Earnings and revenue align with consensus as balances inflation and tariff challenges, supported by stable digital sales and membership income, with Q4 results solid but in line. Membership fee increases boost profitability, while steady comparable sales and modest margin pressures result in gradual stock appreciation." , "bear_case" : "Sluggish consumer spending, supply disruptions, or underperformance in digital growth and membership renewals pressure comps and margins, resulting in missed key metrics and cautious management outlook. Competition, cost pressures, and supply chain concerns weigh on sentiment, causing a notable stock pullback." , "bull_case" : "Strong consumer demand, warehouse expansion, and e-commerce growth drive earnings and margin upside, with Q4 results exceeding expectations due to robust comparable sales and membership fee accretion, leading to a significant stock re-rating. Management's optimistic FY26 outlook highlights international expansion and effective cost management." } , "impacted_companies" : [ { "entity_tag" : "wmt_nyse" , "earnings_id" : "b7e6e2c2-1f2a-4c3b-9e7d-2a4b6e2c2f1a" , "rating" : "neutral" , "description" : "Direct Competitor - Earnings may be influenced by Costco's pricing and sales trends. Strong results could indicate a healthy consumer environment benefiting Costco, while weak results might suggest broader retail challenges." , "relationship" : "Direct Competitor" } , { "entity_tag" : "tgt_nyse" , "earnings_id" : "a1b2c3d4-e5f6-7890-abcd-ef1234567890" , "rating" : "neutral" , "description" : "Direct Competitor - Target's Q4 performance offers insights into consumer discretionary spending and operational efficiency. Strong performance could signal robust consumer demand aiding Costco, while weakness might imply a challenging retail landscape." , "relationship" : "Direct Competitor" } , { "entity_tag" : "amzn_nasd" , "earnings_id" : "96325f3e-b899-432d-89b7-ef0aa86bb0e4" , "rating" : "neutral" , "description" : "Thematic Overlap/Direct Competitor - Amazon's e-commerce performance highly relevant to Costco's digital strategy and online retail trends. Strong growth at Amazon could validate Costco's strategy, while slower growth might indicate a broader slowdown in online retail." , "relationship" : "Direct Competitor" } , { "entity_tag" : "bj_nyse" , "earnings_id" : "f1e2d3c4-b5a6-7890-cdef-1234567890ab" , "rating" : "neutral" , "description" : "Direct Competitor - BJ's results provide the most direct competitive context to Costco's model. A strong showing from BJ's would suggest strength in the warehouse club model, while underperformance could highlight specific challenges." , "relationship" : "Direct Competitor" } ] , "citations" : [ { "title" : "Costco Wholesale Q4 2025 Earnings Preview" , "url" : "https://example.com/costco-q4-preview" } , { "title" : "Warehouse Club Market Analysis" , "url" : "https://example.com/warehouse-club-analysis" } ] }` Show more
