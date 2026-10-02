# Reflexivity 知識庫

**語言：** [English](../en/README.md) · [日本語](../ja/README.md) · [한국어](../ko/README.md) · [简体中文](../zh-cn/README.md) · **繁體中文（台灣）** · [繁體中文（香港）](../zh-hk/README.md)

知識庫內容很多，不需要從頭逐頁閱讀。**使用這套 Knowledge Base 文件**主要有三種方式：

1. 讓 AI 針對這些文件回答問題
2. 直接瀏覽頁面
3. 找不到資料時聯絡支援

> **重要：** 讓 AI 讀取這套 Knowledge Base 文件，與透過 MCP 把 **Reflexivity 服務本身**連接到 AI 應用程式，是兩件不同的事。MCP 連接在下方另外說明。

## 1. 向 AI 詢問這套 Knowledge Base

讓 AI 讀取 GitHub 文件後，可以直接查找相關頁面、摘要或比較內容，並取得所需連結。

- **GitHub Copilot** — 開啟 [reflexivity-kb/docs](https://github.com/reflexivity-kb/docs)，針對目前的儲存庫向 Copilot 提問，或把儲存庫加入 Copilot 上下文。[GitHub 說明](https://docs.github.com/en/copilot/tutorials/explore-a-codebase)
- **ChatGPT** — 在 ChatGPT 中連接 GitHub，授權 **reflexivity-kb/docs**，以及在你有權限時的 **reflexivity-kb/client-resources**，再針對儲存庫內的文件提問。[OpenAI 說明](https://help.openai.com/en/articles/11145903-connecting-github-to-chatgpt)
- **Claude** — 在聊天中使用 **Add from GitHub**，或在 Project knowledge 中連接 GitHub，再選擇需要的檔案或資料夾。[Claude 說明](https://support.claude.com/en/articles/10167454-use-the-github-integration)

提問語言不受六種文件語言限制，只要你使用的 AI 助理支援即可。文件原文目前提供六個 locale。

建議這樣指示 AI：

> 請以 Reflexivity GitHub 文件為資訊來源。根據最相關的頁面回答，附上實際使用頁面的直接連結；如果文件裡沒有答案，請明確說明，不要猜測。

### 可以這樣提問

以下都是目前儲存庫資料可以回答的**文件問題**。

1. 「列出與股票相關的 Reflexivity 使用案例，並附直接連結。」
2. 「有哪些固定收益使用案例？請附每個頁面的連結。」
3. 「把適合 Long-only Asset Manager 的使用案例依研究類型整理出來。」
4. 「有哪些由 QUICK 提供、涉及 NVIDIA、Micron、AI、半導體或資料中心的使用案例？」
5. 「有哪些 Scenario Insight 使用案例？請附原始頁面連結。」
6. 「文件裡如何解釋 Reflexivity AI Connections / MCP？它可以研究什麼？」
7. 「哪些 AI 應用程式有 Reflexivity 連接指南？」
8. 「文件中的 7 個 Reflexivity MCP 工具分別是什麼，各自做什麼？」
9. 「ChatGPT 連接指南要求連接後驗證什麼？」
10. 「Reflexivity AI 連接是否提供即時行情或歷史價格序列？另外有哪些 Price History 文件？」

### 另外的功能：從 AI 應用程式直接使用 Reflexivity 服務

如果希望 ChatGPT、Claude 等支援的 AI 應用程式**直接呼叫 Reflexivity**，需要連接 **Reflexivity MCP**。這與讓 AI 讀取 GitHub 手冊是不同的產品連接。

核准使用者可以使用 [Client Resources](https://github.com/reflexivity-kb/client-resources) 中的應用程式連接指南：

- [ChatGPT](https://github.com/reflexivity-kb/client-resources/blob/main/zh-tw/01-技術參考/11-AI-連接/02-應用程式指南/03-ChatGPT/README.md)
- [Claude](https://github.com/reflexivity-kb/client-resources/blob/main/zh-tw/01-技術參考/11-AI-連接/02-應用程式指南/01-Claude/README.md)
- [GitHub Copilot in VS Code](https://github.com/reflexivity-kb/client-resources/blob/main/zh-tw/01-技術參考/11-AI-連接/02-應用程式指南/07-GitHub-Copilot-in-VS-Code/README.md)

透過 MCP，AI 應用程式可以使用已文件化的 Reflexivity Insights 與 Knowledge Graph 功能。它並不是一般即時行情或歷史價格序列的連接。

## 2. 直接瀏覽頁面

如果想自己瀏覽，公開 KB 分成五個主要區域：

- **使用案例** — [研究流程與案例](05-使用案例/README.md)
- **使用指南** — [使用與入門指南](02-使用指南/README.md)
- **產品** — [產品資料](03-產品/README.md)
- **文章** — [文章與歷史公開資料](06-文章/README.md)
- **版本說明** — [版本說明](04-版本說明/README.md)

使用案例也可以依 **投資者/使用者類型、洞察類型、資產類別** 瀏覽。例如可直接進入 [股票使用案例](05-使用案例/03-依資產類別/04-股票/README.md)。

核准使用者也可以存取 [Client Resources](https://github.com/reflexivity-kb/client-resources)，其中包含 REST API 與 AI/MCP 連接相關的受限 **技術參考**。

## 3. 找不到資料時直接詢問

如果找不到需要的資料，請聯絡 **jim@reflexivity.com**。

擁有 Client Resources 存取權限的使用者，也可以透過 [GitHub Discussions](https://github.com/reflexivity-kb/client-resources/discussions) 提交文件問題、釐清需求、回饋或缺少資料的請求。

提問時請盡量附上 **相關頁面的直接連結或頁面標題**，並簡短說明原本希望找到什麼。

請勿在 Discussions 中貼出登入憑證、權杖、客戶機密資訊或特定客戶的商業資訊。

### 減少 GitHub 通知

不需要 Watch 儲存庫中的所有更新。建議在儲存庫頁面選擇 **Watch → Participating and @mentions**。若完全不想收到儲存庫通知，可選擇 **Ignore**。只有確實需要接收 Discussions 等特定事件時才使用 **Custom**。

GitHub 官方說明：[Configuring notifications](https://docs.github.com/en/subscriptions-and-notifications/get-started/configuring-notifications)
