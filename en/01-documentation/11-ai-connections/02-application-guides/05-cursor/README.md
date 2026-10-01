<!--
id: RX-PRODUCT-1092
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6aac3cb1eaa60270142476d0
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: ai-connections-1/application-guides/cursor
-->

# Cursor

You need a Reflexivity account with research MCP access. The documented plugin route uses your Cursor team marketplace; other installation routes are described below.

## Current status

The team-marketplace setup route is still being validated. Users have reported difficulty finding the plugin and reconnecting after sign-in expires. Successful tests using a local installation or a Claude Code plugin discovered by Cursor do not establish that the team-marketplace route works for every account.

---

## Install and sign in

Step 1: Ask your team administrator to register [toggleglobal/reflexivity-ai-plugins](https://github.com/toggleglobal/reflexivity-ai-plugins) in the team marketplace.

Step 2: Confirm that you are signed in to the Cursor account and team where the repository was registered.

Step 3: Open Cursor Settings → Plugins and look for Reflexivity Research. Install it if available.

Step 4: Open Cursor Settings → Tools & MCP. Enable `reflexivity-research` if needed, then select Login.

Step 5: Complete Reflexivity sign-in in your browser, then return to Cursor.

---

## If the plugin does not appear

Ask your administrator to confirm that the repository was added to the marketplace for your team and is available to your account. Searching for Reflexivity alone does not establish that the team marketplace has been configured.

If the plugin is still missing, contact [support@reflexivity.com](mailto:support@reflexivity.com) with your Cursor version, operating system, and a screenshot of the Plugins view. Do not include passwords or tokens.

### Other installation routes

Successful tests have also been reported using a locally imported Reflexivity plugin and a direct connection to the Reflexivity MCP server.

These are different setup routes. A plugin installation includes Reflexivity’s setup, doctor, and research workflows. A direct MCP connection exposes the server’s tools but does not automatically install those workflows.

When requesting help, identify which route you used. If you already have a working connection, avoid adding another copy while troubleshooting.

The repository currently documents the team-marketplace route. Detailed local-import and direct-connection instructions should be validated for your Cursor version before being used for a team rollout.

Cursor can present research as text, tables, or visualizations, depending on the request and available data. Ask explicitly for the format you want.

A chart or canvas is not guaranteed for every query. Any visualization should use the returned data without inventing missing values.

---

## Check the connection

Start a new chat and ask:

“Set up Reflexivity Research for me.”

The setup workflow checks tool availability and account access. A successful response containing no saved watchlists or baskets can still be a valid result.

Then ask:

“Use Reflexivity to show Tesla’s main industry themes and explain the evidence behind its top theme.”

Confirm that Cursor actually calls a Reflexivity tool. An answer produced from general knowledge or web research does not verify this connection.

---

## If a working connection stops

Expired sign-in has been reported alongside tool calls that appeared to time out. A timeout alone does not establish the cause.

Open Cursor Settings → Tools & MCP, check `reflexivity-research`, and sign in again if prompted. After completing sign-in, start a new chat and repeat the connection check.

You can also ask:

“Use Reflexivity’s doctor workflow to check my connection.”

If calls still fail, record the exact error and follow [Troubleshooting](../../04-help/01-troubleshooting/README.md).

---

## Try a research question

See [Research examples](../../03-research/README.md) for questions to try, and [Coverage and sources](../../03-research/01-coverage-and-sources/README.md) for limitations.

Output format can vary; a successful research query does not guarantee a chart or interactive visual.

---

[← Documentation](../../../README.md)
