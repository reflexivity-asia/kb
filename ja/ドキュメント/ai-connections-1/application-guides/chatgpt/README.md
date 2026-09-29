<!--
id: RX-PRODUCT-1090
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
source_id: 6aac3cac50675fa0b9e8c278
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: current
source_route: ai-connections-1/application-guides/chatgpt
-->

# ChatGPT

[アプリケーション別ガイド](../README.md) · [ドキュメント](../../../README.md)

## ChatGPTと接続する

---

## 現在の状況

ReflexivityのChatGPT接続は現在も検証中です。リサーチクエリが正常に動作した報告がある一方、認証後もReflexivityのツールを呼び出せないセッションがあります。接続を利用する前に、その会話でツールを実際に呼び出せることを確認してください。

---

## 設定方法を選ぶ

### ワークスペースのプラグイン

管理者がReflexivityプラグインを利用可能にしている場合は、ワークスペースで案内されているインストール方法を使用してください。Reflexivityのリポジトリは [toggleglobal/reflexivity-ai-plugins](https://github.com/toggleglobal/reflexivity-ai-plugins) です。

ワークスペースプラグインの方法では、その方法独自のインストール、認証、ツールアクセス確認が必要です。Webでの直接接続が成功しても、ワークスペースプラグインのインストールまで検証されたことにはなりません。

ワークスペースでReflexivityを利用できない場合は、代替方法を試す前に管理者へ確認するか、[support@reflexivity.com](mailto:support@reflexivity.com) までお問い合わせください。

### Webで直接接続する

アカウントとワークスペースでdeveloper-mode appsが許可されている場合は、ChatGPTのリモートMCP接続フローで[Reflexivity MCPエンドポイント](https://api.reflexivity.com/external-research-mcp/mcp)を使用します。

OpenAIでは、Settings → Security and login からdeveloper modeを設定し、ChatGPT Pluginsからappを作成する手順を案内しています。利用条件、接続制御、認証オプションについては[最新のdeveloper mode手順](https://developers.openai.com/api/docs/guides/developer-mode)を参照してください。

Reflexivityのサインインフローを完了します。この方法のReflexivity固有の認証設定は現在も検証中です。app作成またはサインインを完了できない場合はサポートへお問い合わせください。

---

## Developer modeが無効の場合

Developer modeは、ここで説明している直接カスタムMCP接続に適用されます。

ワークスペースですでにReflexivityが提供されている場合は、別の接続を作るのではなく、そのワークスペースのインストール手順から始めてください。

Webで直接接続する場合は、アカウントとワークスペースでdeveloper-mode appsが許可されているか確認します。設定項目が表示されない、または無効になっている場合は、ワークスペース管理者に許可された設定方法を確認してください。

ワークスペースで利用可能であること、サインインに成功すること、ツールを利用できることはそれぞれ別の確認項目です。インストール後、会話でReflexivityが選択されており、実際のツール呼び出しが成功することを確認してください。

OpenAIは現在、MCPサーバーを宣言するインポート済みプラグインについて、リモートHTTPSサーバーに接続するものを含めデスクトップ専用と案内しています。ワークスペースのインストール方法でサポートされるアプリケーションを使用しているか確認してください。詳細は[OpenAIのワークスペースプラグイン文書](https://learn.chatgpt.com/docs/enterprise/plugin-management)を参照してください。

---

## 会話でツールアクセスを確認する

新しい会話を開始し、Reflexivity appを選択します。developer-mode appの場合は、composerのDeveloper mode toolsから選択します。

次のように依頼してください。

「Reflexivityを使って、利用可能なウォッチリストとバスケットを一覧表示してください。Reflexivityのツールを呼び出せない場合は、接続確認を完了できなかったと伝えてください。この確認の代わりにWeb検索を使わないでください。」

ChatGPTが実際にReflexivityのツールを呼び出し、結果を受け取ることを確認します。正常な空リストは有効な結果です。認証エラー、ツール利用不可、タイムアウトがある場合は確認成功ではありません。

---

## サインイン済みだがツールが使えない

会話でReflexivityが選択されているか確認します。developer-mode appの場合は、ツール設定を確認し、appを更新して最新のツールを取得します。求められた場合は再認証し、新しい会話でもう一度確認してください。

問題が続く場合は、[support@reflexivity.com](mailto:support@reflexivity.com) に設定方法、Web/デスクトップのどちらを使用したか、わかる場合はアプリケーションのバージョン、発生時刻とタイムゾーン、正確なエラー内容を送ってください。認証情報やトークンは含めないでください。

---

## 必要な詳しさを指定する

「Reflexivityを使ってNVIDIAの主要な業界テーマを10件挙げ、最上位のテーマを裏付ける根拠を3段落で説明してください。利用可能な場合は関連日付と報告期間を含め、取得した根拠と解釈を分けてください。不足している根拠があれば明示してください。」

回答の長さや見せ方はアプリケーションや会話によって異なる場合があります。[リサーチ例](../../research/README.md)と[トラブルシューティング](../../help/troubleshooting/README.md)も参照してください。

Codexを利用する場合は[Codexガイド](../codex/README.md)を参照してください。

---

[← ドキュメント](../../../README.md)
