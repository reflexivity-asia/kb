<!--
id: RX-USECASE-0065
type: use-case
language: zh
locale: zh-HK
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

# 從上漲的美國股票尋找相關日本公司

<!-- locale-switcher:start -->
**Languages:** [English](../../../../en/use-cases/asset-class/equities/rising-us-stocks-related-japanese-companies.md) · [日本語](../../../../ja/ユースケース/運用資産別/株式/rising-us-stocks-related-japanese-companies.md) · [한국어](../../../../ko/유스케이스/운용자산별/주식/rising-us-stocks-related-japanese-companies.md) · [简体中文](../../../../zh-cn/使用案例/按资产类别/股票/rising-us-stocks-related-japanese-companies.md) · [繁體中文（台灣）](../../../../zh-tw/使用案例/依資產類別/股票/rising-us-stocks-related-japanese-companies.md) · **繁體中文（香港）**
<!-- locale-switcher:end -->

[← 股票使用案例](README.md) · [按資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)

**提供日期：** 2026-09-18  
**主要資產：** 股票

> 本案例中的數據及市場環境反映提供日期當時的情況。

> ### [在 Reflexivity 開啟這個研究範例 →](https://app.reflexivity.com/alfred?mode=research&conversationId=8d4011b7-597b-4361-ad87-501046a67b28&scrollTo=top)

## 問題

**從 9 月初到昨天，找出上漲的美國行業與主要股票，並列出與這些公司相關的日本企業。**

## 先縮小美國市場領漲股範圍

分析先找出 2026 年 9 月 1 日至 9 月 17 日美國市場上漲的股票，再以這些領漲股為起點追蹤與日本供應鏈的關聯。

半導體是主要強勢來源，Intel、AMD 與 Qualcomm 領漲。Meta 在 AI／平台方向上漲，Oracle 在 AI／雲端方向上漲。同期 Nvidia 大致持平，顯示即使在半導體行業內部，表現也有明顯差異。

![所選美國股票的表現](../../../../assets/usecases/quick/RX-USECASE-0065/01-us-stock-performance.webp)

| 公司 | 主題 / 行業 | 回報率 | 價格，9 月 1 日 → 9 月 17 日 |
| --- | --- | ---: | --- |
| Intel | 半導體 | +22.3% | $88.97 → $108.80 |
| AMD | 半導體 | +18.6% | $459.61 → $545.09 |
| Meta | AI / 平台 | +17.9% | $578.54 → $682.31 |
| Qualcomm | 半導體 | +13.3% | $166.61 → $188.71 |
| Oracle | AI / 雲端 | +6.6% | $141.32 → $150.59 |
| Micron | 記憶體半導體 | +4.7% | $933.44 → $977.50 |
| TSMC | 晶圓代工 | +3.9% | $414.00 → $430.26 |

## 如何把這些走勢連結到日本

下一步把上漲的美國公司拆分為**半導體製造設備、材料與基板、記憶體、晶圓代工敞口、AI 晶片後端處理**等供應鏈類別。

### 半導體製造設備

美國一側的需求驅動因素包括 Intel、AMD、Nvidia、TSMC 等半導體公司的資本支出。原始資料列出的日本公司包括：

- Tokyo Electron (8035)
- Lasertec (6920)
- Disco (6146)
- Advantest (6857)
- Kokusai Electric (6525)
- Towa (6315)
- Tokyo Seimitsu (7729)
- SCREEN Holdings (7735)

### 半導體材料與基板

- SUMCO (3436)
- Tokyo Ohka Kogyo (4186)
- Shin-Etsu Chemical (4063)
- Ibiden (4062)
- Fujimi Incorporated (5384)
- Taiyo Holdings (4626)
- C. Uyemura (4966)
- HOYA (7741)

### 記憶體與後端處理

原始資料也把 Kioxia、Kokusai Electric、Towa、Advantest、Disco 與 Lasertec，和記憶體景氣以及 AI 晶片後端處理或檢測需求連結起來。

## 為甚麼這個工作流程有用

重點不是從一份靜態的日本半導體股票清單開始，而是依下列順序推進：

**辨識目前價格強勢的美國股票 → 分類上漲背後的行業／主題 → 利用知識圖譜擴展到相關日本公司。**

這樣可以把一般的行業篩選，轉化為一條從已經出現顯著市場走勢的公司出發的研究路徑。

## 限制

- 與日本公司的關係反映知識圖譜中的一般供應鏈與主題連結。
- 分析沒有核實各日本公司的具體訂單金額或收入影響。
- 觀察區間約兩週，時間較短，而且同一行業內的股票表現差異很大。
- 價格與回報率依據所提供 Reflexivity 分析中的每日收盤價。

下一步可以進一步追蹤 Intel、AMD 或 Qualcomm 等特定美國公司的競爭對手與供應商。

---




本內容由 QUICK 提供。

視乎國家或地區、語言環境、使用產品、權限及數據涵蓋範圍，未必可以完全按本文方式重現本案例。

[← 股票使用案例](README.md) · [按資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)
