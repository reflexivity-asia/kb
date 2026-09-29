<!--
id: RX-PRODUCT-1098
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
kb_imported: 2026-09-29
status: published
translation_status: current
resource: Reflexivity Documentation
-->
# カバレッジと情報源

[リサーチ](../README.md) · [ドキュメント](../../../README.md)

---

### 利用できるリサーチ

Insightsには、決算レビュー、決算プレビュー、Company Catalyst、Market Catalyst、Scenario Insightsが含まれます。Knowledge Graphでは、テーマ、製品、国・地域、競合企業など、企業との関係性を扱います。利用可否は企業、テーマ、リサーチ種別、対象期間によって異なります。

検索対象期間の既定値は直近30日です。過去のリサーチを探す場合は、より長い期間を指定してください。企業名やtickerが曖昧な場合はexchangeも指定します。テーマ検索はReflexivityで定義されたテーマにマッチするため、回答内で実際に選択されたテーマを確認してください。

### フィルターと出力上の制約

現在文書化されているMCPのリサーチインターフェースでは、subject、research type、保存済みwatchlist／basket、日付範囲で絞り込めます。一方、Star ratingのフィルターや返却フィールドは公開されていません。そのため「7 stars以上のinsight」のような条件は、この接続では確実にフィルターできません。

MCPインターフェースと、別のReflexivity製品APIでは、利用できるフィールドやフィルターが必ずしも同じではありません。この接続で対応する入力値は[MCPツールリファレンス](../../reference/mcp-tool-reference/README.md)を参照してください。

返された情報の見せ方は利用するAIアプリケーションによって異なります。回答の長さ、表、ビジュアル出力には差があります。必要な形式と詳細度を明示し、取得できない根拠や未対応の表示形式はそのまま明記してください。

---

### 3種類のテーマ

| テーマ | 意味 | 例 |
| --- | --- | --- |
| Industry | 企業が何をしているか。製品、サービス、能力、経済における役割 | AI Chips、Renewable Energy |
| Financial | 企業の財務状態、業績、経営判断 | Revenue Growth、Capital Allocation |
| Macro | 企業に影響する外部要因 | Interest Rate Changes、Tariff Implementations |

テーマとの関係があることは、根拠のあるエクスポージャーを示しますが、その企業が投資対象として魅力的であることを意味しません。

---

### ランキングと方向性

企業側のテーマランキングは、**その企業にとってどのテーマが重要か**を示します。Rank 1は、そのテーマグループ内で最も強い関係です。

Industry Theme側の企業ランキングは、**そのテーマにとってどの企業が重要か**を示します。この2種類のランキングは独立して評価されます。あるテーマが小規模企業の事業にとって極めて重要でも、その企業がテーマ全体では相対的に小さな位置づけになることがあります。両者を同じランキングとして扱わないでください。

rankは相対的な関係を示す値であり、売上比率、確率、リターン予測ではありません。この接続で公開されている結果はrankであり、基礎手法で説明される数値ウェイトそのものではありません。

FinancialとMacroのエクスポージャーには方向性があります。

- **Positive:** 根拠が企業に有利な影響を示している
- **Negative:** 根拠が企業に不利な影響を示している
- **Neutral:** 影響が混在、相殺、方向性なし、または不明確

方向性は企業ごとに異なります。Industry Themeにはpositive／negativeの方向性はありません。

---

### 根拠の情報源

Company-Themeの関係性は、年次・四半期の開示資料、決算説明会Transcript、Report、Presentationなど企業の一次開示情報から構築されます。複数の開示資料に含まれる裏付けを反映し、最近の資料がより強く影響します。

この接続では関係性の説明、根拠テキスト、document IDが返る場合があります。詳細度は関係性によって異なり、説明文だけが返る場合もあります。document IDはクリック可能なsource linkではありません。公開済みリサーチにはReflexivity referenceと日付がありますが、回答に元資料そのものが含まれるとは限りません。

---

### 日付と欠落結果

決算リサーチでは、**reporting period**、**publication date**、**last-updated date**の3つを分けて扱ってください。reporting periodはtitleまたは本文に記載されます。更新日が新しくても、そのレポートが最新四半期を扱っているとは限りません。レスポンスのas-of timestampも、リサーチ公開日や元コンテンツがその時刻に更新されたことを示すものではありません。

すべてのsourceが利用可能な状態で検索結果が空なら、その検索条件に合うリサーチが返らなかったことを意味します。source unavailableまたはomitted itemがある場合は、リクエストの一部を完了できていません。結論を出す前に、欠落した結果を確認してください。

[リサーチ](../README.md)、Troubleshooting、または[MCPツールリファレンス](../../reference/mcp-tool-reference/README.md)も参照してください。

---

← [リサーチ](../README.md) · [ヘルプ](../../help/README.md) →
