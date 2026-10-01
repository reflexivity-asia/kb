<!--
id: RX-USECASE-0050
type: use-case
language: zh
locale: zh-CN
provider: QUICK Corporation
provided: 2026-08-24
status: published
translation_status: current
source_type: partner-provided-use-case
asset_class: equities, crypto, multi-asset
publication_mode: faithful-source-preserving
-->

# 检验 Robinhood 与 Bitcoin 的价格关系

<!-- locale-switcher:start -->
**Languages:** [English](../../../../en/use-cases/asset-class/multi-asset/robinhood-bitcoin-correlation.md) · [日本語](../../../../ja/ユースケース/運用資産別/マルチアセット/robinhood-bitcoin-correlation.md) · [한국어](../../../../ko/유스케이스/운용자산별/멀티에셋/robinhood-bitcoin-correlation.md) · **简体中文** · [繁體中文（台灣）](../../../../zh-tw/使用案例/依資產類別/多資產/robinhood-bitcoin-correlation.md) · [繁體中文（香港）](../../../../zh-hk/使用案例/按資產類別/多資產/robinhood-bitcoin-correlation.md)
<!-- locale-switcher:end -->

[← 多资产使用案例](README.md) · [按资产类别浏览](../README.md) · [全部使用案例](../../README.md)

**提供日期：** 2026-08-24  
**主要资产类别：** 股票、加密资产、多资产

> 本案例数字和市场观察均为原资料时点的历史快照。

## 问题

> 分析 @HOOD 与 Bitcoin 价格之间的相关性。

当公司名称可能混淆时，在 `@` 后使用 ticker 可以让实体识别更准确。

![Robinhood 与 Bitcoin 的价格关系](../../../../assets/usecases/quick/RX-USECASE-0050/source-visuals.webp)

## 研究想确认什么

两张价格图可以在大方向上同时上涨，但这并不意味着它们每天都紧密联动。价格**水平**之间的高相关，也可能只是因为两个资产都共享长期趋势而被放大。

因此，研究分四步进行：

1. 比较过去一年主要高点、低点和剧烈变动日期；
2. 比较价格水平相关性与日收益相关性；
3. 找出 HOOD 与 Bitcoin 出现分化的时期；
4. 分析什么经济机制既能解释相关性，也能解释关系失效的阶段。

这把分析拆成：**视觉共振 → 定量相关 → 例外 → 经济解释**。

## 当时的市场快照：2025 年 8 月至 2026 年 8 月

| 阶段 | 时间 | HOOD | Bitcoin | 方向 |
| --- | --- | --- | --- | --- |
| 起点 | 2025 年 8 月下旬 | ~108 | ~110,000 | — |
| 高点 | 2025 年 10 月初 | ~150 | ~124,800 | 两者都接近高位 |
| 快速下跌 | 2026 年 2 月初 | 72 | ~63,300 | 两者均大幅下跌 |
| 次级低点 | 2026 年 6 月 | ~93 | ~58,500 | 出现部分分化 |
| 最近反弹 | 2026-08-21 | 108 | ~78,400 | 两者均明显反弹 |

QUICK 原资料把这一期间的关系描述为较强正相关。价格水平相关性估计约为 **+0.8**，日收益相关性约在 **+0.5 至 +0.6** 区间。

## 为什么要区分价格水平与收益

高水平相关性可能只是因为两个资产在较长时间内都处于上涨趋势。

日收益相关性问的是更严格的问题：**这两个资产是否真的从一天到下一天一起变动？**

同时使用两种指标，有助于区分共同长期趋势与较短周期的真实共振。

## 分化和相关性同样重要

原资料特别指出 2026 年 6 月：Bitcoin 继续走低，而 HOOD 回升到大约 105–108。

这很重要，因为它说明 HOOD 并不只是 Bitcoin 的简单代理。财报、交易活跃度、业务组合或指引等公司特定因素，在某些时期可能压倒加密资产关系。

## 经济解释

原资料把这种关系连接到两个渠道：

- Robinhood 对加密交易活动有敞口，因此 Bitcoin 市场环境可能影响市场对交易收入和用户活跃度的预期。
- HOOD 与 Bitcoin 都可能表现为高 beta 风险资产，因此同时受到利率、风险偏好等共同宏观变量影响。

这两个渠道都不意味着两者会永久一对一联动。

## 如何使用结果

不要把高相关性当成 HOOD 永远应该作为 Bitcoin proxy 交易的证明。

更有价值的是观察关系什么时候稳定、什么时候失效。后续可以跟踪：

- 加密交易量；
- Robinhood 财报和指引；
- 业务组合变化；
- 利率与更广泛的风险偏好。

## 局限

- 原资料中的相关性估计为近似值。
- 相关性取决于样本和时间期限。
- 共同宏观驱动可以提高相关性，但并不证明直接因果关系。

## 本使用案例说明了什么

这个工作流从表面上的跨资产共振开始，进入基于收益的相关性检验，并主动寻找打破这段关系的时期。

---

本内容由 QUICK 提供。

根据国家或地区、语言环境、所用产品、权限及数据覆盖范围，可能无法完全按本文方式复现该案例。

[← 多资产使用案例](README.md) · [按资产类别浏览](../README.md) · [全部使用案例](../../README.md)
