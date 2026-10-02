<!--
id: RX-PRODUCT-1055
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# V1 Get earnings insight recap by ID

[← Documentation](../README.md)
Returns a detailed recap for a specific earnings insight.

### Header Parameters
Accept-Language string An IETF BCP 47 language tag specifying the language preference for the response content. When provided, the API will return insight text (titles, descriptions, KPIs, themes, etc.) in the requested language. Defaults to `en` if the header is omitted. Returns `404` if the requested language is not available for the insight.
Currently supported languages: `ar`, `de`, `en`, `fr`, `he`, `hu`, `it`, `ja`, `ko`, `nl`, `pt`, `ru`, `es`, `zh-Hans`, `zh-Hant`.

### Path Parameters
id string (uuid) Required The unique ID of the earnings insight recap.

## Response Expand all
200 Object Successful response with detailed earnings insight recap

### Response Attributes
id string (uuid) type string Enum values: `recap` entity_tag string earnings_id string title string created_at string (date-time) updated_at string (date-time) key_metrics string guidance_update string reaction_desc string kpis array Show child attributes

insights array Show child attributes

quotes array Show child attributes

themes array Show child attributes

other_themes array Show child attributes

impacted_companies array Show child attributes

peer_comparison_sector_context array Show child attributes

analyst_and_street_reaction object Show child attributes

risk_assessment_update object Show child attributes

citations array Show child attributes

documents array Show child attributes

404 Object Insight not found, or the requested language is not available for this insight.

## Request and response example

GET

/earnings-insights/v1/recap/{id}

cURL `1 curl --location --globoff 'https://api.reflexivity.com/earnings-insights/v1/recap/{id}' \` Try in API Explorer
### Response
200 404 `{ "id" : "e8d43c75-2101-4701-a9b9-453d4bad31b4" , "type" : "recap" , "entity_tag" : "jbl_nyse" , "earnings_id" : "b7e6e2c2-1f2a-4c3b-9e7d-2a4b6e2c2f1a" , "title" : "Jabil Q4 Earnings Recap: AI-Driven Growth Exceeds Expectations, Strong Guidance Raised" , "created_at" : "2025-10-07T17:29:23Z" , "updated_at" : "2025-10-07T17:29:23Z" , "key_metrics" : "EPS: $3.15 vs. $2.92 consensus (+7.9% beat), Revenue: $7.68B vs. $7.55B consensus (+1.7% beat), Core Operating Margin: 6.8% vs. 6.25% target" , "guidance_update" : "Management raised FY 2026 EPS guidance to $12.50-$13.00 (from $12.00-$12.50) and revenue guidance to $32.0B-$33.0B (from $31.0B-$32.0B), citing strong AI infrastructure demand" , "reaction_desc" : "Stock surged 8.2% in after-hours trading and opened 6.5% higher, driven by strong AI segment performance and raised guidance" , "kpis" : [ { "title" : "EPS Beat" , "description" : "Strong operational leverage and AI segment growth drove significant earnings upside" , "rating" : "positive" , "value" : "$3.15 vs. $2.92 consensus" } , { "title" : "AI Infrastructure Growth" , "description" : "Intelligent Infrastructure segment grew 52% YoY, exceeding expectations" , "rating" : "positive" , "value" : "52% YoY growth vs. 50% expected" } , { "title" : "Margin Expansion" , "description" : "Core operating margin exceeded strategic target, driven by product mix and efficiency" , "rating" : "positive" , "value" : "6.8% vs. 6.25% target" } ] , "insights" : [ { "title" : "AI Infrastructure Leadership" , "description" : "Strong positioning in AI data center infrastructure drives growth and margin expansion" , "rating" : "positive" } , { "title" : "US Manufacturing Investment" , "description" : "$500M Southeast US investment showing early returns with improved supply chain resilience" , "rating" : "positive" } , { "title" : "Operational Excellence" , "description" : "Cost management and efficiency initiatives driving margin improvement" , "rating" : "positive" } ] , "quotes" : [ { "speaker_name" : "Kenny Wilson" , "speaker_title" : "CEO" , "text" : "Our AI infrastructure business continues to exceed expectations, with strong demand from cloud providers and data center operators driving significant growth." , "section_id" : "b7e6e2c2-1f2a-4c3b-9e7d-2a4b6e2c2f1a" } , { "speaker_name" : "Mike Dastoor" , "speaker_title" : "CFO" , "text" : "The $500 million investment in US manufacturing capabilities is already showing returns, improving our supply chain resilience and operational efficiency." , "section_id" : "e8d43c75-2101-4701-a9b9-453d4bad31b4" } ] , "themes" : [ { "theme_id" : "b7e6e2c2-1f2a-4c3b-9e7d-2a4b6e2c2f1a" , "rating" : "positive" , "relationship" : "Industry" } , { "theme_id" : "e8d43c75-2101-4701-a9b9-453d4bad31b4" , "rating" : "neutral" , "relationship" : "Industry" } , { "theme_id" : "96325f3e-b899-432d-89b7-ef0aa86bb0e4" , "rating" : "positive" , "relationship" : "Financial" } , { "theme_id" : "a1b2c3d4-e5f6-7890-abcd-ef1234567890" , "rating" : "neutral" , "relationship" : "Financial" } , { "theme_id" : "f1e2d3c4-b5a6-7890-cdef-1234567890ab" , "rating" : "neutral" , "relationship" : "Macro" } ] , "other_themes" : [ { "name" : "US Manufacturing Investment" , "type" : "Strategic" , "rating" : "positive" , "relationship" : "Macro" } , { "name" : "Cloud Infrastructure Demand" , "type" : "Market" , "rating" : "positive" , "relationship" : "Industry" } ] , "impacted_companies" : [ { "entity_tag" : "flex_nasd" , "earnings_id" : "e8d43c75-2101-4701-a9b9-453d4bad31b4" , "rating" : "negative" , "description" : "Direct competitor underperforming in AI infrastructure segment, may face margin pressure" , "relationship" : "Direct Competitor" } , { "entity_tag" : "cls_nyse" , "earnings_id" : "96325f3e-b899-432d-89b7-ef0aa86bb0e4" , "rating" : "neutral" , "description" : "Competitor may benefit from similar AI infrastructure trends but faces margin competition" , "relationship" : "Direct Competitor" } ] , "peer_comparison_sector_context" : [ "EMS industry benefiting from AI infrastructure buildout and cloud computing growth" , "Competitive landscape favors companies with strong AI/cloud capabilities" , "Supply chain resilience becoming key differentiator in EMS sector" ] , "analyst_and_street_reaction" : { "base_case" : "Strong AI demand continues with gradual margin expansion and steady growth" , "bear_case" : "AI demand slowdown or supply chain issues could pressure growth and margins" , "bull_case" : "Accelerating AI adoption drives further growth and margin expansion beyond guidance" } , "risk_assessment_update" : { "assessments" : [ "AI infrastructure demand remains robust" , "US manufacturing investment provides competitive advantage" , "Operational efficiency gains sustainable" ] , "upcoming_catalysts" : "Q1 2026 guidance, AI infrastructure contract wins, manufacturing capacity expansion" } , "citations" : [ { "title" : "Jabil Q4 2025 Earnings Call Transcript" , "url" : "https://example.com/jabil-q4-transcript" } , { "title" : "AI Infrastructure Manufacturing Report" , "url" : "https://example.com/ai-infrastructure-manufacturing" } ] , "documents" : [ { "id" : "jabil-q4-10k" , "name" : "Jabil Q4 2025 10-K Filing" } , { "id" : "jabil-ai-strategy" , "name" : "AI Infrastructure Strategy Presentation" } ] }` Show more
