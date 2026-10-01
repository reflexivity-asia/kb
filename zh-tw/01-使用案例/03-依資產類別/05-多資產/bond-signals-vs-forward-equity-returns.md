<!--
id: RX-USECASE-0033
type: use-case
language: zh
locale: zh-TW
author: Reflexivity Research
published: 2026-09-15
status: published
translation_status: current
original_language: en
source_text_status: canonicalized_from_reviewed_ja_rendering
publication_mode: faithful-source-preserving
-->

# 檢驗債券市場訊號是否與未來股票報酬相關

<!-- locale-switcher:start -->
**Languages:** [English](../../../../en/01-use-cases/03-asset-class/05-multi-asset/bond-signals-vs-forward-equity-returns.md) · [日本語](../../../../ja/01-ユースケース/03-運用資産別/05-マルチアセット/bond-signals-vs-forward-equity-returns.md) · [한국어](../../../../ko/01-유스케이스/03-운용자산별/05-멀티에셋/bond-signals-vs-forward-equity-returns.md) · [简体中文](../../../../zh-cn/01-使用案例/03-按资产类别/05-多资产/bond-signals-vs-forward-equity-returns.md) · **繁體中文（台灣）** · [繁體中文（香港）](../../../../zh-hk/01-使用案例/03-按資產類別/05-多資產/bond-signals-vs-forward-equity-returns.md)
<!-- locale-switcher:end -->

[← 多資產使用案例](README.md) · [依資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)

**作者：** Reflexivity Research  
**主要資產類別：** 固定收益、股票、跨資產  
**適用使用者：** Multi-asset PM、quant、資產配置人員  
**分析類型：** 跨資產分析、時間序列分析、假設檢驗

> 本頁保留實際 Reflexivity 研究輸出的推理結構，而不是只留下結論。數字與市場觀察均對應原始研究日期。

**[在 Reflexivity 中開啟這個研究範例 →](https://app.reflexivity.com/app/alfred?conversationId=1ae89f55-bd78-4dfe-a303-65f8d4843d05&mode=research&activeHistorySidebarCategory=all)**

## 研究檢驗了什麼

問題是：債券市場某個 spread 的大幅變動，是否與後續 S&P 500 報酬存在可辨識的模式。

研究並未把目前 spread 水準直接當成交易訊號，而是先把最新觀察放進歷史分布，再問：**過去 spread 位於相近水準時，股票在接下來 20 個交易日表現如何？**

## Scatter plot 如何建立

- 樣本：**1,244 個每日觀察值**
- 期間：**2021 年 9 月至 2026 年 8 月**
- X 軸：目標 spread，由低到高排列
- Y 軸：**其後 20 個交易日的 S&P 500 報酬**
- 最新 spread：另外標示，以顯示其在歷史分布中的位置

這種設計可以同時看見兩件事：今天的讀值在歷史上位於哪裡，以及相近 spread 水準之後的股票結果有多分散。

## 原始研究發現

- 最新 spread：截至 2026-09-01 為 **+7.72**
- 五年期間，該 spread 與其後 20 個交易日 S&P 500 報酬的相關係數：**-0.22**
- spread 較高時，之後平均報酬略偏低，但相近 X 值所對應的未來股票結果分散度非常大

因此，研究把這個關係描述為**偏弱**，而沒有把小幅負相關包裝成較強的預測訊號。

這正是本使用案例的核心：量化假設，也保留「這個訊號可能沒有太大實用價值」的可能性。

## 如何閱讀最新值標記

最新 spread 的標記放在 Y=0，只是視覺上的參考，用來顯示目前 X 值位於哪裡。

它**不是**尚未觀察到的未來 20 個交易日股票報酬預測。

## 分析限制

- 20 個交易日的 forward window 彼此重疊。
- -0.22 的相關係數把複雜關係壓縮成一個線性統計值。
- 樣本可能受到特定市場 regime 主導。
- 若 spread 定義、預測期間或樣本期間改變，結果可能大幅不同。

實務上的重點是：用真實 time series 檢驗跨資產經驗法則，並保留弱結果或負結果，而不是勉強建立有吸引力的敘事。

## 本使用案例說明了什麼

這項研究展示如何把跨資產直覺轉成可衡量的檢驗、把最新觀察放入歷史背景，並判斷表面關係是否強到值得進一步使用。


---

[← 多資產使用案例](README.md) · [依資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)
