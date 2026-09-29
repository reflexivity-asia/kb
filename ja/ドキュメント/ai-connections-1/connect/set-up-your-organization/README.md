<!--
id: RX-PRODUCT-1086
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
source_id: 6aac2306407571e9758172a7
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: current
source_route: ai-connections-1/connect/set-up-your-organization
-->

# 組織を設定する

[接続](../README.md) · [ドキュメント](../../../README.md)

**ドラフト:** この設定方法は、まだ接続テストが必要です。

チームが利用するアプリケーションでReflexivityを利用可能にしたうえで、各ユーザーに[アカウントを接続](../connect-your-account/README.md)してもらいます。

---

## 導入方法を選ぶ

| アプリケーション | 管理者が行うこと |
| --- | --- |
| Claude | Ownerがカスタムコネクタを追加し、その後メンバーが各自のアカウントを接続します。 |
| ChatGPT | 選択する方法に応じて、ワークスペースのプラグインを利用可能にするか、直接MCP接続を許可します。 |
| Claude Code / Codex | Reflexivityプラグインを確認し、組織のアプリケーションポリシーに沿って、そのマーケットプレイスを利用可能にします。 |
| Cursor | Reflexivityリポジトリをチームのマーケットプレイスに登録し、ユーザーがインストールできるようにします。 |
| GitHub Copilot | 関連する組織またはEnterpriseのポリシーで、Reflexivity MCPサーバーを許可します。 |
| Microsoft 365 Copilot | コネクタを設定し、選択したユーザーまたはグループに展開します。 |

各方法の詳細は[アプリケーション別ガイド](../../application-guides/README.md)を参照してください。プラグインリポジトリは [toggleglobal/reflexivity-ai-plugins](https://github.com/toggleglobal/reflexivity-ai-plugins) です。

---

## 全体展開の前にパイロットを行う

まずは一般ユーザー用アカウントを使う小規模なグループから開始します。文書化された手順で連携機能を見つけてインストールできること、ご自身のReflexivityアカウントでサインインできること、Reflexivityのツールを実際に呼び出せることを確認してください。

また、新しい会話でもリサーチが機能すること、サインインの有効期限が切れたり接続が無効化されたりした場合に再接続できることも確認します。

Cursorでは、プラグインがチームのマーケットプレイス、ローカルインストール、または別のアプリケーションのプラグインディレクトリのどこから利用されたかを記録してください。ある方法でのテスト成功は、他の方法も検証済みであることを意味しません。

### 各ユーザーに次の手順を明確に案内する

該当するアプリケーションガイドと[アカウントを接続する](../connect-your-account/README.md)を共有してください。

アプリケーション側で利用を承認しても、Reflexivityアカウントが作成されたり、ユーザーが自動的にサインインしたりするわけではありません。各ユーザーに、それぞれのフルReflexivityユーザーアカウントが必要です。

設定や再接続に失敗する場合は[トラブルシューティング](../../help/troubleshooting/README.md)を参照してください。

---

[← ドキュメント](../../../README.md)
