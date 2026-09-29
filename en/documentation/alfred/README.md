<!--
id: RX-PRODUCT-1002
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f23352e
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: alfred
-->
# Alfred

Alfred allows applications to submit user questions to assistant services and receive generated responses with related metadata. Use Alfred for chat-style workflows where a user question, session context, and optional routing information need to be sent to backend assistant services.

Alfred supports both general knowledge requests and targeted assistant requests.

## Base Path

/alfred/v1

## Start Here

[Consuming Alfred](consuming-alfred/README.md)

- Use this guide to understand the Alfred request flow, session behavior, target routing, and streamed metadata behavior before calling the endpoint pages.

## Endpoints

[Ask Question](ask-question/README.md) : ​ POST /alfred/v1

- Use this endpoint to submit a user question with session context. The request can include routing information when the question should be handled by a specific assistant.
[Ask general knowledge](../README.md) : ​ POST /alfred/v1/general-knowledge

- Use this endpoint to submit a general knowledge question that does not need to be routed to a specialized assistant.

## Notes

Requests may include session context so conversations can be associated with a specific user interaction.

Requests may include a target field when the question should be routed to a specific assistant.

Responses may include metadata events that can be processed and displayed by the client application.

---

[← Documentation](../README.md)
