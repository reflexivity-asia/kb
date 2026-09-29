<!--
id: RX-PRODUCT-1004
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f233534
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: alfred/ask-question
-->
# Ask question

Returns streamed event response from the assistants.

#### Body Parameters Expand all

question string Required The question to ask Alfred.

ancillary object Additional information to help Alfred answer the question.

Show child attributes

session_id string Required The session id.

target string Specifies target assistant.

### Response Expand all

200 Object Alfred API status.

#### Response Attributes

source string The source of the streamed event. It specifies the assistant that generated the event.

event string The event type.

data object The data received from the assistant.

Show child attributes

request_id string The request id.

400 Object Bad request.

500 Object Internal error.

---

[← Documentation](../../README.md)
