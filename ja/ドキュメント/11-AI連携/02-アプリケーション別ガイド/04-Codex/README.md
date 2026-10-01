<!--
id: RX-PRODUCT-1091
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
source_id: 6aac3d4d50675fa0b9e8d365
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: current
source_route: ai-connections-1/application-guides/codex
-->

# Codex

[アプリケーション別ガイド](../README.md) · [ドキュメント](../../../README.md)

## Codexと接続する

Reflexivity ResearchはCodex CLIとデスクトップアプリで利用できます。フルReflexivityユーザーアカウントが必要です。

---

## プラグインをインストールする

ターミナルでReflexivityのマーケットプレイスを追加します。

```bash
codex plugin marketplace add toggleglobal/reflexivity-ai-plugins
```

次にCodexを開きます。

```bash
codex
```

`/plugins` を開いてReflexivityをインストールします。新しいタスクまたはセッションを開始し、次のように依頼します。

「Reflexivityを設定してください。」

接続設定はプラグインから提供されます。サインインを求められた場合は完了し、その後、以下の接続確認を実行してください。

---

## サインインする

サインインが必要な場合は、ターミナルで次を実行します。

```bash
codex mcp login reflexivity-research
```

ターミナルに表示されたサインインリンクをブラウザーで開き、Reflexivityへのサインインを完了します。その後ターミナルに戻り、確認が表示されるまで待ちます。

---

## 接続を確認する

デスクトップアプリでは、Reflexivity Researchプラグインを有効にした新しいタスクを開始します。CLIでは新しいセッションを開始します。

```bash
codex
```

次のように依頼します。

「Reflexivity Researchを設定してください。」

セットアップフローでは、ツールの利用可否とアカウントアクセスを確認します。保存済みウォッチリストが0件でも正常な場合があります。ツールが見つからない場合は、`/plugins` でプラグインが有効になっていることを確認し、新しいセッションを開始してください。

接続に問題がある場合は[トラブルシューティング](../../04-ヘルプ/01-トラブルシューティング/README.md)、質問例は[リサーチ例](../../03-リサーチ/README.md)を参照してください。

---

[← ドキュメント](../../../README.md)
