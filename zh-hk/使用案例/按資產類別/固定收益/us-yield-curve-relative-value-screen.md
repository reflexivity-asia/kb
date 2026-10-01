<!--
id: RX-USECASE-0030
type: use-case
language: zh
locale: zh-HK
author: Reflexivity Research
published: 2026-09-15
status: published
translation_status: current
original_language: en
source_text_status: canonicalized_from_platform_research_with_reviewed_editorial_clarification
asset_class: Fixed Income (US Rates)
roles: Fixed Income PM, Rates Investor, Relative-Value Investor
publication_mode: faithful-source-preserving
-->

# 篩選美國孳息曲線的 steepener 與 flattener 候選

<!-- locale-switcher:start -->
**Languages:** [English](../../../../en/use-cases/asset-class/fixed-income/us-yield-curve-relative-value-screen.md) · [日本語](../../../../ja/ユースケース/運用資産別/債券/us-yield-curve-relative-value-screen.md) · [한국어](../../../../ko/유스케이스/운용자산별/채권/us-yield-curve-relative-value-screen.md) · [简体中文](../../../../zh-cn/使用案例/按资产类别/固定收益/us-yield-curve-relative-value-screen.md) · [繁體中文（台灣）](../../../../zh-tw/使用案例/依資產類別/固定收益/us-yield-curve-relative-value-screen.md) · **繁體中文（香港）**
<!-- locale-switcher:end -->

[← 固定收益使用案例](README.md) · [按資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)

**作者：** Reflexivity Research  
**主要資產：** 固定收益（美國利率）  
**適用使用者：** Fixed Income PM、Rates Investor、Relative-Value Investor  
**分析類型：** 孳息曲線、相對價值、screening

> 此來源是一份修正 follow-up，而不是完整原始研究包。本頁只保留實際提供的修正 screening table 及決策邏輯，不重建缺失的較早輸出。

**[在 Reflexivity 中開啟這個研究示例 →](https://app.reflexivity.com/app/alfred?conversationId=7a3cccb2-8503-4530-b85b-34386f208480&mode=research&activeHistorySidebarCategory=all)**

## 這份來源修正了甚麼

較早輸出中，部分顯示的交易標籤與底層邏輯並不一致。這份 follow-up 修正了該問題。

核心教訓是：不能單靠歷史 percentile 判斷一段曲線應歸類為哪種交易。某個 spread 相對歷史可能看起來非常平坦或倒掛，但若 **carry 與 rolldown 對持倉不利**，表面上吸引的交易可能其實不值得做。

## 修正後 screening table

| Pair | Curve spread | Annualized spread | Historical percentile | Rolldown | 修正後觀點 |
|---|---:|---:|---:|---:|---|
| 3y-2y | -9.7 bp | -9.7 bp | 9.6% | 23.6 bp | Neutral |
| 4y-3y | -0.9 bp | -0.9 bp | 15.2% | 8.8 bp | Neutral |
| 5y-4y | 3.3 bp | 3.3 bp | 28.7% | 4.2 bp | Steepener / pay |
| 7y-5y | 11.8 bp | 5.9 bp | 37.4% | 8.5 bp | Neutral |
| 8y-7y | 5.6 bp | 5.6 bp | 39.9% | -6.2 bp | Neutral |
| 12y-8y | 20.0 bp | 5.0 bp | 45.5% | 14.4 bp | Flattener / receive |
| 20y-12y | 20.3 bp | 2.5 bp | 51.9% | 0.2 bp | Neutral |
| 25y-20y | -0.7 bp | -0.1 bp | 21.9% | -21.0 bp | Steepener / pay |
| 30y-25y | -4.7 bp | -0.9 bp | 12.9% | -4.0 bp | Steepener / pay |

## 為甚麼 3y-2y 與 4y-3y 是 Neutral

原先錯誤來自只聚焦它們較低的歷史 percentile，因此把兩者標成 steepener 候選，但沒有充分反映相反方向的 rolldown。

在修正後邏輯中：

- **3y-2y** 位於第 9.6 percentile，但 rolldown 為 23.6 bp；
- **4y-3y** 位於第 15.2 percentile，但 rolldown 為 8.8 bp。

表面 valuation 訊號與 carry／rolldown 訊號互相抵銷，因此兩者都重新分類為 neutral。

## 修正後分布

- **Steepener / pay：** 3 組 — 5y-4y、25y-20y、30y-25y
- **Flattener / receive：** 1 組 — 12y-8y
- **Neutral：** 5 組 — 3y-2y、4y-3y、7y-5y、8y-7y、20y-12y

## 如何閱讀這個 screen

此例的價值不是個別交易標籤本身，而是先結合**歷史相對價值與 carry／rolldown**，再決定某段曲線是否真的具吸引力。

低 percentile 初看可能令 steepener 很吸引；但如果持倉會承受足夠不利的 rolldown，更合理的結論可能是 neutral。因此這個 screen 是深入交易結構分析的起點，而不是自動產生交易訊號的工具。

## 本使用案例說明了甚麼

這份修正本身很有價值，因為它展示當顯示邏輯與經濟含義不一致時，研究流程如何修正自己。可重複使用的模式是：歷史位置 → carry／rolldown → 綜合交易分類 → 若組成因素不支持 headline signal，則修正分類。


---

[← 固定收益使用案例](README.md) · [按資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)
