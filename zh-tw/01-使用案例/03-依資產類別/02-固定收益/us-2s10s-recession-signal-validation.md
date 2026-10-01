<!--
id: RX-USECASE-0031
type: use-case
language: zh
locale: zh-TW
author: Reflexivity Research
published: 2026-09-15
status: published
translation_status: current
original_language: en
source_text_status: canonicalized_from_platform_research_with_reviewed_editorial_clarification
asset_class: Fixed Income (US Rates), Macro
roles: Fixed Income PM, Macro Strategist, Asset Allocator
publication_mode: faithful-source-preserving
-->

# 檢驗美國 2s10s 殖利率曲線是否曾預測衰退

<!-- locale-switcher:start -->
**Languages:** [English](../../../../en/02-use-cases/03-asset-class/02-fixed-income/us-2s10s-recession-signal-validation.md) · [日本語](../../../../ja/02-ユースケース/03-運用資産別/02-債券/us-2s10s-recession-signal-validation.md) · [한국어](../../../../ko/01-유스케이스/03-운용자산별/02-채권/us-2s10s-recession-signal-validation.md) · [简体中文](../../../../zh-cn/01-使用案例/03-按资产类别/02-固定收益/us-2s10s-recession-signal-validation.md) · **繁體中文（台灣）** · [繁體中文（香港）](../../../../zh-hk/01-使用案例/03-按資產類別/02-固定收益/us-2s10s-recession-signal-validation.md)
<!-- locale-switcher:end -->

[← 固定收益使用案例](README.md) · [依資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)

**作者：** Reflexivity Research  
**主要資產：** 固定收益（美國利率）、總體  
**適用使用者：** 固定收益 PM、總體策略師、資產配置者  
**分析類型：** 假設檢驗、時間序列分析

> 本頁保留一份有明確日期的 Reflexivity 研究輸出及其限制。來源中的一項統計數字看起來需要重新驗證，因此下列結果不應視為已獨立確認的歷史事實。

**[在 Reflexivity 中開啟這個研究範例 →](https://app.reflexivity.com/app/alfred?conversationId=5c412f9a-ea78-4c81-8911-f0419ddeefd8&mode=research&activeHistorySidebarCategory=all)**

## 研究問題

**美國 2 年期 / 10 年期公債利差倒掛，歷史上是否能預測 9 到 12 個月後的衰退？**

原始研究檢視 1976–2025 年資料，並在不同領先期間測試這個常見的殖利率曲線規則。更廣泛的目的，是把市場上常被重複引用的經驗法則放進明確的數據檢驗中，包括誤報與漏掉的衰退。

> **資料品質提醒：** 原資料中有些數字的建構方式與定義應重新確認。尤其是「自 1976 年以來，曲線有 **83.5% 的時間處於倒掛**」這項陳述非常不尋常，需要再驗證。本頁忠實記錄研究輸出，但**不把這個統計當成已驗證的一般事實**。

## 不同領先期間的結果

| 指標 | 9 個月 | 10 個月 | 11 個月 | 12 個月 |
|---|---:|---:|---:|---:|
| Sensitivity | 56.9% | 55.2% | 50.0% | 44.8% |
| Precision | 6.8% | 6.6% | 6.0% | 5.4% |
| False-positive rate | 86.5% | 86.7% | 87.3% | 87.9% |
| Accuracy | 17.9% | 17.5% | 16.5% | 15.4% |

原資料特別指出 10 個月窗口，其中 precision 為 **6.6%**、false-positive rate 為 **86.7%**。依來源定義，如果把「曲線倒掛」直接當成可交易的衰退訊號，會產生大量誤報。

## 逐次衰退檢視

| 衰退 | 期間 | 前 9–12 個月是否倒掛？ | 原資料平均利差 |
|---|---|---|---:|
| 1980-02 至 1980-08 | 6 個月 | 否 | 0.60% |
| 1981-08 至 1982-12 | 16 個月 | 是 | 0.53% |
| 1990-08 至 1991-04 | 8 個月 | 是 | 0.04% |
| 2001-04 至 2001-12 | 8 個月 | 否 | 0.36% |
| 2008-01 至 2009-07 | 18 個月 | 是 | 0.03% |
| 2020-03 至 2020-05 | 2 個月 | 是 | -0.21% |

## 主要重點

1. **原資料所報告的 precision 很低**，代表在測試設定下，衰退警報遠多於實際發生的衰退。
2. 原資料把 6 次衰退中的 4 次歸類為有捕捉到，漏掉 1980 與 2001 年兩次。
3. QE、全球對美國公債的需求，以及市場結構改變，可能讓不同時期的關係產生變化。
4. 原資料建議不要單獨使用一條利差，而應把 2s10s 與其他曲線定義、失業率、信用利差與領先指標一起比較。

## 後續測試

- 與失業率變化、信用利差、領先經濟指標比較預測能力；
- 測試 3m10y、1y10y 等其他曲線定義；
- 依重大結構轉折拆分樣本，例如全球金融危機前後與 QE 導入後。

## 如何解讀結果

真正有用的教訓不是「倒掛曲線是對的」或「倒掛曲線是錯的」，而是把市場上常被視為常識的規則，**強迫放進明確定義、不同領先期、誤報計算與 regime 檢查中**。

由於原資料本身至少包含一項看起來可疑的統計數字，在依賴其所報告的績效之前，下一步應該先重現資料建構方式，並驗證衰退標記與倒掛定義。

## 本使用案例說明了什麼

這個例子同時展示自動化假設檢驗的價值與限制：Reflexivity 可以組織歷史測試並揭露誤報，但分析師仍必須對異常統計提出質疑，並在把輸出視為既定證據之前驗證資料定義。


---

[← 固定收益使用案例](README.md) · [依資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)
