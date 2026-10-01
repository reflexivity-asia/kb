<!--
id: RX-USECASE-0030
type: use-case
language: zh
locale: zh-CN
author: Reflexivity Research
published: 2026-09-15
status: published
translation_status: current
original_language: en
source_text_status: localized_from_en_canonical
asset_class: Fixed Income (US Rates)
roles: Fixed Income PM, Rates Investor, Relative-Value Investor
publication_mode: faithful-source-preserving
-->

# 筛选美国收益率曲线中的陡峭化与平坦化候选

<!-- locale-switcher:start -->
**Languages:** [English](../../../../en/02-use-cases/03-asset-class/02-fixed-income/us-yield-curve-relative-value-screen.md) · [日本語](../../../../ja/02-ユースケース/03-運用資産別/02-債券/us-yield-curve-relative-value-screen.md) · [한국어](../../../../ko/01-유스케이스/03-운용자산별/02-채권/us-yield-curve-relative-value-screen.md) · **简体中文** · [繁體中文（台灣）](../../../../zh-tw/01-使用案例/03-依資產類別/02-固定收益/us-yield-curve-relative-value-screen.md) · [繁體中文（香港）](../../../../zh-hk/01-使用案例/03-按資產類別/02-固定收益/us-yield-curve-relative-value-screen.md)
<!-- locale-switcher:end -->

[← 固定收益使用案例](README.md) · [按资产类别浏览](../README.md) · [全部使用案例](../../README.md)

**作者：** Reflexivity Research  
**主要资产：** 固定收益（美国利率）  
**适用用户：** 固定收益 PM、利率投资者、相对价值投资者  
**分析类型：** 收益率曲线、相对价值、筛选

> 这份来源是一次纠错后的 follow-up，并不是完整的原始研究包。本页只保留实际提供的修正筛选表和决策逻辑，不重构缺失的早期输出。

**[在 Reflexivity 中打开这个研究示例 →](https://app.reflexivity.com/app/alfred?conversationId=7a3cccb2-8503-4530-b85b-34386f208480&mode=research&activeHistorySidebarCategory=all)**

## 修正内容

早期输出中，部分显示的交易标签与底层经济逻辑不一致。这份 follow-up 修正了该问题。

关键教训是：不能只根据历史分位来给曲线区段分类。某个利差相对历史看起来很平或倒挂，但如果 **carry 和 rolldown 对持仓不利**，表面上有吸引力的交易也可能并不值得做。

## 修正后的筛选表

| 区段 | 曲线利差 | 年化利差 | 历史分位 | Rolldown | 修正后判断 |
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

## 为什么 3y-2y 和 4y-3y 是中性

原先错误来自只看较低的历史分位，把它们标为陡峭化候选，却没有反映 rolldown 的抵消作用。

修正后的逻辑中：

- **3y-2y** 处于 9.6% 分位，但 rolldown 为 23.6 bp
- **4y-3y** 处于 15.2% 分位，但 rolldown 为 8.8 bp

估值信号与 carry/rolldown 信号相互冲突，因此两组都被重新归类为中性。

## 修正后的分布

- **Steepener / pay：** 3 组 — 5y-4y、25y-20y、30y-25y
- **Flattener / receive：** 1 组 — 12y-8y
- **中性：** 5 组 — 3y-2y、4y-3y、7y-5y、8y-7y、20y-12y

## 如何读取这个筛选器

这个案例的价值不在于单个交易标签，而在于：在判断某段曲线是否真的有吸引力之前，把**历史相对价值与 carry、rolldown 一起看**。

较低的历史分位乍看会让陡峭化交易显得很有吸引力。但如果持有过程中需要承受足够不利的 rolldown，更合理的结论可能是中性。因此，这个筛选器是后续构建交易的起点，而不是自动信号生成器。

## 本使用案例说明了什么

这次修正之所以有价值，是因为它展示了一套能够在显示逻辑与经济逻辑不一致时主动修正结果的研究过程。可复用的模式是：**历史位置 → carry/rolldown → 综合交易分类 → 当各组成部分不支持 headline 信号时进行修正**。


---

[← 固定收益使用案例](README.md) · [按资产类别浏览](../README.md) · [全部使用案例](../../README.md)
