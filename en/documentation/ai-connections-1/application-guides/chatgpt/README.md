<!--
id: RX-PRODUCT-1090
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6aac3cac50675fa0b9e8c278
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: ai-connections-1/application-guides/chatgpt
-->

# ChatGPT

## Connect with ChatGPT

---

## Current status

Reflexivity’s ChatGPT connection is still being validated. Successful research queries have been reported, but some sessions have no callable Reflexivity tools even after authentication. Verify tool access in the conversation before relying on the connection.

---

## Choose your setup route

### Workspace plugin

If your administrator has made the Reflexivity plugin available, use the installation route supplied by your workspace. The Reflexivity repository is [toggleglobal/reflexivity-ai-plugins](https://github.com/toggleglobal/reflexivity-ai-plugins).

The workspace-plugin route needs its own installation, authentication, and tool-access validation. A successful direct web connection does not validate a workspace-plugin installation.

If Reflexivity is not available in your workspace, ask your administrator or contact [support@reflexivity.com](mailto:support@reflexivity.com) before attempting an alternative installation.

### Direct connection on the web

Where your account and workspace permit developer-mode apps, use ChatGPT’s remote MCP connection flow with the [Reflexivity MCP endpoint](https://api.reflexivity.com/external-research-mcp/mcp).

OpenAI documents developer mode under Settings → Security and login and app creation through ChatGPT Plugins. Follow the [current developer-mode instructions](https://developers.openai.com/api/docs/guides/developer-mode) for eligibility, connection controls, and authentication options.

Complete the Reflexivity sign-in flow. The Reflexivity-specific authentication configuration for this route is still being validated; contact support if app creation or sign-in cannot be completed.

---

## Developer mode is disabled

Developer mode applies to the direct custom-MCP connection route described here.

If your workspace already provides Reflexivity, start with that workspace’s installation instructions rather than creating another connection.

For a direct connection on the web, check that your account and workspace allow developer-mode apps. If the control is unavailable or disabled, ask your workspace administrator to confirm the permitted setup route.

Workspace availability, successful sign-in, and tool access are separate checks. After installation, confirm that Reflexivity is selected for the conversation and that an actual tool call succeeds.

OpenAI currently marks imported plugins that declare MCP servers as desktop-only, including plugins that connect to a remote HTTPS server. Confirm that you are using the application supported by your workspace’s installation route. See [OpenAI’s workspace plugin documentation](https://learn.chatgpt.com/docs/enterprise/plugin-management).

---

## Verify tool access in your conversation

Start a new conversation and select the Reflexivity app. For a developer-mode app, select it through the composer’s Developer mode tools.

Ask:

“Use Reflexivity to list my available watchlists and baskets. If you cannot call Reflexivity’s tools, say that the connection check could not be completed. Do not substitute web research for this check.”

Confirm that ChatGPT calls a Reflexivity tool and receives a result. A successful empty list can be valid. An authentication error, unavailable tool, or timeout means the check did not succeed.

---

## Signed in, but no tools are available

Check that Reflexivity is selected for the conversation. For a developer-mode app, review its tool settings and refresh the app to retrieve the current tools. Reauthenticate if prompted, then repeat the check in a new conversation.

If the problem continues, send [support@reflexivity.com](mailto:support@reflexivity.com) your setup route, whether you used web or desktop, application version where available, the time and time zone, and the exact error. Do not include credentials or tokens.

---

## Ask for the level of detail you need

“Use Reflexivity to list NVIDIA’s ten strongest industry themes. Explain the evidence behind the top theme in three paragraphs, include relevant dates and reporting periods where available, and distinguish retrieved evidence from interpretation. Identify any missing evidence.”

Answer length and presentation can vary between applications and conversations. See [Research examples](../../research/README.md) and [Troubleshooting](../../help/troubleshooting/README.md).

Using Codex? Follow the [Codex guide](../codex/README.md).

---

[← Documentation](../../../README.md)
