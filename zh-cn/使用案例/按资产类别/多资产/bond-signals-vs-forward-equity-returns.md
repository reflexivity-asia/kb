<!--
id: RX-USECASE-0033
type: use-case
language: zh
locale: zh-CN
author: Reflexivity Research
published: 2026-09-15
status: published
translation_status: current
original_language: en
source_text_status: canonicalized_from_reviewed_ja_rendering
publication_mode: faithful-source-preserving
-->

# 检验债券市场信号是否与未来股票收益有关

<!-- locale-switcher:start -->
**Languages:** [English](../../../../en/use-cases/asset-class/multi-asset/bond-signals-vs-forward-equity-returns.md) · [日本語](../../../../ja/ユースケース/運用資産別/マルチアセット/bond-signals-vs-forward-equity-returns.md) · [한국어](../../../../ko/유스케이스/운용자산별/멀티에셋/bond-signals-vs-forward-equity-returns.md) · **简体中文** · [繁體中文（台灣）](../../../../zh-tw/使用案例/依資產類別/多資產/bond-signals-vs-forward-equity-returns.md) · [繁體中文（香港）](../../../../zh-hk/使用案例/按資產類別/多資產/bond-signals-vs-forward-equity-returns.md)
<!-- locale-switcher:end -->

[← 多资产使用案例](README.md) · [按资产类别浏览](../README.md) · [全部使用案例](../../README.md)

**作者：** Reflexivity Research  
**主要资产类别：** 固定收益、股票、跨资产  
**适用用户：** 多资产 PM、量化研究员、资产配置者  
**分析类型：** 跨资产分析、时间序列分析、假设检验

> 本页保留一份真实 Reflexivity Research 输出的研究逻辑，而不是只保留结论。数字和市场观察均对应原研究时点。

**[在 Reflexivity 中打开这个研究示例 →](https://app.reflexivity.com/app/alfred?conversationId=1ae89f55-bd78-4dfe-a303-65f8d4843d05&mode=research&activeHistorySidebarCategory=all)**

## 研究检验了什么

问题是：某个债券市场利差出现较大变动时，之后的 S&P 500 收益是否会呈现可识别的模式。

研究并没有把当前利差水平本身直接当作交易信号，而是把当前观察放入历史分布中，并追问：**过去利差处于类似水平时，之后 20 个交易日股票市场表现如何？**

## 散点图如何构建

- 样本：**1,244 个日度观察值**
- 期间：**2021 年 9 月至 2026 年 8 月**
- X 轴：目标利差，从低到高排列
- Y 轴：**随后 20 个交易日的 S&P 500 收益**
- 最新利差：单独标记，以显示其在历史分布中的位置

这个设置同时让两件事可见：今天的读数在历史上处于哪里，以及类似利差水平附近，之后股票收益的分布到底有多分散。

## 主要发现

- 最新利差：截至 2026-09-01 为 **+7.72**
- 五年内该利差与未来 20 个交易日 S&P 500 收益的相关系数：**-0.22**
- 利差越高时，之后平均股票收益略偏低，但在相似 X 值附近，未来股票收益的离散程度非常大

因此，原研究把这段关系描述为**弱关系**，而没有把一个幅度有限的负相关包装成更强的预测信号。

这正是本使用案例的核心：把假设量化，同时保留“这个信号可能并不好用”的可能性。

## 如何理解最新值标记

最新利差的标记被放在 Y=0，仅仅是为了显示当前 X 值位于历史分布的哪个位置。

它**不是**对未来尚未发生的 20 个交易日股票收益的预测。

## 分析局限

- 20 个交易日的未来窗口彼此重叠。
- -0.22 的相关系数把复杂关系压缩成了一个线性统计量。
- 样本可能受到特定市场环境主导。
- 如果利差定义、预测期限或样本期间改变，结果可能明显不同。

实际意义是：跨资产经验法则应该用真实时间序列检验，而且即使结果很弱甚至是否定性的，也应保留，而不是强行制造一个更有吸引力的叙事。

## 本使用案例说明了什么

这项研究展示了如何把跨资产直觉转化为可测量的检验，把当前观察放进历史语境，并判断表面关系是否足够强，值得进一步使用。


---

[← 多资产使用案例](README.md) · [按资产类别浏览](../README.md) · [全部使用案例](../../README.md)
