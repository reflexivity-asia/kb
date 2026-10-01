<!--
id: RX-USECASE-0031
type: use-case
language: zh
locale: zh-CN
author: Reflexivity Research
published: 2026-09-15
status: published
translation_status: current
original_language: en
source_text_status: localized_from_en_canonical
asset_class: Fixed Income (US Rates), Macro
roles: Fixed Income PM, Macro Strategist, Asset Allocator
publication_mode: faithful-source-preserving
-->

# 检验美国 2s10s 曲线历史上是否预示经济衰退

<!-- locale-switcher:start -->
**Languages:** [English](../../../../en/02-use-cases/03-asset-class/02-fixed-income/us-2s10s-recession-signal-validation.md) · [日本語](../../../../ja/02-ユースケース/03-運用資産別/02-債券/us-2s10s-recession-signal-validation.md) · [한국어](../../../../ko/01-유스케이스/03-운용자산별/02-채권/us-2s10s-recession-signal-validation.md) · **简体中文** · [繁體中文（台灣）](../../../../zh-tw/01-使用案例/03-依資產類別/02-固定收益/us-2s10s-recession-signal-validation.md) · [繁體中文（香港）](../../../../zh-hk/01-使用案例/03-按資產類別/02-固定收益/us-2s10s-recession-signal-validation.md)
<!-- locale-switcher:end -->

[← 固定收益使用案例](README.md) · [按资产类别浏览](../README.md) · [全部使用案例](../../README.md)

**作者：** Reflexivity Research  
**主要资产：** 固定收益（美国利率）、宏观  
**适用用户：** 固定收益 PM、宏观策略师、资产配置者  
**分析类型：** 假设检验、时间序列分析

> 本页保留一份带明确日期的 Reflexivity 研究输出及其局限。原研究中有一项统计值看起来需要重新验证，因此以下结果不应被视为已经独立核实的历史事实。

**[在 Reflexivity 中打开这个研究示例 →](https://app.reflexivity.com/app/alfred?conversationId=5c412f9a-ea78-4c81-8911-f0419ddeefd8&mode=research&activeHistorySidebarCategory=all)**

## 研究问题

**美国 2 年期 / 10 年期国债利差倒挂，历史上是否能提前 9–12 个月预示经济衰退？**

原研究考察 1976–2025 年，并在多个领先窗口下测试这一常见的收益率曲线经验法则。更广泛的目的，是把常被重复引用的市场经验放进明确的数据测试中，同时计入误报和漏掉的衰退。

> **数据质量提示：** 原研究包含一些需要重新检查构造方式和定义的数值。尤其是“自 1976 年以来曲线有 **83.5% 的时间处于倒挂状态**”这一说法看起来异常，需要重新验证。本页忠实记录原研究输出，并不把这一数字作为已验证的一般事实。

## 按领先窗口得到的结果

| 指标 | 9 个月 | 10 个月 | 11 个月 | 12 个月 |
|---|---:|---:|---:|---:|
| Sensitivity | 56.9% | 55.2% | 50.0% | 44.8% |
| Precision | 6.8% | 6.6% | 6.0% | 5.4% |
| False-positive rate | 86.5% | 86.7% | 87.3% | 87.9% |
| Accuracy | 17.9% | 17.5% | 16.5% | 15.4% |

原研究重点指出 10 个月窗口，其中 precision 为 **6.6%**，false-positive rate 为 **86.7%**。按照原研究的定义，如果把“曲线倒挂”直接当成可执行的衰退信号，会产生大量误报。

## 历次衰退回顾

| 衰退 | 区间 | 提前 9–12 个月倒挂？ | 原研究平均利差 |
|---|---|---|---:|
| 1980-02 至 1980-08 | 6 个月 | 否 | 0.60% |
| 1981-08 至 1982-12 | 16 个月 | 是 | 0.53% |
| 1990-08 至 1991-04 | 8 个月 | 是 | 0.04% |
| 2001-04 至 2001-12 | 8 个月 | 否 | 0.36% |
| 2008-01 至 2009-07 | 18 个月 | 是 | 0.03% |
| 2020-03 至 2020-05 | 2 个月 | 是 | -0.21% |

## 主要结论

1. **报告的 precision 很低**，意味着在这套测试设置下，衰退警报远多于实际发生的衰退。
2. 原研究将六次衰退中的四次归类为被捕捉到，漏掉 1980 年和 2001 年两次。
3. 原研究指出 QE、全球对美国国债的需求以及市场结构变化，可能使不同市场阶段中的关系发生变化。
4. 建议把 2s10s 与其他曲线定义，以及失业率、信用利差和领先指标一起比较，而不是孤立使用单一利差。

## 后续测试

- 与失业率变化、信用利差和领先经济指标比较预测表现
- 测试 3m10y、1y10y 等其他收益率曲线定义
- 围绕重大结构变化拆分样本，包括全球金融危机前后 QE 的引入

## 如何解读结果

有用的结论并不是“倒挂曲线是对的”或“倒挂曲线是错的”。更重要的是，把一个常被当成市场常识重复引用的规则，**强制放进明确的定义、领先窗口、误报统计和市场阶段检验中**。

由于原研究本身至少有一项统计值看起来可疑，在依赖这些表现数字之前，下一步应重新复现数据构造，并验证衰退标签和倒挂定义。

## 本使用案例说明了什么

这个案例同时展示了自动化假设检验的价值和边界：Reflexivity 可以结构化历史测试并暴露误报，但分析者仍需要质疑异常统计，并在把输出当作既定证据之前验证数据定义。


---

[← 固定收益使用案例](README.md) · [按资产类别浏览](../README.md) · [全部使用案例](../../README.md)
