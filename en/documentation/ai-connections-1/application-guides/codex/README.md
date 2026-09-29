<!--
id: RX-PRODUCT-1091
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6aac3d4d50675fa0b9e8d365
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: ai-connections-1/application-guides/codex
-->

# Codex

## Connect with Codex

Reflexivity Research works in Codex CLI and the desktop app. You need a full Reflexivity user account.

---

## Install the plugin

In Terminal, add the Reflexivity marketplace:

```bash
codex plugin marketplace add toggleglobal/reflexivity-ai-plugins
```

Then open Codex:

```bash
codex
```

Open `/plugins` and install Reflexivity. Start a new task or session and ask:

“Set up Reflexivity for me.”

The plugin supplies the connection settings. Complete any sign-in prompt, then follow the connection checks below.

---

## Sign in

If sign-in is required, run in Terminal:

```bash
codex mcp login reflexivity-research
```

Open the sign-in link shown in Terminal and complete Reflexivity sign-in in your browser. Return to Terminal and wait for confirmation.

---

## Check the connection

In the desktop app, start a new task with the Reflexivity Research plugin enabled. For the CLI, start a new session:

```bash
codex
```

Then ask:

“Set up Reflexivity Research for me.”

The setup workflow checks tool availability and account access. A successful result with no saved watchlists is valid. If tools are missing, confirm that the plugin is enabled in `/plugins` and start a new session.

See [Troubleshooting](../../help/troubleshooting/README.md) for connection problems, or see [example questions](../../research/README.md).

---

[← Documentation](../../../README.md)
