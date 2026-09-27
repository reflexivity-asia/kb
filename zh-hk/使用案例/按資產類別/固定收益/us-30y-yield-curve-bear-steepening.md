<!--
id: RX-USECASE-0053
type: use-case
language: zh
locale: zh-HK
provider: QUICK Inc.
provided: 2026-08-19
status: published
translation_status: current
source_type: partner-provided-use-case
asset_class: Fixed Income, Macro
roles: Long-only Asset Manager, Hedge Fund Tier 1
publication_mode: faithful-source-preserving
-->

# 從整條孳息曲線解讀美國 30 年期孳息上升

<!-- locale-switcher:start -->
**Languages:** [English](../../../../en/usecases/byasset/fixedincome/us-30y-yield-curve-bear-steepening.md) · [日本語](../../../../ja/ユースケース/運用資産別/債券/us-30y-yield-curve-bear-steepening.md) · [한국어](../../../../ko/유스케이스/운용자산별/채권/us-30y-yield-curve-bear-steepening.md) · [简体中文](../../../../zh-cn/使用案例/按资产类别/固定收益/us-30y-yield-curve-bear-steepening.md) · [繁體中文（台灣）](../../../../zh-tw/使用案例/依資產類別/固定收益/us-30y-yield-curve-bear-steepening.md) · **繁體中文（香港）**
<!-- locale-switcher:end -->

[← 固定收益使用案例](README.md) · [按資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)

**提供日期：** 2026-08-19  
**主要資產：** 固定收益、宏觀  
**適用使用者：** Long-only Asset Manager、對沖基金

> 本案例保留原始問題、分析流程、證據及結論。數字及市場環境均為提供日期當時的快照。

> 美國 30 年期 Treasury 孳息正在上升。整體孳息曲線如何變化？

## 研究目標

30 年期孳息上升本身不能告訴我們，走勢究竟反映預期政策利率改變，還是集中於長端的財政風險、Treasury supply、通脹預期或 term premium。

因此，分析先比較不同 maturity 的孳息變化，辨識**是哪一段曲線正在移動**；之後看曲線形狀，最後再與過往加息及減息 regime 比較，判斷目前走勢是否像傳統政策周期，還是另有原因。

## 初步解讀：長端帶動的沽售

原資料把最近一至三個月窗口的走勢描述為**bear steepening**：長年期孳息升幅遠高於前端。

- 30Y：**5.31%**，一個月 +25 bp
- 20Y：**5.30%**，+23 bp
- 10Y：**4.72%**，+17 bp
- 2Y：**4.19%**，+1 bp
- 3M：**3.87%**，+2 bp

30Y-10Y spread 擴至約 **+0.59 個百分點**；整體曲線仍然向上，包括 10Y-2Y 約 **+0.52 pp**、10Y-3M 約 **+0.85 pp**。

原資料把長端壓力連到財政赤字、債務供應、通脹及 term premium 憂慮，而不是政策控制較強的前端出現同幅度重新定價。

## 各 maturity 變化

| Maturity | 目前孳息 | 1 個月變化 | 3 個月變化 |
|---|---:|---:|---:|
| 30Y | 5.31% | +25 bp | +17 bp |
| 20Y | 5.30% | +23 bp | +16 bp |
| 10Y | 4.72% | +17 bp | +11 bp |
| 7Y | 4.54% | +14 bp | +11 bp |
| 5Y | 4.38% | +10 bp | +11 bp |
| 3Y | 4.25% | +4 bp | +11 bp |
| 2Y | 4.19% | +1 bp | +12 bp |
| 1Y | 4.00% | -1 bp | +19 bp |
| 6M | 3.95% | -1 bp | +18 bp |
| 3M | 3.87% | +2 bp | +19 bp |

原資料以 **2026-08-17** 為參考日，使用 FRED daily constant-maturity Treasury yields。非交易日用上一個交易日數值填補；三個月比較使用約 91 日前最接近的交易日。

![美國國債各年期孳息變化](../../../圖片/使用案例/quick/RX-USECASE-0053/01-maturity-yield-changes.webp)

![目前與三個月前的美國國債孳息曲線](../../../圖片/使用案例/quick/RX-USECASE-0053/02-yield-curve-current-vs-3m.webp)

## 為甚麼之後要與過往政策 regime 比較

確認目前是長端帶動後，下一個問題是：這是否屬於典型加息或減息周期的曲線形態？如果不是，就應把焦點由政策利率擴展到財政、供應、通脹及 term premium。

原資料因此加入第二個問題：**目前曲線行為與過往加息及減息 episode 有何不同？**

## 歷史政策 regime 比較

原資料概括常見模式：

- **加息周期：** 前端孳息跟隨政策利率上升，通常令曲線 flatten，甚至倒掛。
- **減息周期：** 前端孳息快速下降，常見 bull steepening。

原資料認為 2026 年 episode 不同之處，是 effective fed funds rate 約維持在 **3.63%**，但長端孳息上升。

| Regime | 政策方向 | Fed funds 起點 → 終點 | 2s10s 變化 | 30Y 變化 | 原資料曲線標籤 |
|---|---|---|---:|---:|---|
| Current 2026 | Hold | 3.64% → 3.63% | -18 bp | +47 bp | Bear flattening |
| 2024–25 | Cuts | 5.13% → 3.72% | +71 bp | +64 bp | Bear steepening |
| 2022–23 | Hikes | 0.20% → 5.12% | -132 bp | +191 bp | Bear flattening |
| 2019 | Cuts | 2.13% → 0.65% | +30 bp | -109 bp | Bull steepening |
| 2015–18 | Hikes | 0.24% → 2.27% | -103 bp | +11 bp | Bear flattening |
| 2007–08 | Cuts | 4.94% → 0.16% | +110 bp | -214 bp | Bull steepening |
| 2004–06 | Hikes | 1.03% → 4.99% | -212 bp | -29 bp | Bull flattening |

![歷史政策階段的 2s10s 利差與 Fed Funds](../../../圖片/使用案例/quick/RX-USECASE-0053/03-2s10s-fed-funds-history.webp)

## 為甚麼 bear steepening 與 bear flattening 可以同時出現

兩個標籤指的是**不同時間窗口及不同曲線量度方式**。

前半部分比較最近一至三個月整條 maturity spectrum，尤其超長端升幅較強，所以可描述為局部 bear steepening。後半部分則用較長政策 regime 比較 2s10s spread，因此可得到 bear flattening。

所以，同一市場可以在某個局部 segment／短窗口呈現 bear steepener，同時在另一個 horizon 及 curve definition 下呈現 bear flattener。兩者不是同一項量度的矛盾結論。

## 如何閱讀結果

目的不是把 30 年期孳息當作孤立數字，而是依次問：

**哪些 maturity 移動？ → 曲線形狀如何改變？ → 是否符合政策利率 regime？ → 如果不符合，下一步應研究哪些非政策變數？**

當政策利率大致穩定，但長端孳息持續上升，下一步可檢查財政政策、Treasury supply、通脹預期及 term premium。

## 限制

- Treasury yields 為 constant-maturity annualized yields；spread 使用一致的孳息差。
- 變化按 daily close 計算，不包括 intraday move。
- 歷史 regime 邊界是根據 fed-funds data 設定的代表性期間；更改日期會改變結果。
- 原研究引用包括 FEDFUNDS、DGS2、DGS10、DGS30、T10Y2Y、T10Y3M 等 FRED series，以及相關新聞與 catalyst material。

## 本使用案例說明了甚麼

這個使用案例展示如何把單一 maturity 的 headline move 擴展為整條曲線分析、分清不同 measurement windows，並用歷史政策 regime 判斷何時應更重視財政、供應或 term-premium 因素。

---

本內容由 QUICK 提供。

視乎國家或地區、語言環境、使用產品、權限及數據涵蓋範圍，未必可以完全按本文方式重現本案例。

[← 固定收益使用案例](README.md) · [按資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)
