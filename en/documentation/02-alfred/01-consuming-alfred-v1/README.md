<!--
id: RX-PRODUCT-1003
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f233530
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: alfred/consuming-alfred
-->
# 🧠 Consuming Alfred v1

This guide helps you integrate [Alfred](../README.md), our autonomous financial analyst, into your systems. The Alfred v1 API provides a streaming interface to interact with Reflexivity assistants, each with distinct capabilities for financial analysis workflows.

## 🔐 Authentication

To start using the [Alfred API](../README.md), obtain an authentication token from the [Overview authentication section](../../README.md) and include it in the Authorization header for all requests:

HTTP `Authorization: Bearer `
## 📡 Request

### HTTP Method

`POST`

### Headers

Title Description Title Description Header

Type

Required

Description

`Authorization`

`string`

Yes

Bearer token authentication

`Content-Type`

`string`

Yes

Must be `application/json`

### Request Body

TypeScript `{
question: string; // The user's query
session_id: string; // Unique session identifier (uuid format)
target?: string; // Optional: specific assistant to target
ancillary?: { // Optional: additional context
documents?: string[]; // Document IDs for context
};
}`
#### Target Reflexivity Assistant Options

- `"all"` (default): routes to all assistants

- `"document-assistant"`: document analysis

- `"scenario-assistant"`: scenario analysis

- `"chart-assistant"`: chart generation

- `"fallback-assistant"`: general responses

---

## 📊 Response Stream

### Stream Format

The response is streamed as a series of JSON objects, each representing a response from a specific service.

TypeScript `{
source: string; // Source of the response
data: { // Response data with confidence scoring
confidence: number; // Confidence score (0-1)
scores: Record ; // Detailed scoring breakdown
[key: string]: any; // Additional service-specific data
};
request_id: string; // Mirrors the request session_id
}`
### Response Types

#### 1. 📑 Document Assistant

The [Document Assistant](https://support.reflexivity.com/hc/en-us/articles/27023208583444-What-is-Document-Search-and-how-does-it-work) can answer user questions using content from any financial or economic document that is indexed in Reflexivity. The assistant can read basic text and collect data from tables and charts.

Response:

JSON `{
source: "document-assistant";
data: {
message: string;
citationsResult: {
citations: Record | null;
};
citation_group_id: string;
overview: {
documents: number;
companies: number;
document_types: Record ;
industries: Record ;
};
};
}`

Document Message

Document View

#### 2. 🔮 Scenario Assistant

The [Scenario Analysis Assistant](https://support.reflexivity.com/hc/en-us/articles/27023105377556-What-is-Scenario-Analysis-and-how-does-it-work) runs historical scenario analysis.

Response:

TypeScript `{
source: "scenario-assistant";
data: {
conditions: Array ;
entities: Array ;
actions?: Array ;
}>;
};
}`

#### 3. 📈 Chart Assistant

The [Chart Assistant](https://support.reflexivity.com/hc/en-us/articles/27023168045716-What-is-Chart-and-how-does-it-work) is used for plotting fundamental, technical, or economic data series that Reflexivity holds within [Calculator service](../../03-calculator/README.md).

TypeScript `{
source: "chart-assistant";
data: {
assets: Array ;
start?: string;
end?: string;
horizon?: "OneDay" | "OneWeek" | "TwoWeeks" | "OneMonth" | "TwoMonths" | "ThreeMonths" | "SixMonths" | "OneYear" | "ThreeYears" | "FiveYears" | "TenYears" | "Max";
resample?: "1D" | "1W" | "1M" | "1h" | "30m" | "15m" | "5m" | "1m";
series_type?: "line" | "candlestick" | "bars";
y_axis_type?: "split" | "merged";
};
}`

Example response from Alfred:

JSON `{
"source": "chart-assistant",
"data": {
"assets": [
{
"is_default": false,
"snake": "aapl_nasd.pe_ibes_trailing_12m",
"tag": "aapl_nasd"
},
{
"is_default": false,
"snake": "googl_nasd.pe_ibes_trailing_12m",
"tag": "googl_nasd"
}
],
"confidence": 0.9998950958251953,
"horizon": "ThreeMonths",
"price_display": "price",
"resample": "1D",
"series_type": "line",
"y_axis_type": "split"
},
"request_id": "7adbdd1c-d786-4c43-971f-56ced7db6df4"
}`

#### 4. 📰 Fallback Assistant

The [Fallback Assistant](https://support.reflexivity.com/hc/en-us/articles/27677451697172-What-is-the-General-Knowledge-Base) pulls from a general repository of financial sources like news and other web sources. After your question is sent to the assistant, the answer string is returned in markdown format, which may contain special links as below.

Markdown `- [Investopedia](https://www.investopedia.com/dow-jones-today-04022025-11707447 \"article\")
- [MT Newswires](149530a5-7619-4812-8983-9f63f86b0c93 \"internal_news\")`

#### Response Schema

TypeScript `{
source: "fallback-assistant";
data: {
answer: string;
};
}` Title Description
### ⚠️ Error Responses

#### Authentication Error

JSON `{
status: 401;
message: "Unauthorized";
}`
#### Invalid Request

JSON `{
status: 400;
message: "Invalid request parameters";
}`
## 🧪 Example Usage

### Curl Request

Bash `curl -X POST 'https://api.example.com/alfred/v1' \
-H 'Authorization: Bearer ' \
-H 'Content-Type: application/json' \
-d '{
"question": "What are Tesla'\''s latest financial results?",
"session_id": "123e4567-e89b-12d3-a456-426614174000",
"target": "document-assistant"
}'`
## 📝 Notes

- The API streams responses.

- Responses are chunked and each chunk is a complete JSON object.

- The stream ends with a completion signal or error.

- Rate limiting applies based on the user’s subscription tier.

- All timestamps are in ISO 8601 format.

## 🤝 Need Help?

- Help center: [Getting started with Reflexivity](https://support.reflexivity.com/hc/en-us/articles/26906922816404-What-is-Reflexivity)

- Contact: [support@reflexivity.com](mailto:support@reflexivity.com)

---

[← Documentation](../../README.md)
