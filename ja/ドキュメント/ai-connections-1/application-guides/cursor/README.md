<!--
id: RX-PRODUCT-1092
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
source_id: 6aac3cb1eaa60270142476d0
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: current
source_route: ai-connections-1/application-guides/cursor
-->

# Cursor

[アプリケーション別ガイド](../README.md) · [ドキュメント](../../../README.md)

リサーチMCPアクセスが有効なReflexivityアカウントが必要です。ここで説明するプラグイン方法はCursorのチームマーケットプレイスを利用します。その他の方法についても下記で説明します。

## 現在の状況

チームマーケットプレイス経由の設定方法は現在も検証中です。プラグインが見つからない、サインイン期限切れ後の再接続が難しいという報告があります。ローカルインストールや、Cursorが検出したClaude Codeプラグインでの成功例はありますが、すべてのアカウントでチームマーケットプレイス経由が動作することを示すものではありません。

---

## インストールしてサインインする

ステップ1: チーム管理者に [toggleglobal/reflexivity-ai-plugins](https://github.com/toggleglobal/reflexivity-ai-plugins) をチームマーケットプレイスへ登録してもらいます。

ステップ2: リポジトリが登録されたCursorアカウントとチームにサインインしていることを確認します。

ステップ3: Cursor Settings → Plugins を開き、Reflexivity Researchを探します。表示される場合はインストールします。

ステップ4: Cursor Settings → Tools & MCP を開き、必要に応じて `reflexivity-research` を有効にしてLoginを選びます。

ステップ5: ブラウザーでReflexivityへのサインインを完了し、Cursorに戻ります。

---

## プラグインが表示されない場合

管理者に、リポジトリがチームのマーケットプレイスに追加され、ご自身のアカウントで利用可能になっているか確認してもらってください。Reflexivityを検索しても見つからないことだけでは、チームマーケットプレイスが設定済みかどうかは判断できません。

それでも表示されない場合は、Cursorのバージョン、OS、Plugins画面のスクリーンショットを添えて [support@reflexivity.com](mailto:support@reflexivity.com) までお問い合わせください。パスワードやトークンは含めないでください。

### その他のインストール方法

ローカルにインポートしたReflexivityプラグインや、Reflexivity MCPサーバーへの直接接続でも成功例があります。

これらは別の設定方法です。プラグインをインストールすると、Reflexivityのsetup、doctor、researchワークフローも利用できます。直接MCP接続ではサーバーのツールは利用できますが、それらのワークフローは自動的にはインストールされません。

サポートを依頼する際は、どの方法を使ったかを明記してください。すでに動作する接続がある場合は、トラブルシューティング中に別の接続を重複して追加しないでください。

このリポジトリでは現在、チームマーケットプレイス経由の方法を文書化しています。ローカルインポートや直接接続の詳細手順は、チーム展開に使う前にご利用のCursorバージョンで検証する必要があります。

Cursorは、依頼内容と利用可能なデータに応じて、リサーチ結果をテキスト、表、可視化で表示できます。必要な形式を明示してください。

すべてのクエリでチャートやキャンバスが表示されるとは限りません。可視化は返されたデータを使用し、不足値を推測して補ってはいけません。

---

## 接続を確認する

新しいチャットを開始し、次のように依頼します。

「Reflexivity Researchを設定してください。」

セットアップフローでは、ツールの利用可否とアカウントアクセスを確認します。保存済みのウォッチリストやバスケットが0件でも正常な結果の場合があります。

続けて次のように依頼します。

「Reflexivityを使ってTeslaの主要な業界テーマを示し、最上位テーマの根拠を説明してください。」

Cursorが実際にReflexivityのツールを呼び出したことを確認してください。一般知識やWeb検索だけで生成された回答は、この接続の確認にはなりません。

---

## 動いていた接続が停止した場合

サインイン期限切れと、タイムアウトのように見えるツール呼び出しが同時に報告されています。タイムアウトだけでは原因を特定できません。

Cursor Settings → Tools & MCP を開き、`reflexivity-research` を確認し、求められた場合は再サインインします。サインイン完了後、新しいチャットで接続確認をもう一度実行してください。

次のように依頼することもできます。

「Reflexivityのdoctorワークフローで接続を確認してください。」

それでも失敗する場合は、正確なエラーを記録し、[トラブルシューティング](../../help/troubleshooting/README.md)に従ってください。

---

## リサーチ質問を試す

試せる質問は[リサーチ例](../../research/README.md)、制約については[カバレッジと情報源](../../research/coverage-and-sources/README.md)を参照してください。

出力形式は異なる場合があり、リサーチに成功してもチャートやインタラクティブな表示が必ず提供されるわけではありません。

---

[← ドキュメント](../../../README.md)
