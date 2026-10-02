# Reflexivity ナレッジベース

**言語:** [English](../en/README.md) · **日本語** · [한국어](../ko/README.md) · [简体中文](../zh-cn/README.md) · [繁體中文（台灣）](../zh-tw/README.md) · [繁體中文（香港）](../zh-hk/README.md)

このナレッジベースには幅広い資料が収録されています。最初からすべてを読む必要はありません。目的に合わせて、次の3つの使い方から選べます。

## 1. ReflexivityをAIに接続する

Reflexivityは **MCP** を通じて対応AIアプリケーションに直接接続できます。接続すると、会話の中からReflexivityの **Insights** と **Knowledge Graph** を利用できます。

これは、AIにこのGitHubドキュメントを読ませることとは別の機能です。

[Reflexivity Client Resources](https://github.com/reflexivity-kb/client-resources) へのアクセス権がある場合は、各アプリケーション向けの接続ガイドをご利用ください。

- **ChatGPT** — [ReflexivityをChatGPTに接続する](https://github.com/reflexivity-kb/client-resources/blob/main/ja/01-技術リファレンス/11-AI連携/02-アプリケーション別ガイド/03-ChatGPT/README.md)
- **Claude** — [ReflexivityをClaudeに接続する](https://github.com/reflexivity-kb/client-resources/blob/main/ja/01-技術リファレンス/11-AI連携/02-アプリケーション別ガイド/01-Claude/README.md)
- **GitHub Copilot** — [ReflexivityをGitHub Copilot in VS Codeに接続する](https://github.com/reflexivity-kb/client-resources/blob/main/ja/01-技術リファレンス/11-AI連携/02-アプリケーション別ガイド/07-GitHub-Copilot-in-VS-Code/README.md)

利用可否や検証状況は、アプリケーションやワークスペースによって異なる場合があります。設定後は、ログインできたことだけでなく、実際にReflexivityのツールを呼び出せることを確認してください。

**質問する言語に制限はありません。** お使いのAIアシスタントが対応している言語で質問できます。Reflexivity側の言語指定に対応するツールではベストエフォートで処理され、翻訳がないコンテンツは英語のまま返る場合があります。

### Reflexivityに質問してみる

以下は、現在のReflexivity MCPのドキュメントで確認できる機能に基づく質問例です。

1. 「NVIDIAの最近の決算レビューと決算プレビューを探して。」
2. 「NVIDIAに関する最近のCompany Catalystを見せて。」
3. 「NVIDIAと関連性の高いテーマを教えて。上位3テーマについて根拠も説明して。」
4. 「Artificial Intelligenceテーマに関連する企業を探して。」
5. 「Knowledge GraphでNVIDIAの主要な競合企業を調べ、関係の根拠も示して。」
6. 「この企業に関連するマクロテーマと財務テーマを、利用可能な場合はエクスポージャー方向も含めて示して。」
7. 「利用できるReflexivityのウォッチリストとバスケットを一覧にして。」
8. 「このウォッチリストまたはバスケットを対象に最近のリサーチを検索して。」
9. 「この企業のScenario Insightを探して、利用可能な予測日と数値を示して。」
10. 「このテーマに関連する企業を探し、それぞれの最近の決算リサーチを比較して。」

MCP接続の対象はReflexivityのリサーチとKnowledge Graphです。一般的なリアルタイム株価や過去価格系列を取得するための接続ではありません。

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
