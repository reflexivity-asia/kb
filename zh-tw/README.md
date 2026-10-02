# Reflexivity 知識庫

**語言：** [English](../en/README.md) · [日本語](../ja/README.md) · [한국어](../ko/README.md) · [简体中文](../zh-cn/README.md) · **繁體中文（台灣）** · [繁體中文（香港）](../zh-hk/README.md)

知識庫內容很多，不需要從頭逐頁閱讀。可以依需求選擇以下三種方式。

## 1. 將 Reflexivity 連接到 AI

Reflexivity 可以透過 **MCP** 直接連接到支援的 AI 應用程式。連接後，可以在對話中使用 Reflexivity 的 **Insights** 與 **Knowledge Graph** 功能。

這與單純讓 AI 讀取這個 GitHub 文件儲存庫是兩回事。

如果你已獲准存取 [Reflexivity Client Resources](https://github.com/reflexivity-kb/client-resources)，請使用對應應用程式的連接指南：

- **ChatGPT** — [將 Reflexivity 連接到 ChatGPT](https://github.com/reflexivity-kb/client-resources/blob/main/zh-tw/01-技術參考/11-AI-連接/02-應用程式指南/03-ChatGPT/README.md)
- **Claude** — [將 Reflexivity 連接到 Claude](https://github.com/reflexivity-kb/client-resources/blob/main/zh-tw/01-技術參考/11-AI-連接/02-應用程式指南/01-Claude/README.md)
- **GitHub Copilot** — [將 Reflexivity 連接到 GitHub Copilot in VS Code](https://github.com/reflexivity-kb/client-resources/blob/main/zh-tw/01-技術參考/11-AI-連接/02-應用程式指南/07-GitHub-Copilot-in-VS-Code/README.md)

不同應用程式與工作區的可用性及驗證狀態可能不同。設定完成後，請確認 AI 實際能夠呼叫 Reflexivity 工具，而不只是登入成功。

**提問語言沒有限制。** 只要你的 AI 助理支援，就可以使用該語言提問。Reflexivity 工具在支援語言偏好的功能中以 best-effort 方式處理；若沒有對應翻譯，部分內容可能仍以英文回傳。

### 可以這樣使用 Reflexivity

以下問題都基於目前 Reflexivity MCP 文件中已說明的功能。

1. 「查找 NVIDIA 最近的 Earnings Recap 與 Earnings Preview。」
2. 「顯示最近與 NVIDIA 有關的 Company Catalyst 研究。」
3. 「NVIDIA 關聯度最高的主題有哪些？請說明前三個主題背後的依據。」
4. 「查找與 Artificial Intelligence 主題相關的公司。」
5. 「在 Knowledge Graph 中查找 NVIDIA 的主要競爭對手，並顯示關係依據。」
6. 「顯示這家公司相關的總體與財務主題，並在有資料時提供 exposure direction。」
7. 「列出我可以使用的 Reflexivity watchlist 與 basket。」
8. 「在這個 watchlist 或 basket 中搜尋最近的研究。」
9. 「查找這家公司的 Scenario Insight，並顯示可用的預測日期與數值。」
10. 「先查找與這個主題相關的公司，再比較這些公司的近期財報研究。」

MCP 連接用於 Reflexivity 研究與 Knowledge Graph 工作流程，並不是用於一般即時行情或歷史價格序列查詢。

## 2. 直接瀏覽頁面

如果想自己瀏覽，公開 KB 分成五個主要區域：

- **使用案例** — [研究流程與案例](01-使用案例/README.md)
- **使用指南** — [使用與入門指南](02-使用指南/README.md)
- **產品** — [產品資料](03-產品/README.md)
- **文章** — [文章與歷史公開資料](04-文章/README.md)
- **版本說明** — [版本說明](05-版本說明/README.md)

使用案例也可以依 **投資者/使用者類型、洞察類型、資產類別** 瀏覽。例如可直接進入 [股票使用案例](01-使用案例/03-依資產類別/04-股票/README.md)。

核准使用者也可以存取 [Client Resources](https://github.com/reflexivity-kb/client-resources)，其中包含 REST API 與 AI/MCP 連接相關的受限 **技術參考**。

## 3. 找不到資料時直接詢問

如果找不到需要的資料，請聯絡 **jim@reflexivity.com**。

擁有 Client Resources 存取權限的使用者，也可以透過 [GitHub Discussions](https://github.com/reflexivity-kb/client-resources/discussions) 提交文件問題、釐清需求、回饋或缺少資料的請求。

提問時請盡量附上 **相關頁面的直接連結或頁面標題**，並簡短說明原本希望找到什麼。

請勿在 Discussions 中貼出登入憑證、權杖、客戶機密資訊或特定客戶的商業資訊。

### 減少 GitHub 通知

不需要 Watch 儲存庫中的所有更新。建議在儲存庫頁面選擇 **Watch → Participating and @mentions**。若完全不想收到儲存庫通知，可選擇 **Ignore**。只有確實需要接收 Discussions 等特定事件時才使用 **Custom**。

GitHub 官方說明：[Configuring notifications](https://docs.github.com/en/subscriptions-and-notifications/get-started/configuring-notifications)
