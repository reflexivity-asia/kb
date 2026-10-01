<!--
id: RX-PRODUCT-1088
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
source_id: 6aac3c9f407571e9758289ca
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: current
source_route: ai-connections-1/application-guides/claude
-->

# Claude

[アプリケーション別ガイド](../README.md) · [ドキュメント](../../../README.md)

## Claudeと接続する

ClaudeのWeb版とデスクトップ版では、リモートのカスタムコネクタを使用します。フルReflexivityユーザーアカウントが必要です。

---

## コネクタを追加する

個人アカウントでは、**Customize → Connectors → + → Add custom connector** を開き、次のサーバーURLを使用します。

`https://api.reflexivity.com/external-research-mcp/mcp`

管理対象のTeamまたはEnterpriseアカウントでは、Ownerが先に **Organization settings → Connectors → Add → Custom → Web** から追加します。

---

## アカウントを接続する

**Customize → Connectors** でコネクタを選択し、**Connect** を選びます。Reflexivityへのサインインを完了したら、会話でコネクタを有効にします。

現在のアカウント要件や設定については[Claudeのコネクタ手順](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp)を参照してください。ターミナルのプラグインを使う場合は[Claude Code](../02-Claude-Code/README.md)を参照してください。

---

## 接続を確認する

会話でReflexivityを有効にし、次のように依頼します。

「Reflexivityを使って、利用可能なウォッチリストとバスケットを一覧表示してください。ツールを利用できない場合は、接続確認を完了できなかったと伝えてください。」

Reflexivityのツールが実際に結果を返すことを確認してください。空のリストは正常な場合がありますが、認証エラーや呼び出し失敗は接続確認成功ではありません。

---

## 接続が無効化された場合

コネクタ設定を開き、Reflexivityを再接続します。テストでは、Manage connectorsでツール一覧を更新すると再サインインが発生し、アクセスが回復しました。再接続後、接続確認をもう一度実行してください。

Claudeアプリからサインアウトした後、Claude Code側でも接続が無効化されたという報告があります。両方を利用している場合は、影響を受けた各アプリケーションで接続を確認してください。問題が続く場合は[トラブルシューティング](../../04-ヘルプ/01-トラブルシューティング/README.md)を参照してください。

---

[← ドキュメント](../../../README.md)
