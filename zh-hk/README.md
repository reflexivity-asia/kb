# Reflexivity 知識庫

**語言：** [English](../en/README.md) · [日本語](../ja/README.md) · [한국어](../ko/README.md) · [简体中文](../zh-cn/README.md) · [繁體中文（台灣）](../zh-tw/README.md) · **繁體中文（香港）**

知識庫內容很多，不需要由頭逐頁閱讀。可以按需要選擇以下三種方式。

## 1. 直接用 AI 提問

把 GitHub 儲存庫連接到 AI 助手後，可以直接根據現有文件提問。

- **GitHub Copilot** — 在 GitHub 開啟 [reflexivity-kb/docs](https://github.com/reflexivity-kb/docs)，並在 Copilot Chat 中針對目前的儲存庫提問。[GitHub 說明](https://docs.github.com/en/copilot/how-tos/copilot-on-github/chat-with-copilot/get-started-with-chat)
- **ChatGPT** — 在 ChatGPT 的 **Settings → Plugins** 中連接 GitHub，並授權 ChatGPT 可以讀取的儲存庫。[OpenAI 說明](https://help.openai.com/en/articles/11145903-connecting-github-to-chatgpt)
- **Claude** — 在聊天中選擇 **+ → Add from GitHub**，或把 GitHub 加入 Project knowledge，再選擇要使用的檔案或資料夾。[Claude 說明](https://support.claude.com/en/articles/10167454-use-the-github-integration)

公開資料請加入 **reflexivity-kb/docs**。如果你已獲准存取 [Reflexivity Client Resources](https://github.com/reflexivity-kb/client-resources)，也可以一併加入該儲存庫。

**提問語言不受知識庫六種發布語言限制。** 只要你使用的 AI 助手支援，就可以使用其他語言提問。知識庫原文目前提供英文、日文、韓文、簡體中文、繁體中文（台灣）及繁體中文（香港）。

若問題需要核對出處，建議要求 AI 同時提供實際使用頁面的直接連結。

> 請以 `reflexivity-kb/docs`，以及在我有權限時的 `reflexivity-kb/client-resources` 作為資訊來源。請根據最相關的 Reflexivity 文件回答，並附上實際使用頁面的直接連結。如果儲存庫裡沒有答案，請明確說明，不要猜測。

### 可以這樣提問

以下例子都已確認可以由目前儲存庫中的現有資料回答。

**公開 Knowledge Base**

1. 「列出與股票相關的 Reflexivity 使用案例，並附上直接連結。」
2. 「有哪些固定收益使用案例？請附每個頁面的連結。」
3. 「把適合 Long-only Asset Manager 的使用案例按研究類型整理出來。」
4. 「有哪些由 QUICK 提供、涉及 NVIDIA、Micron、AI、半導體或數據中心的使用案例？」
5. 「有哪些 Scenario Insight 使用案例？請附原始頁面連結。」

**Client Resources — 需要核准的存取權限**

6. 「Reflexivity AI Connections / MCP 是甚麼？可以研究哪些內容？」
7. 「Reflexivity MCP 的 7 個工具分別是甚麼，各自做甚麼？」
8. 「如何把 Reflexivity 連接到 ChatGPT？」
9. 「如何把 Reflexivity 連接到 Claude 或 GitHub Copilot？」
10. 「Reflexivity MCP 能否提供即時報價或歷史價格序列？另外文件中的 market-close price API 是甚麼？」

## 2. 直接瀏覽頁面

如果想自己瀏覽，公開 KB 分為五個主要區域：

- **使用案例** — [研究流程及案例](01-使用案例/README.md)
- **使用指南** — [使用及入門指南](02-使用指南/README.md)
- **產品** — [產品資料](03-產品/README.md)
- **文章** — [文章及歷史公開資料](04-文章/README.md)
- **版本說明** — [版本說明](05-版本說明/README.md)

使用案例亦可按 **投資者/使用者類型、洞察類型、資產類別** 瀏覽。例如可直接進入 [股票使用案例](01-使用案例/03-按資產類別/04-股票/README.md)。

核准使用者亦可存取 [Client Resources](https://github.com/reflexivity-kb/client-resources)，其中包括 REST API 及 AI/MCP 連接相關的受限 **技術參考**。

## 3. 找不到資料時直接查詢

如果找不到需要的資料，請聯絡 **jim@reflexivity.com**。

擁有 Client Resources 存取權限的使用者，亦可透過 [GitHub Discussions](https://github.com/reflexivity-kb/client-resources/discussions) 提交文件問題、釐清要求、意見或缺少資料的請求。

提問時請盡量附上 **相關頁面的直接連結或頁面標題**，並簡短說明原本希望找到甚麼。

請勿在 Discussions 中貼出登入憑證、權杖、客戶機密資料或特定客戶的商業資料。

### 減少 GitHub 通知

不需要 Watch 儲存庫中的所有更新。建議在儲存庫頁面選擇 **Watch → Participating and @mentions**。若完全不想收到儲存庫通知，可選擇 **Ignore**。只有確實需要接收 Discussions 等特定事件時才使用 **Custom**。

GitHub 官方說明：[Configuring notifications](https://docs.github.com/en/subscriptions-and-notifications/get-started/configuring-notifications)
