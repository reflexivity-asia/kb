<!--
id: RX-PRODUCT-1093
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
source_id: 6ab2c9c1ad267bc33e1d530e
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: current
source_route: ai-connections-1/application-guides/gemini
-->

# Gemini

[アプリケーション別ガイド](../README.md) · [ドキュメント](../../../README.md)

GeminiをReflexivityのリサーチMCPサーバーに接続すると、企業間の関係、業界テーマ、競合企業、リサーチInsightsを利用できます。リサーチMCPアクセスが有効なReflexivityアカウントが必要です。

この接続で利用できるのは読み取り専用のリサーチツールです。Reflexivityプラグインや、そのsetup・診断コマンドはインストールされません。

---

## Gemini Webから接続する

Googleは現在、米国在住の18歳以上のユーザーで、個人のGoogle Accountを使用し、言語が英語、Keep Activityが有効な場合にカスタムappを提供しています。業務用・学校用Google Accountは現在対象外です。

ブラウザーでGeminiを開きます。

SettingsからConnected Appsへ進みます。画面によっては、Connected AppsがPersonal Intelligenceの下に表示されることがあります。

Custom appsでAdd a custom appを選び、次のサーバーアドレスを入力します。

`https://api.reflexivity.com/external-research-mcp/mcp`

Nextを選び、Reflexivityアカウントでサインインと認可の手順を完了します。

会話では `@` を入力し、接続済みappを選択してReflexivityへ依頼します。

Custom appsが表示されない場合は、アカウント要件とKeep Activityの設定を確認してください。

これらの手順は[Googleのカスタムapp接続ガイド](https://support.google.com/gemini/answer/17209137?co=GENIE.Platform%3DDesktop&hl=en)に沿っています。

---

## Gemini CLIから接続する

Gemini CLIをインストールして利用できる状態で、ターミナルから次を実行します。

```bash
gemini mcp add --transport http --scope user reflexivity-research https://api.reflexivity.com/external-research-mcp/mcp
```

これによりユーザー設定に接続が保存され、複数のプロジェクトで利用できます。

Gemini CLIを起動します。

```bash
gemini
```

Gemini CLI内で接続を認証します。

```text
/mcp auth reflexivity-research
```

ブラウザーでReflexivityアカウントへのサインインを完了し、ターミナルに戻ります。

接続と利用可能なツールを確認します。

```text
/mcp list
```

認証の有効期限が切れた場合は、`/mcp auth reflexivity-research` をもう一度実行してください。

これらのコマンドは[Gemini CLIのMCP文書](https://geminicli.com/docs/tools/mcp-server/)に沿っています。

---

## 接続を確認する

Geminiに次のように依頼します。

「Reflexivityを使って、自分のウォッチリストだけを一覧表示してください。ツールを呼び出せない場合は、接続確認を完了できなかったと伝えてください。」

Geminiが実際にReflexivityのツールを呼び出すことを確認してください。ウォッチリストが空でも接続成功の場合があります。一般知識やWeb検索だけの回答はアクセス確認になりません。

---

## 最初のリサーチ質問を試す

「Reflexivityを使ってNVIDIAの主要な業界テーマを特定し、最も強い関係性を裏付ける根拠を説明してください。」

次のような質問もできます。

「Reflexivityを使って、サイバーセキュリティのテーマに関連する企業を探してください。」

「Reflexivityを使ってMicrosoftに関するリサーチInsightsを探し、根拠を要約してください。」

---

## トラブルシューティング

サインインに成功してもリサーチツールが利用できない場合は、使用したReflexivityアカウントにリサーチMCPアクセスがあるか確認してください。

GeminiがReflexivityを使わずに回答する場合は、プロンプト内でReflexivityを明示的に指定してください。Gemini Webでは `@` から接続済みappを選択します。

Gemini CLIでは `/mcp list` で接続エラーを確認し、必要に応じて再認証してください。

問題が続く場合は、エラーメッセージと、Gemini WebまたはGemini CLIのどちらを使用しているかをReflexivityサポートへ共有してください。

---

[← ドキュメント](../../../README.md)
