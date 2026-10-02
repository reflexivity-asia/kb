# Reflexivity Knowledge Base

**Languages:** **English** · [日本語](../ja/README.md) · [한국어](../ko/README.md) · [简体中文](../zh-cn/README.md) · [繁體中文（台灣）](../zh-tw/README.md) · [繁體中文（香港）](../zh-hk/README.md)

The knowledge base is intentionally broad. You do not need to read every page before using it. Choose the route that fits what you need.

## 1. Ask with AI

You can connect the GitHub repositories to an AI assistant and ask questions directly against the available documentation.

- **GitHub Copilot** — Open [reflexivity-kb/docs](https://github.com/reflexivity-kb/docs) on GitHub and ask Copilot Chat about the current repository. [GitHub instructions](https://docs.github.com/en/copilot/how-tos/copilot-on-github/chat-with-copilot/get-started-with-chat)
- **ChatGPT** — In ChatGPT, open **Settings → Plugins**, connect GitHub, and authorize the repositories you want ChatGPT to read. [OpenAI instructions](https://help.openai.com/en/articles/11145903-connecting-github-to-chatgpt)
- **Claude** — In a chat choose **+ → Add from GitHub**, or add GitHub to Project knowledge, then select the files or folders you want Claude to use. [Claude instructions](https://support.claude.com/en/articles/10167454-use-the-github-integration)

For public documentation, add **reflexivity-kb/docs**. If you have approved access to [Reflexivity Client Resources](https://github.com/reflexivity-kb/client-resources), you can add that repository as well.

Your question is **not limited to the six languages in which the KB is published**. Ask in any language supported by your AI assistant. The source material itself is currently published in English, Japanese, Korean, Simplified Chinese, Traditional Chinese (Taiwan), and Traditional Chinese (Hong Kong).

For source-sensitive questions, ask the assistant to cite the exact pages it used. A useful starting instruction is:

> Use `reflexivity-kb/docs` and, if available to me, `reflexivity-kb/client-resources` as the source of truth. Answer from the most relevant Reflexivity documentation and include direct links to the pages you used. If the answer is not in the repositories, say so rather than guessing.

### Questions you can try

The following examples were checked against material that currently exists in the repositories.

**Public Knowledge Base**

1. “Show me the equity-related Reflexivity use cases and give me direct links.”
2. “What fixed-income use cases are available? Link each example.”
3. “Show me the use cases for a long-only asset manager, grouped by research type.”
4. “Which QUICK-provided use cases cover NVIDIA, Micron, AI, semiconductors, or data centers?”
5. “What Scenario Insight use cases are available? Give me links to the underlying pages.”

**Client Resources — approved access required**

6. “What is Reflexivity AI Connections / MCP, and what can it research?”
7. “What are the seven Reflexivity MCP tools and what does each one do?”
8. “How do I connect Reflexivity to ChatGPT?”
9. “How do I connect Reflexivity to Claude or GitHub Copilot?”
10. “Does the Reflexivity MCP connection provide live quotes or historical price series? What separate market-close price API is documented?”

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
