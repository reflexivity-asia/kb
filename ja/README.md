# Reflexivity ナレッジベース

**言語:** [English](../en/README.md) · **日本語** · [한국어](../ko/README.md) · [简体中文](../zh-cn/README.md) · [繁體中文（台灣）](../zh-tw/README.md) · [繁體中文（香港）](../zh-hk/README.md)

このナレッジベースには幅広い資料が収録されています。最初からすべてを読む必要はありません。目的に合わせて、次の3つの使い方から選べます。

## 1. AIに質問する

GitHubリポジトリをAIアシスタントに接続し、公開されているドキュメントをもとに直接質問できます。

- **GitHub Copilot** — GitHubで [reflexivity-kb/docs](https://github.com/reflexivity-kb/docs) を開き、Copilot Chatで現在のリポジトリについて質問します。[GitHubの手順](https://docs.github.com/en/copilot/how-tos/copilot-on-github/chat-with-copilot/get-started-with-chat)
- **ChatGPT** — ChatGPTの **Settings → Plugins** からGitHubを接続し、読み取りを許可するリポジトリを選択します。[OpenAIの手順](https://help.openai.com/ja-jp/articles/11145903-github%E3%82%92chatgpt%E3%81%AB%E6%8E%A5%E7%B6%9A%E3%81%99%E3%82%8B)
- **Claude** — チャットで **+ → Add from GitHub** を選ぶか、Project knowledgeにGitHubを追加し、使用するファイルやフォルダを選択します。[Claudeの手順](https://support.claude.com/en/articles/10167454-use-the-github-integration)

公開資料には **reflexivity-kb/docs** を追加してください。[Reflexivity Client Resources](https://github.com/reflexivity-kb/client-resources) の利用権限がある場合は、そちらも追加できます。

**質問できる言語は、KBが公開している6言語に限定されません。** お使いのAIアシスタントが対応している言語で質問できます。KBの原文は現在、英語、日本語、韓国語、簡体字中国語、繁体字中国語（台湾）、繁体字中国語（香港）で公開されています。

出典が重要な質問では、利用したページのリンクを必ず示すようAIに指示することをおすすめします。

> `reflexivity-kb/docs` と、アクセス権がある場合は `reflexivity-kb/client-resources` を情報源として使用してください。Reflexivityの最も関連するドキュメントから回答し、参照したページへの直接リンクを付けてください。リポジトリ内に答えがない場合は推測せず、その旨を明記してください。

### 質問例

以下は、現在リポジトリ内に実際に存在する資料で回答できることを確認した例です。

**公開ナレッジベース**

1. 「株式関連のReflexivityユースケースを、直接リンク付きで一覧にして。」
2. 「債券関連ではどんなユースケースがある？各ページへのリンクも付けて。」
3. 「ロングオンリーのアセットマネージャー向けユースケースを、リサーチ種別ごとに整理して。」
4. 「NVIDIA、Micron、AI、半導体、データセンターに関するQUICK提供のユースケースを教えて。」
5. 「Scenario Insightのユースケースには何がある？元ページへのリンクも付けて。」

**Client Resources — 承認済みアクセスが必要**

6. 「ReflexivityのAI Connections / MCPとは何？何をリサーチできる？」
7. 「Reflexivity MCPの7つのツールと、それぞれの役割を教えて。」
8. 「ReflexivityをChatGPTに接続する方法を教えて。」
9. 「ReflexivityをClaudeまたはGitHub Copilotに接続する方法を教えて。」
10. 「Reflexivity MCPでライブ価格や過去の価格系列は取得できる？別途記載されている市場終値APIは何？」

## 2. ページを直接見る

手動で探したい場合、公開KBは次の5つのコレクションに分かれています。

- **ユースケース** — [リサーチワークフローと事例](01-ユースケース/README.md)
- **利用ガイド** — [利用・オンボーディングガイド](02-利用ガイド/README.md)
- **製品** — [製品資料](03-製品/README.md)
- **記事** — [記事・過去の公開資料](04-記事/README.md)
- **リリース** — [リリースノート](05-リリース/README.md)

ユースケースは **運用者別・洞察タイプ別・運用資産別** に閲覧できます。たとえば [株式ユースケース](01-ユースケース/03-運用資産別/04-株式/README.md) から直接探せます。

承認済みユーザーは [Client Resources](https://github.com/reflexivity-kb/client-resources) も利用でき、REST APIやAI/MCP接続に関するアクセス制限付きの **技術リファレンス** を参照できます。

## 3. 見つからない資料はサポートに質問する

必要な資料が見つからない場合は **jim@reflexivity.com** までご連絡ください。

Client Resourcesへのアクセス権があるユーザーは、[GitHub Discussions](https://github.com/reflexivity-kb/client-resources/discussions) から、ドキュメントの質問、確認、フィードバック、未掲載資料のリクエストを投稿することもできます。

お問い合わせの際は、可能であれば **該当ページのURL（ハードリンク）またはページタイトル** と、「何を探していたか」を短く添えてください。

Discussionsには、認証情報、トークン、顧客機密情報、顧客固有の商業情報を投稿しないでください。

### GitHub通知を減らす

すべての更新をWatchする必要はありません。リポジトリ画面の **Watch** から、通常は **Participating and @mentions** を選ぶのがおすすめです。通知が不要なら **Ignore** を選択できます。Discussionsなど特定のイベントだけを受け取りたい場合のみ **Custom** を利用してください。

GitHub公式: [Configuring notifications](https://docs.github.com/en/subscriptions-and-notifications/get-started/configuring-notifications)
