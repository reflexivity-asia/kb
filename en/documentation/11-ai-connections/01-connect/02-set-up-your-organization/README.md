<!--
id: RX-PRODUCT-1086
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6aac2306407571e9758172a7
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: ai-connections-1/connect/set-up-your-organization
-->

# Set up your organization

**Draft:** This setup path still needs connection testing.

Make Reflexivity available in the applications your team uses, then direct users to [connect their accounts](../01-connect-your-account/README.md).

---

## Choose the deployment route

| Application | Administrator's task |
| --- | --- |
| Claude | An Owner adds the custom connector; members then connect their accounts. |
| ChatGPT | Make the workspace plugin available or permit a direct MCP connection, as the chosen route requires. |
| Claude Code or Codex | Review the Reflexivity plugin and make its marketplace available under your organization's application policies. |
| Cursor | Register the Reflexivity repository in your team marketplace so users can install it. |
| GitHub Copilot | Allow the Reflexivity MCP server under the relevant organization or enterprise policies. |
| Microsoft 365 Copilot | Configure and deploy a connector to selected users or groups. |

The [application guides](../../02-application-guides/README.md) describe each route. The plugin repository is [toggleglobal/reflexivity-ai-plugins](https://github.com/toggleglobal/reflexivity-ai-plugins).

---

## Pilot before rollout

Start with a small group using ordinary user accounts. Confirm that users can find and install the integration using the documented route, sign in with their own Reflexivity account, and successfully call the Reflexivity tools.

Also check that research works in a new conversation and that users can reconnect if sign-in expires or a connection is invalidated.

For Cursor, record whether the plugin came from the team marketplace, a local installation, or another application’s plugin directory. A successful test through one route does not validate the others.

### Give each user a clear next step

Share the relevant application guide and [Connect your account](../01-connect-your-account/README.md).

Application approval makes the integration available. It does not create Reflexivity accounts or sign users in. Each person needs their own full Reflexivity user account.

For failed setup or reconnection, see [Troubleshooting](../../04-help/01-troubleshooting/README.md).

---

[← Documentation](../../../README.md)
