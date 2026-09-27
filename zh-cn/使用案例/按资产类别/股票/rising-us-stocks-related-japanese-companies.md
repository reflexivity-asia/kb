<!--
id: RX-USECASE-0065
type: use-case
language: zh
locale: zh-CN
provider: QUICK Inc.
provided: 2026-09-18
status: published
translation_status: current
original_language: en
source_text_status: localized_from_en_canonical
source_type: partner-provided-use-case
asset_class: Equities
publication_mode: faithful-source-preserving
-->

# 从上涨的美国股票中寻找相关日本公司

<!-- locale-switcher:start -->
**Languages:** [English](../../../../en/usecases/byasset/equities/rising-us-stocks-related-japanese-companies.md) · [日本語](../../../../ja/ユースケース/運用資産別/株式/rising-us-stocks-related-japanese-companies.md) · [한국어](../../../../ko/유스케이스/운용자산별/주식/rising-us-stocks-related-japanese-companies.md) · **简体中文** · [繁體中文（台灣）](../../../../zh-tw/使用案例/依資產類別/股票/rising-us-stocks-related-japanese-companies.md) · [繁體中文（香港）](../../../../zh-hk/使用案例/按資產類別/股票/rising-us-stocks-related-japanese-companies.md)
<!-- locale-switcher:end -->

[← 股票使用案例](README.md) · [按资产类别浏览](../README.md) · [全部使用案例](../../README.md)

**提供日期：** 2026-09-18  
**主要资产：** 股票

> 本案例中的数据和市场环境反映提供日期当时的情况。

> ### [在 Reflexivity 中打开这个研究示例 →](https://app.reflexivity.com/alfred?mode=research&conversationId=8d4011b7-597b-4361-ad87-501046a67b28&scrollTo=top)

## 问题

**从 9 月初到昨天，找出上涨的美国行业和主要股票，并列出与这些公司相关的日本企业。**

## 先缩小美国市场领涨股范围

分析先找出 2026 年 9 月 1 日至 9 月 17 日美国市场上涨的股票，再以这些领涨股为起点追踪与日本供应链的联系。

半导体是主要强势来源，Intel、AMD 和 Qualcomm 领涨。Meta 在 AI/平台方向上涨，Oracle 在 AI/云方向上涨。同期 Nvidia 基本持平，说明即使在半导体板块内部，表现也存在明显差异。

![所选美国股票的表现](../../../图片/使用案例/quick/RX-USECASE-0065/01-us-stock-performance.webp)

| 公司 | 主题 / 行业 | 收益率 | 价格，9 月 1 日 → 9 月 17 日 |
| --- | --- | ---: | --- |
| Intel | 半导体 | +22.3% | $88.97 → $108.80 |
| AMD | 半导体 | +18.6% | $459.61 → $545.09 |
| Meta | AI / 平台 | +17.9% | $578.54 → $682.31 |
| Qualcomm | 半导体 | +13.3% | $166.61 → $188.71 |
| Oracle | AI / 云 | +6.6% | $141.32 → $150.59 |
| Micron | 存储半导体 | +4.7% | $933.44 → $977.50 |
| TSMC | 晶圆代工 | +3.9% | $414.00 → $430.26 |

## 如何把这些走势连接到日本

下一步把上涨的美国公司拆分为**半导体制造设备、材料和基板、存储、晶圆代工敞口、AI 芯片后端处理**等供应链类别。

### 半导体制造设备

美国一侧的需求驱动包括 Intel、AMD、Nvidia、TSMC 等半导体公司的资本开支。原资料识别出的日本公司包括：

- Tokyo Electron (8035)
- Lasertec (6920)
- Disco (6146)
- Advantest (6857)
- Kokusai Electric (6525)
- Towa (6315)
- Tokyo Seimitsu (7729)
- SCREEN Holdings (7735)

### 半导体材料与基板

- SUMCO (3436)
- Tokyo Ohka Kogyo (4186)
- Shin-Etsu Chemical (4063)
- Ibiden (4062)
- Fujimi Incorporated (5384)
- Taiyo Holdings (4626)
- C. Uyemura (4966)
- HOYA (7741)

### 存储与后端处理

原资料还把 Kioxia、Kokusai Electric、Towa、Advantest、Disco 和 Lasertec 与存储行业敞口及 AI 芯片后端或检测需求联系起来。

## 为什么这个工作流有用

重点不是从一份静态的日本半导体股票清单开始，而是按以下顺序推进：

**识别当前价格强势的美国股票 → 分类上涨背后的行业/主题 → 利用知识图谱扩展到相关日本公司。**

这样可以把一般的行业筛选转化为一条从已经出现显著市场走势的公司出发的研究路径。

## 局限

- 与日本公司的关系反映知识图谱中的一般供应链和主题联系。
- 分析没有核实各日本公司的具体订单金额或收入影响。
- 观察窗口约两周，时间较短，而且同一行业内的股票表现差异很大。
- 价格和收益率基于所提供 Reflexivity 分析中的每日收盘价。

后续可以继续追踪 Intel、AMD 或 Qualcomm 等具体美国公司的竞争对手和供应商。

---




本内容由 QUICK 提供。

根据国家或地区、语言环境、所用产品、权限及数据覆盖范围，可能无法完全按本文方式复现该案例。

[← 股票使用案例](README.md) · [按资产类别浏览](../README.md) · [全部使用案例](../../README.md)
