<!--
id: RX-USECASE-0033
type: use-case
language: zh
locale: zh-HK
author: Reflexivity Research
published: 2026-09-15
status: published
translation_status: current
original_language: en
source_text_status: localized_from_en_canonical
publication_mode: faithful-source-preserving
-->

# 測試債券市場指標與未來股票回報是否有關

<!-- locale-switcher:start -->
**Languages:** [English](../../../../en/02-use-cases/03-asset-class/05-multi-asset/bond-signals-vs-forward-equity-returns.md) · [日本語](../../../../ja/02-ユースケース/03-運用資産別/05-マルチアセット/bond-signals-vs-forward-equity-returns.md) · [한국어](../../../../ko/01-유스케이스/03-운용자산별/05-멀티에셋/bond-signals-vs-forward-equity-returns.md) · [简体中文](../../../../zh-cn/01-使用案例/03-按资产类别/05-多资产/bond-signals-vs-forward-equity-returns.md) · [繁體中文（台灣）](../../../../zh-tw/01-使用案例/03-依資產類別/05-多資產/bond-signals-vs-forward-equity-returns.md) · **繁體中文（香港）**
<!-- locale-switcher:end -->

[← 多資產使用案例](README.md) · [按資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)

**作者：** Reflexivity Research  
**主要資產：** 固定收益、股票、跨資產  
**適用使用者：** Multi-Asset PM、Quant、Asset Allocator  
**分析類型：** 跨資產分析、時間序列、假設測試

> 本頁保留一項實際 Reflexivity 研究的分析邏輯。數字與市場觀察均屬原研究日期的歷史快照，不代表當前市場判斷。

**[在 Reflexivity 中開啟這個研究示例 →](https://app.reflexivity.com/app/alfred?conversationId=1ae89f55-bd78-4dfe-a303-65f8d4843d05&mode=research&activeHistorySidebarCategory=all)**

## 研究問題

研究檢查債券市場某個 spread 的大幅變化，是否與之後 S&P 500 回報存在可辨識的統計模式。

方法不是把當前 spread 水平直接視為可行動訊號，而是先放回歷史分布，再問：**過去 spread 處於相近水平時，股票在之後 20 個交易日表現如何？**

## Scatter plot 設計

- 樣本：**1,244 個每日觀察**
- 期間：**2021 年 9 月至 2026 年 8 月**
- X 軸：目標 spread，由低至高排序
- Y 軸：**之後 20 個交易日的 S&P 500 回報**
- 最新 spread：另行標示，以顯示在歷史分布中的位置

這樣可以同時看到當前讀數在歷史上所處的位置，以及相近 spread 水平下後續股票結果的分散程度。

## 研究結果

- 最新 spread：截至 2026-09-01 為 **+7.72**
- 五年內，spread 與未來 20 個交易日 S&P 500 回報的 correlation：**-0.22**
- 較高 spread 平均而言稍偏向較低後續回報，但相似 X 值下的股票結果分散非常大

因此，來源把這段關係描述為**弱**。它沒有把 -0.22 的輕微負 correlation 誇大成強預測關係。

這正是本案例的重點：把假設量化，同時保留「這個指標可能沒有很高實用價值」的可能性。

## 如何理解最新值標記

最新 spread 的標記放在 Y=0，只是圖上的視覺參考，用來顯示當前 X 值的位置。

它**不是**對尚未觀察到的未來 20 日股票回報作 0% 預測。

## 分析限制

- 20 個交易日 forward windows 互相重疊；
- -0.22 correlation 把複雜關係壓縮成單一線性統計；
- 樣本可能受到特定市場 regime 主導；
- 改變 spread 定義、horizon 或 sample period，都可能令結果明顯不同。

實務上的研究教訓，是把跨資產經驗法則放進真實時間序列檢查，並保留弱或無效的結果，而不是強行製造更有力的敘事。

## 本使用案例說明了甚麼

這項研究展示如何把跨資產直覺轉成可量度測試，把當前觀察放回歷史背景，再判斷表面關係是否足夠穩健，值得進一步研究。


---

[← 多資產使用案例](README.md) · [按資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)
