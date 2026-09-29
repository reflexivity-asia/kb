<!--
id: RX-PRODUCT-1088
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6aac3c9f407571e9758289ca
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: ai-connections-1/application-guides/claude
-->

# Claude

## Connect with Claude

Claude web and desktop use a remote custom connector. You need a full Reflexivity user account.

---

## Add the connector

For an individual account, open **Customize → Connectors → + → Add custom connector**. Use this server URL:

`https://api.reflexivity.com/external-research-mcp/mcp`

For a managed Team or Enterprise account, an Owner first adds it through **Organization settings → Connectors → Add → Custom → Web**.

---

## Connect your account

In **Customize → Connectors**, select the connector and choose **Connect**. Complete Reflexivity sign-in, then enable the connector in your conversation.

See [Claude's connector instructions](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp) for current account availability and settings. For the terminal plugin, use [Claude Code](../claude-code/README.md).

---

## Check the connection

Enable Reflexivity in your conversation and ask:

“Use Reflexivity to list my available watchlists and baskets. If the tools are unavailable, tell me that the connection check could not be completed.”

Confirm that a Reflexivity tool returns a result. An empty list can be valid; an authentication error or failed call is not a successful check.

---

## If the connection is invalidated

Open the connector settings and reconnect Reflexivity. During testing, refreshing the tool list in Manage connectors triggered a new sign-in and restored access. After reconnecting, repeat the connection check.

Connection invalidation was reported in Claude Code after signing out of the Claude app. If you use both, check the connection in each affected application. See [Troubleshooting](../../help/troubleshooting/README.md) if the problem continues.

---

[← Documentation](../../../README.md)
