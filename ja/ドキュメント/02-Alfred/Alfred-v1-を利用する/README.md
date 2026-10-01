<!--
id: RX-PRODUCT-1003
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f233530
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: current
source_route: alfred/consuming-alfred
-->
# 🧠 Alfred v1 を利用する

このガイドでは、自律型金融アナリストである[Alfred](../README.md)をシステムに組み込む方法を説明します。Alfred v1 APIはストリーミング形式のインターフェースを提供し、金融分析ワークフローごとに異なる機能を持つReflexivityの各アシスタントと連携できます。

## 🔐 認証

[概要の認証セクション](../../01-概要/README.md)の手順で認証トークンを取得し、すべてのリクエストの `Authorization` ヘッダーに指定します。

```text
Authorization: Bearer YOUR_ACCESS_TOKEN
```

## 📡 リクエスト

### HTTPメソッド

`POST`

### ヘッダー

| Header | Type | 必須 | 説明 |
|---|---|---:|---|
| `Authorization` | `string` | はい | Bearerトークンによる認証 |
| `Content-Type` | `string` | はい | `application/json` を指定 |

### リクエストボディ

```ts
{
  question: string;        // ユーザーの質問
  session_id: string;      // 一意のセッションID（UUID形式）
  target?: string;         // 任意: 対象アシスタント
  ancillary?: {            // 任意: 追加コンテキスト
    documents?: string[];  // コンテキストとして使うDocument ID
  };
}
```

#### 指定できるReflexivityアシスタント

- `"all"`（デフォルト）: すべてのアシスタントにルーティング
- `"document-assistant"`: ドキュメント分析
- `"scenario-assistant"`: シナリオ分析
- `"chart-assistant"`: チャート生成
- `"fallback-assistant"`: 一般的な回答

## 📊 レスポンスストリーム

### ストリーム形式

レスポンスは複数のJSONオブジェクトとしてストリーミングされます。各オブジェクトは特定のサービスからのレスポンスを表します。

```ts
{
  source: string;      // レスポンスの送信元
  data: {
    confidence: number;        // 信頼度スコア（0〜1）
    scores: Record<string, any>; // 詳細なスコア内訳
    [key: string]: any;        // サービス固有の追加データ
  };
  request_id: string;  // リクエストのsession_idに対応
}
```

### レスポンスの種類

#### 1. 📑 Document Assistant

[Document Assistant](https://support.reflexivity.com/hc/en-us/articles/27023208583444-What-is-Document-Search-and-how-does-it-work)は、Reflexivityにインデックスされた金融・経済ドキュメントを参照してユーザーの質問に回答します。通常のテキストに加え、表やチャートからデータを取得できます。

```json
{
  "source": "document-assistant",
  "data": {
    "message": "string",
    "citationsResult": {
      "citations": {}
    },
    "citation_group_id": "string",
    "overview": {
      "documents": 0,
      "companies": 0,
      "document_types": {},
      "industries": {}
    }
  }
}
```

#### 2. 🔮 Scenario Assistant

[Scenario Analysis Assistant](https://support.reflexivity.com/hc/en-us/articles/27023105377556-What-is-Scenario-Analysis-and-how-does-it-work)は、過去データを使ったシナリオ分析を実行します。

```ts
{
  source: "scenario-assistant";
  data: {
    conditions: Array<any>;
    entities: Array<any>;
    actions?: Array<any>;
  };
}
```

#### 3. 📈 Chart Assistant

[Chart Assistant](https://support.reflexivity.com/hc/en-us/articles/27023168045716-What-is-Chart-and-how-does-it-work)は、Reflexivityの[Calculatorサービス](../../03-計算/README.md)が保持するファンダメンタル、テクニカル、経済データの系列を描画するために使用します。

```ts
{
  source: "chart-assistant";
  data: {
    assets: Array<any>;
    start?: string;
    end?: string;
    horizon?: "OneDay" | "OneWeek" | "TwoWeeks" | "OneMonth" | "TwoMonths" | "ThreeMonths" | "SixMonths" | "OneYear" | "ThreeYears" | "FiveYears" | "TenYears" | "Max";
    resample?: "1D" | "1W" | "1M" | "1h" | "30m" | "15m" | "5m" | "1m";
    series_type?: "line" | "candlestick" | "bars";
    y_axis_type?: "split" | "merged";
  };
}
```

Alfredからのレスポンス例:

```json
{
  "source": "chart-assistant",
  "data": {
    "assets": [
      {
        "is_default": false,
        "snake": "aapl_nasd.pe_ibes_trailing_12m",
        "tag": "aapl_nasd"
      },
      {
        "is_default": false,
        "snake": "googl_nasd.pe_ibes_trailing_12m",
        "tag": "googl_nasd"
      }
    ],
    "confidence": 0.9998950958251953,
    "horizon": "ThreeMonths",
    "price_display": "price",
    "resample": "1D",
    "series_type": "line",
    "y_axis_type": "split"
  },
  "request_id": "7adbdd1c-d786-4c43-971f-56ced7db6df4"
}
```

#### 4. 📰 Fallback Assistant

[Fallback Assistant](https://support.reflexivity.com/hc/en-us/articles/27677451697172-What-is-the-General-Knowledge-Base)は、ニュースなどの一般的な金融情報源から回答を取得します。回答文字列はMarkdown形式で返され、次のようなリンクを含む場合があります。

```md
- [Investopedia](https://www.investopedia.com/dow-jones-today-04022025-11707447 "article")
- [MT Newswires](149530a5-7619-4812-8983-9f63f86b0c93 "internal_news")
```

レスポンススキーマ:

```ts
{
  source: "fallback-assistant";
  data: {
    answer: string;
  };
}
```

## ⚠️ エラーレスポンス

### 認証エラー

```json
{
  "status": 401,
  "message": "Unauthorized"
}
```

### 不正なリクエスト

```json
{
  "status": 400,
  "message": "Invalid request parameters"
}
```

## 🧪 利用例

### curlリクエスト

```bash
curl -X POST 'https://api.example.com/alfred/v1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{
    "question": "What are Tesla'''s latest financial results?",
    "session_id": "123e4567-e89b-12d3-a456-426614174000",
    "target": "document-assistant"
  }'
```

## 📝 補足

- APIレスポンスはストリーミングされます。
- レスポンスはチャンクに分割され、各チャンクは完全なJSONオブジェクトです。
- ストリームは完了シグナルまたはエラーで終了します。
- 利用プランに応じてレート制限が適用されます。
- すべてのタイムスタンプはISO 8601形式です。

## 🤝 サポート

- ヘルプセンター: [Reflexivityを使い始める](https://support.reflexivity.com/hc/en-us/articles/26906922816404-What-is-Reflexivity)
- お問い合わせ: [support@reflexivity.com](mailto:support@reflexivity.com)

---

[← ドキュメント](../../README.md)
