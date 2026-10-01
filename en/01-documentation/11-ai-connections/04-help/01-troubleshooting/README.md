<!--
id: RX-PRODUCT-1100
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6aa95a33407571e97561742b
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: ai-connections-1/help/troubleshooting
-->

# Troubleshooting

Start with the checks for your application below. After reconnecting, verify that an actual Reflexivity tool call succeeds. An answer from general knowledge or web research does not confirm that Reflexivity is connected.

---

## Check your application

### Claude web and desktop

Open Claude’s connector settings and select Reflexivity. Check whether the connector needs you to connect or sign in again.

Complete any sign-in prompt, return to Claude, and enable Reflexivity in the conversation. If available, refresh the connector’s tool list.

Then ask:

“Use Reflexivity to list my watchlists only. If the connection is unavailable, report the connection error instead of answering from general knowledge.”

A successful tool response confirms that the call worked. An empty list can be valid.

### Claude Code in a terminal

Run `/mcp` and select `reflexivity-research`. Check whether the server is available and authenticated.

If authentication is required, choose Authenticate and complete the browser flow. Return to Claude Code and check `/mcp` again.

If the plugin’s tools are missing, run `/reload-plugins` and start a new session.

Run `/reflexivity:doctor` to inspect the plugin, server connection, sign-in, and account access. After resolving the reported issue, run `/reflexivity:setup` to check the connection again.

Being signed in to Claude or Reflexivity in a browser does not by itself confirm that this MCP connection is authenticated.

### Cursor

Open Settings → Tools & MCP and locate the Reflexivity connection. For the plugin installation, its server name is `reflexivity-research`.

Check that the connection is enabled. Select Login if authentication is required, complete browser sign-in, and return to Cursor.

For a plugin installation, ask:

“Use Reflexivity’s doctor workflow to check my connection.”

For a direct MCP connection without the plugin, check the server’s status and available tools in Cursor, then request a Reflexivity tool call. The plugin’s doctor workflow is not automatically included with a direct connection.

### Codex

Confirm that the Reflexivity plugin is installed and enabled, then start a new task or session.

Ask:

“Use Reflexivity’s doctor workflow to check my connection.”

Follow the sign-in instructions reported by the application, then repeat the setup check. The diagnostic should distinguish missing tools, failed authentication, and missing research access.

### ChatGPT

First identify whether you are using a workspace-provided plugin or a direct developer-mode connection.

Check that Reflexivity is available to your account and selected for the conversation. For a developer-mode connection, review the app’s tool settings and refresh the tools if necessary.

Complete any authentication prompt, start a new conversation, and request a Reflexivity tool call.

If developer mode is disabled, follow the guidance in the [ChatGPT guide](../../02-application-guides/03-chatgpt/README.md).

### Gemini

For Gemini web, check that your Google Account meets the custom app requirements and that Reflexivity is enabled in Connected Apps. In your conversation, type `@` and select the connected app.

For Gemini CLI, run `/mcp list` to check the connection. If authentication is required, run `/mcp auth reflexivity-research` and complete sign-in with your Reflexivity account.

For full setup instructions, see the [Gemini application guide](../../02-application-guides/06-gemini/README.md).

---

## Reflexivity is missing

For a plugin installation, confirm that Reflexivity is installed and enabled.

In a managed organization, your administrator may need to make the plugin or connection available first. In Cursor, confirm that you are using the team where the Reflexivity repository was registered.

For a direct connection, check the server URL and connection settings in your application guide.

Avoid adding another copy of the connection while troubleshooting an existing installation.

---

## Browser sign-in succeeded, but the application is not connected

Your browser session and your AI application’s connection can have different authentication states. A browser success message does not confirm that the application finished connecting.

Return to the application, inspect the Reflexivity connection, and complete the checks for your application above.

Confirm that tools are available and that a tool call succeeds.

---

## A working connection stopped

Use the steps for your application above to reconnect, then repeat a connection check.

If access returns but drops again shortly afterward, record the time of the last successful call and the next failure. Send those details, the exact error, and your application version to [support@reflexivity.com](mailto:support@reflexivity.com).

Repeated reconnection may restore access temporarily, but it does not resolve the underlying cause. Avoid repeatedly reinstalling the plugin or creating duplicate connections.

---

## Sign-in fails or keeps repeating

Complete the sign-in flow in your browser, then return to the application and inspect its connection status.

If the application continues to request sign-in, record the exact error and installation method. Contact support instead of repeatedly adding new connections.

---

## Signed in but access is denied

Check which Reflexivity account you used and whether it has research MCP access.

Installing the plugin or receiving it from your administrator does not by itself grant access to Reflexivity research.

---

## The connection cannot be reached

The application needs to reach `api.reflexivity.com` and `identity.reflexivity.com`.

Check the connection URL and your network. If your organization restricts external connections, ask its administrator to check access to those hosts.

A timeout alone does not establish whether the cause is network connectivity, authentication, or an unavailable research source. Include the exact error when requesting help.

---

## No research was found

Searches cover the last 30 days unless you ask for a different period. Try a longer period, add the company’s exchange, or choose another research type.

An empty result is different from a source being unavailable. The answer should identify which happened.

See [Coverage and sources](../../03-research/01-coverage-and-sources/README.md).

---

## The answer uses the wrong company, theme, or quarter

For a company, provide its full name, ticker, and exchange.

For a theme, check the Reflexivity theme matched to your question and ask again using that name.

For a quarter, ask for the reporting period and publication date separately. A recent update can belong to an older quarter.

---

## A requested filter or field is unavailable

The documented research MCP interface does not expose a star-rating filter or a returned star-rating field. Requests such as “show 7+ star insights” cannot be reliably applied through this interface.

A dedicated bullish/bearish direction field is also not defined in the current documented scenario detail. Missing direction should be reported as unavailable rather than inferred from the title.

See the [MCP tool reference](../../05-reference/01-mcp-tool-reference/README.md) for supported inputs and response fields.

---

## The answer is too brief or has no visual

Ask for the output you need: a comparison table, a fuller explanation, supporting evidence, or relevant dates.

Applications may present the returned information differently. Charts and other visualizations depend on the application and available data.

For example:

“Expand the answer using Reflexivity’s available evidence. Explain the top relationship, include relevant dates, and identify any missing support.”

---

## Only part of the answer is available

Ask which companies or research items are missing and why. Retry unavailable sources later.

Missing data should not be treated as zero, no exposure, or evidence that nothing happened.

---

## Get help

Email [support@reflexivity.com](mailto:support@reflexivity.com) with your application and version, operating system, and whether you used web or desktop.

Include the installation method: workspace plugin, team marketplace, local plugin, imported plugin, or direct MCP connection.

Provide the time and time zone, exact error, and the question or step that failed. If the connection stopped working, include the last successful call and whether reauthentication restored access.

Leave out passwords, access tokens, sign-in codes, and private research or watchlist details.

---

[← Documentation](../../../README.md)
