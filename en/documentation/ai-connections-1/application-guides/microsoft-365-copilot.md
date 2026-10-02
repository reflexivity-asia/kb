<!--
id: RX-PRODUCT-1096
type: product
language: en
locale: en
author: Reflexivity GTM Team
resource: Reflexivity Documentation
status: published
translation_status: canonical
-->

# Microsoft 365 Copilot

[← Documentation](../../README.md)

# Connect with Microsoft 365 Copilot
Draft: This setup path still needs connection testing.

Microsoft 365 Copilot supports custom federated connectors that read from an MCP server. An administrator configures the connector and makes it available to selected users or groups.

## Administrator setup
The configured production target is:

https://api.reflexivity.com/external-research-mcp/mcp

Microsoft's OAuth route requires a registered client, authentication settings and a Teams Developer Portal registration. Reflexivity must confirm those settings before this becomes a setup guide. See [Microsoft's connector instructions](https://learn.microsoft.com/en-us/microsoft-365/copilot/connectors/set-up-custom-federated-connectors).

## User setup
Once the connector is available, users authenticate to the external service. The exact Reflexivity sign-in steps will follow validation.

This guide concerns Microsoft 365 Copilot for work. Copilot Studio agents use a separate setup route
