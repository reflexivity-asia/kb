<!--
id: RX-PRODUCT-1073
type: product
language: en
locale: en
author: Reflexivity GTM Team
kb_imported: 2026-09-29
status: published
translation_status: canonical
resource: Reflexivity Documentation
-->
# 🧲 Company → Company (Proximity)

[Legacy](../README.md) · [Documentation](../../../README.md)

**Method:** `POST`

#### Body Parameters

`entity` — `string`

the entity tag

### Response

**200** — Object: Successful request

#### Response Attributes

`googl_nasd` — `string`

`snap_nyse` — `string`

**400** — Object: Bad request

**500** — Object: Something went wrong!

**Endpoint:** `POST /kg/v1/connected-entities/proximity`

## Request example

```bash
curl --location 'https://api.reflexivity.com/kg/v1/connected-entities/proximity' \
--data '{
  "entity": "amzn_nasd"
}'
```

## Response example

```json
[
  "googl_nasd",
  "snap_nyse"
]
```

---

← [Legacy](../README.md) · [Scenario Insights](../../../scenario-insights/README.md) →
