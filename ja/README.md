# Reflexivity ナレッジベース

**言語:** [English](../en/README.md) · **日本語** · [한국어](../ko/README.md) · [简体中文](../zh-cn/README.md) · [繁體中文（台灣）](../zh-tw/README.md) · [繁體中文（香港）](../zh-hk/README.md)

このナレッジベースには多くの資料が含まれているため、最初から最後まで順番に読む必要はありません。**このドキュメントを利用する方法**は、主に次の3つです。

1. AIにドキュメントについて質問する
2. ページを直接閲覧する
3. 見つからない資料をサポートに問い合わせる

> **重要:** このKnowledge BaseをAIに読ませて質問することと、**Reflexivityのサービス自体**をMCPでAIアプリケーションに接続することは別の機能です。MCP接続については下の別セクションで説明します。

## 1. AIにこのKnowledge Baseについて質問する

GitHub上のドキュメントをAIに参照させ、該当ページの検索、要約、比較、リンク取得などを行えます。

- **GitHub Copilot** — [reflexivity-kb/docs](https://github.com/reflexivity-kb/docs) を開き、リポジトリについてCopilotに質問するか、リポジトリをCopilotのコンテキストに追加します。[GitHubの手順](https://docs.github.com/en/copilot/tutorials/explore-a-codebase)
- **ChatGPT** — ChatGPTでGitHubを接続し、**reflexivity-kb/docs** と、アクセス権がある場合は **reflexivity-kb/client-resources** を許可して、リポジトリ内の資料について質問します。[OpenAIの手順](https://help.openai.com/ja-jp/articles/11145903-connecting-github-to-chatgpt)
- **Claude** — チャットの **Add from GitHub**、またはProject knowledgeのGitHub連携から必要なファイルやフォルダを追加します。[Claudeの手順](https://support.claude.com/en/articles/10167454-use-the-github-integration)

質問する言語は、利用するAIアシスタントが対応している言語であれば制限されません。ドキュメント原文は現在6つのロケールで公開されています。

AIには、次のように指示すると便利です。

> ReflexivityのGitHubドキュメントを情報源として使ってください。最も関連するページから回答し、参照したページへの直接リンクを付けてください。ドキュメント内に答えがない場合は、推測せずその旨を明記してください。

### 質問例

以下は、現在リポジトリに存在する資料から回答できるドキュメント質問の例です。

1. 「株式関連のReflexivityユースケースを、直接リンク付きで一覧にして。」
2. 「債券関連のユースケースには何がある？各ページへのリンクも付けて。」
3. 「ロングオンリーのアセットマネージャー向けユースケースを、リサーチ種別ごとに整理して。」
4. 「NVIDIA、Micron、AI、半導体、データセンターに関するQUICK提供のユースケースを教えて。」
5. 「Scenario Insightのユースケースには何がある？元ページへのリンクも付けて。」
6. 「ReflexivityのAI Connections / MCPとは何で、何をリサーチできる？」
7. 「Reflexivityの接続ガイドが用意されているAIアプリケーションはどれ？」
8. 「ドキュメントに記載されているReflexivity MCPの7つのツールと役割を教えて。」
9. 「ChatGPT接続ガイドでは、接続後に何を確認するよう書かれている？」
10. 「ReflexivityのAI接続でライブ価格や過去価格系列は取得できる？別途どのPrice History資料がある？」

### 別の機能: AIアプリケーションからReflexivityサービス自体を使う

ChatGPT、Claudeなどの対応AIアプリケーションから**Reflexivityを直接呼び出して使う**場合は、**Reflexivity MCP**を使う別の製品連携です。GitHubのマニュアルをAIに読ませることとは異なります。

承認済みユーザーは [Client Resources](https://github.com/reflexivity-kb/client-resources) のアプリケーション別接続ガイドを利用できます。

- [ChatGPT](https://github.com/reflexivity-kb/client-resources/blob/main/ja/01-技術リファレンス/11-AI連携/02-アプリケーション別ガイド/03-ChatGPT/README.md)
- [Claude](https://github.com/reflexivity-kb/client-resources/blob/main/ja/01-技術リファレンス/11-AI連携/02-アプリケーション別ガイド/01-Claude/README.md)
- [GitHub Copilot in VS Code](https://github.com/reflexivity-kb/client-resources/blob/main/ja/01-技術リファレンス/11-AI連携/02-アプリケーション別ガイド/07-GitHub-Copilot-in-VS-Code/README.md)

MCP接続では、ドキュメント化されているReflexivityのInsightsとKnowledge Graph機能をAIアプリケーションから利用できます。一般的なリアルタイム価格や過去価格系列を取得するための接続ではありません。

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
