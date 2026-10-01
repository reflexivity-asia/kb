<!--
id: RX-USECASE-0033
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

# 債券市場の動きが株式の先行リターンと関係するか検証する

<!-- locale-switcher:start -->
**Languages:** [English](../../../../en/01-use-cases/03-asset-class/05-multi-asset/bond-signals-vs-forward-equity-returns.md) · **日本語** · [한국어](../../../../ko/01-유스케이스/03-운용자산별/05-멀티에셋/bond-signals-vs-forward-equity-returns.md) · [简体中文](../../../../zh-cn/01-使用案例/03-按资产类别/05-多资产/bond-signals-vs-forward-equity-returns.md) · [繁體中文（台灣）](../../../../zh-tw/01-使用案例/03-依資產類別/05-多資產/bond-signals-vs-forward-equity-returns.md) · [繁體中文（香港）](../../../../zh-hk/01-使用案例/03-按資產類別/05-多資產/bond-signals-vs-forward-equity-returns.md)
<!-- locale-switcher:end -->

[← 運用資産別ユースケース](../README.md) · [ユースケース一覧](../../README.md)

**著者:** Reflexivity Research  
**主な運用資産:** 債券、株式、複数資産  
**想定利用者:** マルチアセットPM、クオンツ、アセットアロケーター  
**分析タイプ:** 複数資産分析、時系列分析、仮説検証

> 本ページは、Reflexivity上で実際に生成された調査結果を日本語で読みやすくしたものです。結論だけに要約せず、問い、データ、途中の判断、反証、前提・留意点、最終的な読みまで、元のストーリーをできる限り保持しています。数値・市場環境は元の調査を実行した時点のものです。

**[Reflexivityでこの調査例を開く →](https://app.reflexivity.com/app/alfred?conversationId=1ae89f55-bd78-4dfe-a303-65f8d4843d05&mode=research&activeHistorySidebarCategory=all)**

## 実際に検証したこと

「債券側のスプレッドが大きく動いたとき、その後のS&P 500リターンに傾向があるか」を、**現在値を過去分布の中に置く**形で検証した調査です。

## 散布図の作り方

- 標本数: **1,244の日次観測値**
- 期間: **2021年9月〜2026年8月**
- X軸: 対象スプレッドを小さい順から大きい順へ並べる
- Y軸: **20営業日先のS&P 500リターン**
- 最新スプレッドを別の系列として強調表示

この設定で1,244個の観測値を散布図にすると、最新値が過去分布のどこに位置するかと、同じ水準で将来リターンがどれほどばらついたかを同時に見られます。

![債券シグナルと株式の先行リターン](../../../../assets/usecases/reflexivity/RX-USECASE-0033/chart-1.webp)

*債券市場のシグナルと、その後の株式リターンを観測値ごとに比較した散布図。*

## 元の調査の読み

- 最新スプレッド: **+7.72**（2026-09-01時点）
- 5年間のスプレッドと20営業日先S&P 500リターンの相関: **-0.22**
- 高いスプレッドは平均より低い先行リターン側にやや傾くものの、同じX水準でYの分散が非常に広く、**シグナルは弱い**と評価

重要なのは、調査が「債券シグナルが株を予測できる」と強い結論を作らなかったことです。むしろ、**仮説を定量化した結果、相関が弱いこと自体を結論として残している**点がこのユースケースの核です。

## 最新値マーカーの意味

最新値のマーカーはY=0に置かれていますが、これは**現在のスプレッドがX軸のどこにあるかを示す視覚上の基準**です。まだ観測できない未来20営業日のリターンを予測した値ではありません。

## 分析上の留意点

- 20営業日先を見る窓が重複している
- -0.22は全標本を一本の直線関係で要約した値にすぎない
- 対象期間が特定の市場局面に偏る可能性がある
- スプレッドの定義や期間を変えると結果が変わり得る

このように、複数資産にまたがる経験則を「それらしい説明」で終わらせず、実際の時系列に載せて**効いていない可能性まで確認する**のがこの調査のストーリーです。

## このユースケースで確認できること

このページでは、債券側のシグナルを株式の先行リターンと結び付ける仮説を、散布図と相関で検証する流れを確認できます。**関係が弱いという結果もそのまま残し、仮説に都合のよい結論へ寄せない**点がこの例の要点です。


---

[← 運用資産別ユースケース](../README.md) · [ユースケース一覧](../../README.md)
