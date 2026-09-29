<!--
id: RX-PRODUCT-1089
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
source_id: 6aac3ca5eaa6027014247675
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: current
source_route: ai-connections-1/application-guides/claude-code
-->

# Claude Code

[アプリケーション別ガイド](../README.md) · [ドキュメント](../../../README.md)

## Claude Codeと接続する

ここではターミナル上のClaude Codeを使用します。フルReflexivityユーザーアカウントが必要です。

---

## プラグインをインストールする

```bash
claude plugin marketplace add toggleglobal/reflexivity-ai-plugins
claude plugin install reflexivity@reflexivity
```

新しいセッションを開始し、次を入力します。

```text
/reflexivity:setup
```

接続設定はプラグインから提供されます。認証を求められた場合は `/mcp` を開き、`reflexivity-research` を選択して **Authenticate** を選びます。ブラウザーでReflexivityにサインインし、Claude Codeに戻ります。

---

## 接続を確認する

セットアップフローでは、リサーチツールが利用可能か、アカウントにアクセス権があるかを確認します。保存済みのウォッチリストやバスケットが0件でも正常な場合があります。

ツールが見つからない場合は `/reload-plugins` を実行し、もう一度 `/mcp` を確認してください。その他の問題は[トラブルシューティング](../../help/troubleshooting/README.md)を参照してください。

[質問例](../../research/README.md)も参照してください。

---

## 以前使えていた接続が動かなくなった場合

`/mcp` を開いて `reflexivity-research` を確認します。求められた場合は再認証し、新しいセッションで `/reflexivity:setup` をもう一度実行してください。

テストでは、Claudeアプリからサインアウトした後にClaude Codeの接続が無効化されたという報告がありました。影響を受けたコネクタのツール一覧を更新すると再認証が発生し、アクセスが回復しました。複数のClaudeアプリケーションを利用している場合は、それぞれの接続を確認してください。

診断には `/reflexivity:doctor` を実行します。問題が続く場合は[トラブルシューティング](../../help/troubleshooting/README.md)に従ってください。

---

[← ドキュメント](../../../README.md)
