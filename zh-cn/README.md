# Reflexivity 知识库

**语言：** [English](../en/README.md) · [日本語](../ja/README.md) · [한국어](../ko/README.md) · **简体中文** · [繁體中文（台灣）](../zh-tw/README.md) · [繁體中文（香港）](../zh-hk/README.md)

知识库内容很多，不需要从头逐页阅读。**使用这套 Knowledge Base 文档**主要有三种方式：

1. 让 AI 针对这些文档回答问题
2. 直接浏览页面
3. 找不到资料时联系支持

> **重要：** 让 AI 阅读这套 Knowledge Base 文档，与通过 MCP 把 **Reflexivity 服务本身**连接到 AI 应用，是两件不同的事。MCP 连接在下方单独说明。

## 1. 向 AI 询问这套 Knowledge Base

让 AI 读取 GitHub 文档后，可以直接查找相关页面、做摘要或比较，并返回所需链接。

- **GitHub Copilot** — 打开 [reflexivity-kb/docs](https://github.com/reflexivity-kb/docs)，针对当前仓库向 Copilot 提问，或把仓库加入 Copilot 上下文。[GitHub 说明](https://docs.github.com/en/copilot/tutorials/explore-a-codebase)
- **ChatGPT** — 在 ChatGPT 中连接 GitHub，授权 **reflexivity-kb/docs**，以及在你有权限时的 **reflexivity-kb/client-resources**，然后针对仓库里的文档提问。[OpenAI 说明](https://help.openai.com/en/articles/11145903-connecting-github-to-chatgpt)
- **Claude** — 在聊天中使用 **Add from GitHub**，或在 Project knowledge 中连接 GitHub，再选择所需文件或文件夹。[Claude 说明](https://support.claude.com/en/articles/10167454-use-the-github-integration)

提问语言不受六种文档语言限制，只要你使用的 AI 助手支持即可。文档原文目前提供六个 locale。

建议这样指示 AI：

> 请以 Reflexivity GitHub 文档为信息来源。根据最相关的页面回答，附上实际使用页面的直接链接；如果文档里没有答案，请明确说明，不要猜测。

### 可以这样提问

以下都是目前仓库资料可以回答的**文档问题**。

1. “列出与股票相关的 Reflexivity 使用案例，并附直接链接。”
2. “有哪些固定收益使用案例？请附每个页面的链接。”
3. “把适合 Long-only Asset Manager 的使用案例按研究类型整理出来。”
4. “有哪些由 QUICK 提供、涉及 NVIDIA、Micron、AI、半导体或数据中心的使用案例？”
5. “有哪些 Scenario Insight 使用案例？请附原始页面链接。”
6. “文档里如何解释 Reflexivity AI Connections / MCP？它可以研究什么？”
7. “哪些 AI 应用有 Reflexivity 连接指南？”
8. “文档里的 7 个 Reflexivity MCP 工具分别是什么，各自做什么？”
9. “ChatGPT 连接指南要求连接后验证什么？”
10. “Reflexivity AI 连接是否提供实时行情或历史价格序列？另外有哪些 Price History 文档？”

### 单独的功能：从 AI 应用直接使用 Reflexivity 服务

如果希望 ChatGPT、Claude 等受支持的 AI 应用**直接调用 Reflexivity**，需要连接 **Reflexivity MCP**。这与让 AI 阅读 GitHub 手册是不同的产品连接。

已获准用户可以使用 [Client Resources](https://github.com/reflexivity-kb/client-resources) 中的应用连接指南：

- [ChatGPT](https://github.com/reflexivity-kb/client-resources/blob/main/zh-cn/01-技术参考/11-AI-连接/02-应用指南/03-ChatGPT/README.md)
- [Claude](https://github.com/reflexivity-kb/client-resources/blob/main/zh-cn/01-技术参考/11-AI-连接/02-应用指南/01-Claude/README.md)
- [GitHub Copilot in VS Code](https://github.com/reflexivity-kb/client-resources/blob/main/zh-cn/01-技术参考/11-AI-连接/02-应用指南/07-GitHub-Copilot-in-VS-Code/README.md)

通过 MCP，AI 应用可以使用已文档化的 Reflexivity Insights 和 Knowledge Graph 功能。它并不是通用的实时行情或历史价格序列连接。

## 2. 直接浏览页面

如果希望自己浏览，公开 KB 分为五个主要栏目：

- **使用案例** — [研究流程和案例](01-使用案例/README.md)
- **使用指南** — [使用与入门指南](02-使用指南/README.md)
- **产品** — [产品资料](03-产品/README.md)
- **文章** — [文章和历史公开资料](04-文章/README.md)
- **发布说明** — [发布说明](05-发布说明/README.md)

使用案例还可以按 **投资者/用户类型、洞察类型、资产类别** 浏览。例如可以直接进入 [股票使用案例](01-使用案例/03-按资产类别/04-股票/README.md)。

获准用户还可以访问 [Client Resources](https://github.com/reflexivity-kb/client-resources)，其中包含 REST API 与 AI/MCP 连接相关的受限 **技术参考**。

## 3. 找不到资料时直接询问

如果找不到所需资料，请联系 **jim@reflexivity.com**。

拥有 Client Resources 访问权限的用户，也可以通过 [GitHub Discussions](https://github.com/reflexivity-kb/client-resources/discussions) 提交文档问题、澄清请求、反馈或缺失资料请求。

提问时请尽量附上 **相关页面的硬链接或页面标题**，并简要说明你原本希望找到什么内容。

请不要在 Discussions 中发布登录凭据、令牌、客户机密信息或特定客户的商业信息。

### 减少 GitHub 通知

不需要 Watch 仓库中的所有更新。建议在仓库页面选择 **Watch → Participating and @mentions**。如果完全不想收到仓库通知，可选择 **Ignore**。只有确实希望接收 Discussions 等特定事件时才使用 **Custom**。

GitHub 官方说明：[Configuring notifications](https://docs.github.com/en/subscriptions-and-notifications/get-started/configuring-notifications)
