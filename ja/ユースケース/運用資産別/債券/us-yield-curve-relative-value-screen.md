<!--
id: RX-USECASE-0030
type: use-case
language: ja
locale: ja
author: Reflexivity Research
published: 2026-09-15
status: published
translation_status: local-only
revised: 2026-09-27
editorial_reviewed: 2026-09-27
original_language: en
source_text_status: faithful_japanese_rendering_from_platform_research
publication_mode: faithful-source-preserving
-->

# 米国イールドカーブからスティープナー／フラットナー候補をスクリーニングする

<!-- locale-switcher:start -->
**Languages:** [English](../../../../en/usecases/byasset/fixedincome/us-yield-curve-relative-value-screen.md) · **日本語** · [한국어](../../../../ko/유스케이스/운용자산별/채권/us-yield-curve-relative-value-screen.md) · [简体中文](../../../../zh-cn/使用案例/按资产类别/固定收益/us-yield-curve-relative-value-screen.md) · [繁體中文（台灣）](../../../../zh-tw/使用案例/依資產類別/固定收益/us-yield-curve-relative-value-screen.md) · [繁體中文（香港）](../../../../zh-hk/使用案例/按資產類別/固定收益/us-yield-curve-relative-value-screen.md)
<!-- locale-switcher:end -->

[← 運用資産別ユースケース](../README.md) · [ユースケース一覧](../../README.md)

**著者:** Reflexivity Research  
**主な運用資産:** 債券（米国金利）  
**想定利用者:** 債券PM、金利運用者、相対価値運用  
**分析タイプ:** イールドカーブ、相対価値、スクリーニング

> 本ページは、Reflexivity上で実際に生成された調査結果を日本語で読みやすくしたものです。結論だけに要約せず、問い、データ、途中の判断、反証、前提・留意点、最終的な読みまで、元のストーリーをできる限り保持しています。数値・市場環境は元の調査を実行した時点のものです。

**[Reflexivityでこの調査例を開く →](https://app.reflexivity.com/app/alfred?conversationId=7a3cccb2-8503-4530-b85b-34386f208480&mode=research&activeHistorySidebarCategory=all)**

## この原資料の位置づけ

原資料は調査全体ではなく、**前の出力で判定表示とロジックが一致していなかった点を訂正したフォローアップ**です。そのため、本ページでは提供された訂正表と判断ロジックに範囲を限定して掲載しています。

## 訂正版スクリーニング表

| ペア | カーブ・スプレッド | 年率換算スプレッド | 過去分布上の位置 | ロールダウン | 判定 |
|---|---:|---:|---:|---:|---|
| 3y-2y | -9.7bp | -9.7bp | 9.6% | 23.6bp | 🟡 中立 |
| 4y-3y | -0.9bp | -0.9bp | 15.2% | 8.8bp | 🟡 中立 |
| 5y-4y | 3.3bp | 3.3bp | 28.7% | 4.2bp | 🔴 スティープ化（支払い） |
| 7y-5y | 11.8bp | 5.9bp | 37.4% | 8.5bp | 🟡 中立 |
| 8y-7y | 5.6bp | 5.6bp | 39.9% | -6.2bp | 🟡 中立 |
| 12y-8y | 20.0bp | 5.0bp | 45.5% | 14.4bp | 🔵 フラット化（受け取り） |
| 20y-12y | 20.3bp | 2.5bp | 51.9% | 0.2bp | 🟡 中立 |
| 25y-20y | -0.7bp | -0.1bp | 21.9% | -21.0bp | 🔴 スティープ化（支払い） |
| 30y-25y | -4.7bp | -0.9bp | 12.9% | -4.0bp | 🔴 スティープ化（支払い） |

## なぜ3y-2yと4y-3yは中立なのか

元の誤りは、過去分布上で低い位置にあることだけを見てスティープ化候補の色を付けた一方、**ロールダウンが大きく、保有コストが反対方向に効く**ことを表示に反映できていなかった点です。

訂正版では、3y-2yは過去分布の9.6%地点でもロールダウンが23.6bp、4y-3yは15.2%地点でもロールダウンが8.8bpのため、シグナルが相殺されるとして中立に修正されています。

## 訂正版の分布

- **スティープ化（支払い）: 3組** - 5y-4y、25y-20y、30y-25y
- **フラット化（受け取り）: 1組** - 12y-8y
- **中立: 5組** - 3y-2y、4y-3y、7y-5y、8y-7y、20y-12y

この例のポイントは、単に「過去分布上で低いからスティープ化」と判断せず、**歴史的位置とキャリー／ロールダウンを同時に見て、見た目には魅力的な候補でも中立判断へ修正する**ところにあります。

## このユースケースで確認できること

このページでは、相対価値候補を**過去分布上の位置だけで選ばず、キャリーやロールダウンを加えて判断を修正する**流れを確認できます。シグナルと保有コストが反対方向を示すときに、候補を見送る判断まで含めて検討する例です。


---

[← 運用資産別ユースケース](../README.md) · [ユースケース一覧](../../README.md)
