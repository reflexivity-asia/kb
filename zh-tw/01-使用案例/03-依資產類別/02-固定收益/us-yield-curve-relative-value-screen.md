<!--
id: RX-USECASE-0030
type: use-case
language: zh
locale: zh-TW
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

# 篩選美國殖利率曲線中的 Steepener 與 Flattener 候選

<!-- locale-switcher:start -->
**Languages:** [English](../../../../en/01-use-cases/03-asset-class/02-fixed-income/us-yield-curve-relative-value-screen.md) · [日本語](../../../../ja/01-ユースケース/03-運用資産別/02-債券/us-yield-curve-relative-value-screen.md) · [한국어](../../../../ko/01-유스케이스/03-운용자산별/02-채권/us-yield-curve-relative-value-screen.md) · [简体中文](../../../../zh-cn/01-使用案例/03-按资产类别/02-固定收益/us-yield-curve-relative-value-screen.md) · **繁體中文（台灣）** · [繁體中文（香港）](../../../../zh-hk/01-使用案例/03-按資產類別/02-固定收益/us-yield-curve-relative-value-screen.md)
<!-- locale-switcher:end -->

[← 固定收益使用案例](README.md) · [依資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)

**作者：** Reflexivity Research  
**主要資產：** 固定收益（美國利率）  
**適用使用者：** 固定收益 PM、利率投資人、相對價值投資人  
**分析類型：** 殖利率曲線、相對價值、篩選

> 這份來源是更正後的追蹤研究，而不是完整的原始研究包。本頁保留實際提供的更正篩選表與決策邏輯，不重建缺失的早期輸出。

**[在 Reflexivity 中開啟這個研究範例 →](https://app.reflexivity.com/app/alfred?conversationId=7a3cccb2-8503-4530-b85b-34386f208480&mode=research&activeHistorySidebarCategory=all)**

## 這份來源更正了什麼

較早的輸出中，部分顯示的交易標籤與底層邏輯不一致。這份追蹤研究修正了該問題。

核心教訓是：不能只靠歷史百分位來分類曲線區段。一段利差即使相對歷史看起來異常平坦或倒掛，**carry 與 rolldown 仍可能讓表面上有吸引力的交易變得不划算**。

## 更正後的篩選表

| 配對 | 曲線利差 | 年化利差 | 歷史百分位 | Rolldown | 更正後觀點 |
|---|---:|---:|---:|---:|---|
| 3y-2y | -9.7 bp | -9.7 bp | 9.6% | 23.6 bp | 中性 |
| 4y-3y | -0.9 bp | -0.9 bp | 15.2% | 8.8 bp | 中性 |
| 5y-4y | 3.3 bp | 3.3 bp | 28.7% | 4.2 bp | Steepener / pay |
| 7y-5y | 11.8 bp | 5.9 bp | 37.4% | 8.5 bp | 中性 |
| 8y-7y | 5.6 bp | 5.6 bp | 39.9% | -6.2 bp | 中性 |
| 12y-8y | 20.0 bp | 5.0 bp | 45.5% | 14.4 bp | Flattener / receive |
| 20y-12y | 20.3 bp | 2.5 bp | 51.9% | 0.2 bp | 中性 |
| 25y-20y | -0.7 bp | -0.1 bp | 21.9% | -21.0 bp | Steepener / pay |
| 30y-25y | -4.7 bp | -0.9 bp | 12.9% | -4.0 bp | Steepener / pay |

## 為什麼 3y-2y 與 4y-3y 是中性

原本的錯誤，是只注意它們偏低的歷史百分位，因此標示為 steepener 候選，卻沒有反映相反方向的 rolldown。

更正後的邏輯中：

- **3y-2y** 位於第 9.6 百分位，但 rolldown 為 23.6 bp
- **4y-3y** 位於第 15.2 百分位，但 rolldown 為 8.8 bp

表面估值訊號與 carry / rolldown 訊號互相抵消，因此兩者都改列中性。

## 更正後分布

- **Steepener / pay：** 3 組 — 5y-4y、25y-20y、30y-25y
- **Flattener / receive：** 1 組 — 12y-8y
- **中性：** 5 組 — 3y-2y、4y-3y、7y-5y、8y-7y、20y-12y

## 如何閱讀這個篩選

這個例子的價值不是個別交易標籤，而是先結合**歷史相對價值與 carry / rolldown**，再決定某個曲線區段是否真的具吸引力。

低百分位乍看之下可能讓 steepener 很有吸引力，但如果持有部位會產生足夠大的不利 rolldown，更合理的結論可能仍是中性。因此，這個篩選是後續交易建構的起點，而不是自動訊號產生器。

## 本使用案例說明了什麼

這份更正本身就是一個有用案例：當畫面標籤與經濟邏輯不一致時，研究流程必須能修正自己的輸出。可重複的模式是：歷史位置 → carry / rolldown → 綜合交易分類 → 當各組成因素不支持 headline 訊號時進行更正。


---

[← 固定收益使用案例](README.md) · [依資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)
