<!--
id: RX-USECASE-0064
type: use-case
language: ja
locale: ja
provider: 株式会社QUICK
provided: 2026-09-17
status: published
translation_status: local-only
revised: 2026-09-27
editorial_reviewed: 2026-09-27
source_type: partner-provided-use-case
asset_class: 株式、債券
publication_mode: faithful-source-preserving
-->

# マグニフィセント7の財務体力と金利耐性を比較する

<!-- locale-switcher:start -->
**Languages:** [English](../../../../en/usecases/byasset/equities/magnificent-seven-financial-comparison.md) · **日本語** · [한국어](../../../../ko/유스케이스/운용자산별/주식/magnificent-seven-financial-comparison.md) · [简体中文](../../../../zh-cn/使用案例/按资产类别/股票/magnificent-seven-financial-comparison.md) · [繁體中文（台灣）](../../../../zh-tw/使用案例/依資產類別/股票/magnificent-seven-financial-comparison.md) · [繁體中文（香港）](../../../../zh-hk/使用案例/按資產類別/股票/magnificent-seven-financial-comparison.md)
<!-- locale-switcher:end -->

[← 株式ユースケース](README.md) · [ユースケース一覧](../../README.md)

**提供日:** 2026-09-17  
**主な運用資産:** 株式、債券

> 本ページは株式会社QUICKから提供されたユースケースを、顧客名・宛先・メールアドレス・署名等を除き、質問から分析・結論へ進む流れを可能な限り保持して掲載しています。数値・市場環境は提供日時点のものです。

> ### [Reflexivityでこの調査例を開く →](https://app.reflexivity.com/app/alfred?mode=research&conversationId=21bf31be-608b-4468-9697-9408b296d4dc&scrollTo=top)

## 質問

**マグニフィセント7の財務状態を比較分析してください。特に資金調達や投資の状況などについて、金利変動への耐性も踏まえて分析してください。**

## 7社の資金余力はどこが違うか

この比較では、最新会計年度の財務諸表をもとに、マグニフィセント7を**流動性、負債、ネットキャッシュ、設備投資、フリーキャッシュフロー、資金調達、金利耐性**の観点から確認します。

提供日時点の高金利環境でも、大半の企業は巨額の営業キャッシュフローを持ちます。一方、AI・データセンター投資の拡大に伴い、自己資金中心の企業と社債発行を増やす企業に分かれている点が主要な論点です。

### 財務比較

| Company | Liquidity ($B) | Total Debt ($B) | Net Cash ($B) | Debt/Equity | Interest Coverage | Capex/Rev | FCF ($B) | Debt Issued ($B) |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| Alphabet | 126.8 | 52.2 | 74.7 | 0.13 | 36x | 22.7% | 73.3 | 64.6 |
| Nvidia | 62.6 | 8.8 | 53.7 | 0.06 | 64x | 2.8% | 96.7 | 0.0 |
| Tesla | 44.1 | 9.2 | 34.9 | 0.11 | 3x | 9.0% | 6.2 | 5.6 |
| Amazon | 123.0 | 91.2 | 31.8 | 0.22 | 38x | 18.4% | 7.7 | 25.0 |
| Microsoft | 76.8 | 50.0 | 26.9 | 0.11 | 706x | 34.9% | 67.0 | 0.0 |
| Meta | 81.6 | 61.3 | 20.3 | 0.28 | 87x | 34.7% | 46.1 | 29.9 |
| Apple | 54.7 | 100.8 | -46.1 | 1.37 | net income* | 3.1% | 98.8 | 4.5 |

![流動性・負債・ネットキャッシュの比較](../../../画像/ユースケース/quick/RX-USECASE-0064/01-liquidity-debt-net-cash.webp)

![設備投資強度とフリーキャッシュフローの比較](../../../画像/ユースケース/quick/RX-USECASE-0064/02-capex-fcf.webp)

## 比較から見える4つの違い

1. **ネットキャッシュの二極化**  
   Appleのみがネット負債で、他6社はネットキャッシュ。Alphabetが約747億ドルと最も厚いとされています。

2. **投資強度の格差**  
   MicrosoftとMetaは売上比約35%の設備投資強度で、AmazonもFCFが77億ドルまで圧縮されるほど投資を拡大。一方、NvidiaとAppleは資産効率型です。

3. **資金調達の分岐**  
   Alphabet・Amazon・MetaはAI投資を補完するため社債発行を増やす一方、Nvidia・Microsoftは負債増加が限定的です。

4. **金利耐性にも差**  
   Microsoftのインタレストカバレッジは706倍、Metaは87倍と高水準。Teslaは約3倍で、7社の中では金利上昇に相対的に弱いと整理されています。

## 金利上昇局面での見方

金利上昇局面では、次の3群に整理できます。

- **最も強靭**：Microsoft、Nvidia  
  低レバレッジ、巨額ネットキャッシュ、高い利払い余力を持ちます。
- **中位・借入依存増**：Alphabet、Amazon、Meta  
  投資拡大に伴う社債発行は増えていますが、営業キャッシュフローが大きく、現時点のカバレッジは健全です。
- **相対的に脆弱**：Apple、Tesla  
  Appleは唯一のネット負債、Teslaは収益力・カバレッジが相対的に低いとされています。

ここから、単純な「現金が多い企業」比較ではなく、**AI投資の強度、社債発行の増加、借換えコスト、利払い余力まで同じ表で確認する**ことができます。

## 分析上の留意点

- 会計年度末は各社で異なり、厳密な同時点比較ではありません。
- Appleは純支払利息が財務諸表上ほぼ相殺されるため、カバレッジ倍率を算出せず営業利益との比較で評価しています。
- 総負債はリース債務の扱いなどで各社定義が異なる可能性があります。
- 金利感応度は固定・変動金利の内訳まで反映していません。

さらに、各社の債務満期構成、固定・変動金利の内訳、直近四半期の投資ガイダンスまで掘り下げると、金利感応度をより詳細に確認できます。

---

本コンテンツは、株式会社QUICKよりご提供いただいたものです。

国・地域や言語環境、利用製品、データ提供範囲などによっては、内容をそのまま適用できない場合があります。

[← 株式ユースケース](README.md) · [ユースケース一覧](../../README.md)
