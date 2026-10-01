<!--
id: RX-PRODUCT-1001
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f233528
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: current
source_route: overview
-->
# 概要

## はじめに

Reflexivity開発者ポータルへようこそ。このドキュメントでは、Reflexivityのリサーチ機能をAIアプリケーションに接続する方法と、REST APIを使って直接連携する方法を説明します。

## 目的に応じて始める

### AIアプリケーションを接続する

まず[AI連携](../11-AI連携/README.md)を確認し、続いて[アプリケーション別ガイド](../11-AI連携/02-アプリケーション別ガイド/README.md)から利用するアプリケーションを選択してください。

各ガイドでは、接続方式、必要なアカウント条件、サインイン手順、接続確認の方法を説明しています。

### REST APIで連携する

REST APIを使うと、Reflexivityを独自のアプリケーションやワークフローに組み込めます。

以下の認証手順を確認したうえで、ナビゲーションから必要なエンドポイントを選択してください。各エンドポイントのページには、リクエストパラメータとレスポンス形式が記載されています。

このページで説明するアカウントIDとシークレットはREST API連携用です。AIアプリケーションとの接続では、各アプリケーションのサインインガイドに従ってください。

## REST APIの概要

ReflexivityのREST APIはJSON形式でレスポンスを返します。リクエストには、APIアカウントの認証情報を使って取得したBearerトークンが必要です。

エンドポイントのドキュメントには、企業間関係、リサーチインサイト、価格履歴、Alfredの会話機能などのサービスが含まれます。利用できるサービスはアカウントのアクセス権によって異なります。

## REST APIの接続先

### Production

本番環境では以下の接続先を使用します。

Authentication: [https://auth.reflexivity.com](https://auth.reflexivity.com/)

API: [https://api.reflexivity.com](https://api.reflexivity.com/)

IP address: 34.110.222.251/32

### Staging

ステージング用の認証情報でテストする場合は、以下の接続先を使用します。

Authentication: [https://auth.staging.rflx.co.uk](https://auth.staging.rflx.co.uk/)

API: [https://api.staging.rflx.co.uk](https://api.staging.rflx.co.uk/)

IP address: 35.190.21.243/32

認証情報とサービスの接続先は、必ず同じ環境のものを組み合わせてください。

## REST APIの認証

### API認証情報を取得する

APIアカウントIDとシークレットについてはReflexivityチームまでお問い合わせください。

アクセストークンを取得するときは、アカウントIDを `client_id`、アカウントシークレットを `client_secret` として使用します。

これらの認証情報は、サーバー側のアプリケーションまたはシークレットマネージャーで安全に保管してください。

### アクセストークンを取得する

認証サービスの `/oauth/token` エンドポイントに、認証情報をJSONボディとしてPOSTします。

本番環境の例:

```bash
curl --request POST 'https://auth.reflexivity.com/oauth/token' \
  --header 'Content-Type: application/json' \
  --data '{"client_id":"YOUR_ACCOUNT_ID","client_secret":"YOUR_ACCOUNT_SECRET"}'
```

`YOUR_ACCOUNT_ID` と `YOUR_ACCOUNT_SECRET` を本番環境の認証情報に置き換えてください。

ステージング環境では、ステージング用の認証情報と [https://auth.staging.rflx.co.uk/oauth/token](https://auth.staging.rflx.co.uk/oauth/token) を使用します。

正常なレスポンスには次の項目が含まれます。

- `access_token`: 以後のAPIリクエストで使用するトークン
- `token_type`: トークン種別。Bearerが返されます
- `expires_in`: トークンの有効期間（秒）
- `scope`: トークンに付与された権限

### APIリクエストを認証する

各リクエストの `Authorization` ヘッダーに、次の形式でアクセストークンを指定します。

```text
Authorization: Bearer YOUR_ACCESS_TOKEN
```

GETエンドポイントの場合は、次のようなリクエストになります。

```bash
curl --header 'Authorization: Bearer YOUR_ACCESS_TOKEN' 'https://api.reflexivity.com/ENDPOINT'
```

`YOUR_ACCESS_TOKEN` は認証サービスから返されたトークンに、`ENDPOINT` は各エンドポイントのドキュメントに記載されたパスに置き換えてください。

HTTPメソッド、パラメータ、リクエストボディは各エンドポイントの仕様に従ってください。

### 必要に応じて新しいトークンを取得する

認証レスポンスの `expires_in` を使ってトークンの有効期限を確認し、必要に応じて新しいアクセストークンを取得してください。

認証エラーが返された場合は、トークンが有効であること、および認証情報・認証サービスの接続先・APIの接続先が同じ環境に属していることを確認してください。

## 次のステップ

AIアプリケーションとの接続は[アプリケーション別ガイド](../11-AI連携/02-アプリケーション別ガイド/README.md)に進んでください。

REST API連携では、ナビゲーションから利用するエンドポイントを選び、最初のリクエストを送る前に必須パラメータ、レスポンス項目、例を確認してください。

---

[← ドキュメント](../README.md)
