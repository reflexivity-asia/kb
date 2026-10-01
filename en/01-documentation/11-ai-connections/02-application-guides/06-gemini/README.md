<!--
id: RX-PRODUCT-1093
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6ab2c9c1ad267bc33e1d530e
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: ai-connections-1/application-guides/gemini
-->

# Gemini

Connect Gemini to Reflexivity’s research MCP server to work with company relationships, industry themes, competitors, and research insights. You need a Reflexivity account with research MCP access.

This connection provides read-only research tools. It does not install the Reflexivity plugin or its setup and diagnostic commands.

---

## Connect through Gemini web

Google currently offers custom apps to users aged 18 or older in the United States, using a personal Google Account, English, and Keep Activity enabled. Work and school Google Accounts are not currently eligible.

Open Gemini in your browser.

Go to Settings, then Connected Apps. Depending on your interface, Connected Apps may appear under Personal Intelligence.

Under Custom apps, choose Add a custom app and enter this server address:

`https://api.reflexivity.com/external-research-mcp/mcp`

Click Next and follow the sign-in and authorization prompts using your Reflexivity account.

In a conversation, type `@` and select the connected app to direct your request to Reflexivity.

If Custom apps is missing, check your account eligibility and Keep Activity setting.

These steps follow [Google’s custom app connection guide](https://support.google.com/gemini/answer/17209137?co=GENIE.Platform%3DDesktop&hl=en).

---

## Connect through Gemini CLI

With Gemini CLI installed and working, run this command in your terminal:

```bash
gemini mcp add --transport http --scope user reflexivity-research https://api.reflexivity.com/external-research-mcp/mcp
```

This saves the connection in your user configuration so it is available across projects.

Start Gemini CLI by running:

```bash
gemini
```

Inside Gemini CLI, authenticate the connection:

```text
/mcp auth reflexivity-research
```

Complete the browser sign-in using your Reflexivity account, then return to the terminal.

Check the connection and available tools:

```text
/mcp list
```

If authentication expires, run `/mcp auth reflexivity-research` again.

These commands follow the [Gemini CLI MCP documentation](https://geminicli.com/docs/tools/mcp-server/).

---

## Check your connection

Ask Gemini:

“Use Reflexivity to list my watchlists only. If you cannot call its tools, tell me the connection check could not be completed.”

Confirm that Gemini calls a Reflexivity tool. An empty watchlist result can still indicate a successful connection. A response based only on general knowledge or web search does not verify access.

---

## Try your first research question

“Use Reflexivity to identify NVIDIA’s main industry themes and explain the evidence behind its strongest relationships.”

You can also ask:

“Use Reflexivity to find companies connected to the cybersecurity theme.”

“Use Reflexivity to find research insights about Microsoft and summarize the supporting evidence.”

---

## Troubleshooting

If sign-in succeeds but research tools remain unavailable, confirm that the Reflexivity account you used has research MCP access.

If Gemini answers without using Reflexivity, explicitly request Reflexivity in your prompt. In Gemini web, select the connected app using `@`.

In Gemini CLI, run `/mcp list` to inspect connection errors, then repeat authentication if required.

If the issue continues, share the error message and whether you are using Gemini web or Gemini CLI with Reflexivity support.

---

[← Documentation](../../../README.md)
