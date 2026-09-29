<!--
id: RX-PRODUCT-1089
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6aac3ca5eaa6027014247675
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: ai-connections-1/application-guides/claude-code
-->

# Claude Code

## Connect with Claude Code

These instructions use Claude Code in a terminal. You need a full Reflexivity user account.

---

## Install the plugin

```bash
claude plugin marketplace add toggleglobal/reflexivity-ai-plugins
claude plugin install reflexivity@reflexivity
```

Start a new session and enter:

```text
/reflexivity:setup
```

The plugin supplies the connection settings. If prompted to authenticate, open `/mcp`, select `reflexivity-research`, and choose **Authenticate**. Sign in to Reflexivity in your browser, then return to Claude Code.

---

## Check the connection

The setup workflow checks that the research tools are available and that your account has access. It may return no saved watchlists or baskets; that is a valid result.

If tools are missing, run `/reload-plugins` and check `/mcp` again. For other problems, see [Troubleshooting](../../help/troubleshooting/README.md).

See [example questions](../../research/README.md).

---

## If a previously working connection stops

Open `/mcp` and inspect `reflexivity-research`. Authenticate again if prompted, then repeat `/reflexivity:setup` in a new session.

During testing, a user reported an invalidated connection in Claude Code after signing out of the Claude app. Refreshing the affected connector’s tool list triggered reauthentication and restored access. If you use more than one Claude application, check the connection in each affected application.

For diagnostics, run `/reflexivity:doctor`. If the issue persists, follow [Troubleshooting](../../help/troubleshooting/README.md).

---

[← Documentation](../../../README.md)
