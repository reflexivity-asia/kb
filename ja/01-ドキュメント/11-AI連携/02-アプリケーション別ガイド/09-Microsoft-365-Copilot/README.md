<!--
id: RX-PRODUCT-1096
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
kb_imported: 2026-09-29
status: published
translation_status: current
resource: Reflexivity Documentation
-->
# Microsoft 365 Copilot

[アプリケーション別ガイド](../README.md) · [ドキュメント](../../../README.md)

---

## Microsoft 365 Copilotと接続する

**ドラフト:** この接続方法は、まだ接続テストが必要です。

Microsoft 365 Copilotは、MCPサーバーから読み取るカスタムのフェデレーションコネクタに対応しています。管理者がコネクタを設定し、選択したユーザーまたはグループが利用できるようにします。

---

## 管理者向け設定

設定対象の本番環境は次のとおりです。

https://api.reflexivity.com/external-research-mcp/mcp

MicrosoftのOAuth接続には、登録済みクライアント、認証設定、Teams Developer Portalでの登録が必要です。このページを正式な設定ガイドにする前に、Reflexivity側でこれらの設定を確認する必要があります。詳細は[Microsoftのコネクタ設定手順](https://learn.microsoft.com/en-us/microsoft-365/copilot/connectors/set-up-custom-federated-connectors)を参照してください。

---

## ユーザー向け設定

コネクタが利用可能になったら、ユーザーは外部サービスに対して認証します。Reflexivity固有のサインイン手順は検証完了後に追記します。

このガイドは業務用のMicrosoft 365 Copilotを対象としています。Copilot Studioのエージェントは別の設定方法を使用します。

---

← [GitHub Copilot CLI](../08-GitHub-Copilot-CLI/README.md) · [リサーチ](../../03-リサーチ/README.md) →
