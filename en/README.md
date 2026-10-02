# Reflexivity Knowledge Base

**Languages:** **English** · [日本語](../ja/README.md) · [한국어](../ko/README.md) · [简体中文](../zh-cn/README.md) · [繁體中文（台灣）](../zh-tw/README.md) · [繁體中文（香港）](../zh-hk/README.md)

The Knowledge Base contains a large amount of material, so you do not need to read it from beginning to end. There are three ways to use **this documentation**:

1. ask an AI assistant about the documentation,
2. browse the pages directly,
3. ask support when something is missing.

> **Important:** Asking an AI about this Knowledge Base and connecting the **Reflexivity service itself** to an AI application via MCP are two different things. The MCP connection is explained separately below.

## 1. Ask an AI about this Knowledge Base

You can let an AI assistant read the GitHub documentation and ask it to find, summarize, compare, or link the relevant pages.

- **GitHub Copilot** — Open [reflexivity-kb/docs](https://github.com/reflexivity-kb/docs) and ask Copilot about the repository, or add the repository as Copilot context. [GitHub instructions](https://docs.github.com/en/copilot/tutorials/explore-a-codebase)
- **ChatGPT** — Connect GitHub in ChatGPT, authorize **reflexivity-kb/docs** and, if you have access, **reflexivity-kb/client-resources**, then ask questions about those repositories. [OpenAI instructions](https://help.openai.com/en/articles/11145903-connecting-github-to-chatgpt)
- **Claude** — Use **Add from GitHub** in a chat or add GitHub to Project knowledge, then select the relevant files or folders. [Claude instructions](https://support.claude.com/en/articles/10167454-use-the-github-integration)

You can ask in any language supported by your AI assistant. The documentation itself is currently published in six locales.

A useful instruction is:

> Use the Reflexivity GitHub documentation as the source of truth. Answer from the most relevant pages, include direct links to the pages you used, and say clearly when the answer is not in the documentation.

### Questions you can try

These are documentation questions that can be answered from material currently in the repositories.

1. “Show me the equity-related Reflexivity use cases and give me direct links.”
2. “What fixed-income use cases are available? Link each example.”
3. “Show me the use cases for a long-only asset manager, grouped by research type.”
4. “Which QUICK-provided use cases cover NVIDIA, Micron, AI, semiconductors, or data centers?”
5. “What Scenario Insight use cases are available? Give me links to the underlying pages.”
6. “What is Reflexivity AI Connections / MCP, and what can it research?”
7. “Which AI applications have Reflexivity connection guides?”
8. “What are the seven documented Reflexivity MCP tools and what does each one do?”
9. “What does the ChatGPT setup guide say I should verify after connecting?”
10. “Does the Reflexivity AI connection provide live quotes or historical price series? What separate Price History documentation is available?”

### Separate: use the Reflexivity service itself from an AI application

If you want ChatGPT, Claude, or another supported AI application to **call Reflexivity directly**, that is a separate product integration using **Reflexivity MCP**. It is not the same as giving the AI access to these GitHub manuals.

Approved users can follow the application-specific setup guides in [Client Resources](https://github.com/reflexivity-kb/client-resources):

- [ChatGPT](https://github.com/reflexivity-kb/client-resources/blob/main/en/01-technical-reference/11-ai-connections/02-application-guides/03-chatgpt/README.md)
- [Claude](https://github.com/reflexivity-kb/client-resources/blob/main/en/01-technical-reference/11-ai-connections/02-application-guides/01-claude/README.md)
- [GitHub Copilot in VS Code](https://github.com/reflexivity-kb/client-resources/blob/main/en/01-technical-reference/11-ai-connections/02-application-guides/07-github-copilot-in-vs-code/README.md)

The MCP connection gives the AI application access to documented Reflexivity Insights and Knowledge Graph capabilities. It is not a general-purpose live-quote or historical-price-series connection.

## 2. Browse the pages

If you prefer to explore manually, the public KB is organized into five collections:

- **Use Cases** — [research workflows and examples](01-use-cases/README.md)
- **Guides** — [usage and onboarding guides](02-guides/README.md)
- **Product** — [product materials](03-product/README.md)
- **Articles** — [articles and historical public materials](04-articles/README.md)
- **Releases** — [release notes](05-releases/README.md)

Use Cases can be browsed by **persona**, **insight type**, or **asset class**. For example, you can go directly to [Equities Use Cases](01-use-cases/03-asset-class/04-equities/README.md) or [Fixed Income Use Cases](01-use-cases/03-asset-class/02-fixed-income/README.md).

Approved users also have access to [Client Resources](https://github.com/reflexivity-kb/client-resources), which includes the access-controlled **Technical Reference** for REST APIs and AI/MCP connections.

## 3. Ask support when something is missing

If you cannot find the material you need, contact **jim@reflexivity.com**.

Approved Client Resources users can also use [GitHub Discussions](https://github.com/reflexivity-kb/client-resources/discussions) for documentation questions, clarification, feedback, or requests for missing material.

When asking, please include the **hard link or page title** when possible, plus a short note describing what you expected to find. This makes it much easier to identify the exact gap.

Do not post credentials, tokens, customer-confidential information, or customer-specific commercial material in Discussions.

### Keep GitHub notifications quiet

You do not need to watch every repository update. On the repository page, open **Watch** and choose **Participating and @mentions** for the lowest-noise recommended setting. Choose **Ignore** if you do not want repository notifications. Use **Custom** only if you specifically want selected event types such as Discussions.

GitHub notification help: [Configuring notifications](https://docs.github.com/en/subscriptions-and-notifications/get-started/configuring-notifications).
