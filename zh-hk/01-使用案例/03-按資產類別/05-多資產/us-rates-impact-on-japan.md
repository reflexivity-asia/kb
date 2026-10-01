<!--
id: RX-USECASE-0054
type: use-case
language: zh
locale: zh-HK
provider: QUICK Corporation
provided: 2026-08-20
status: published
translation_status: current
source_type: partner-provided-use-case
asset_class: fixed income, equities, FX, macro, multi-asset
publication_mode: faithful-source-preserving
-->

# 追蹤美國長期利率上升如何傳導到日本市場

<!-- locale-switcher:start -->
**Languages:** [English](../../../../en/02-use-cases/03-asset-class/05-multi-asset/us-rates-impact-on-japan.md) · [日本語](../../../../ja/02-ユースケース/03-運用資産別/05-マルチアセット/us-rates-impact-on-japan.md) · [한국어](../../../../ko/01-유스케이스/03-운용자산별/05-멀티에셋/us-rates-impact-on-japan.md) · [简体中文](../../../../zh-cn/01-使用案例/03-按资产类别/05-多资产/us-rates-impact-on-japan.md) · [繁體中文（台灣）](../../../../zh-tw/01-使用案例/03-依資產類別/05-多資產/us-rates-impact-on-japan.md) · **繁體中文（香港）**
<!-- locale-switcher:end -->

[← 多資產使用案例](README.md) · [按資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)

**提供日期：** 2026-08-20  
**主要資產：** 固定收益、股票、FX、宏觀、多資產

> 本頁保留 QUICK 提供的使用案例。市場水平及解讀均是來源日期快照。

## 問題

美國長期利率正在上升。這會如何影響日本貨幣政策及日本經濟？對銀行、房地產及出口商等主題有甚麼含義？

## 研究要建立甚麼

美國長期利率上升不會機械式傳到日本。

因此研究沿着以下因果鏈：

**美國利率 → 美日孳息差 → FX → BOJ / 日本國內利率 → 日本股票主題**

重點是逐段測試，而不是由「美債孳息較高」直接跳到板塊結論。

## 來源快照

| 指標 | 最新 | 一年前 | 變化 |
|---|---:|---:|---:|
| US 10Y yield | 4.71% | 4.32% | +0.39pp |
| US 30Y yield | 5.29% | 4.92% | +0.37pp |
| Japan 10Y yield | 2.95% | 1.57% | +1.38pp |
| BOJ policy rate | 1.00% | — | tightening cycle |
| Japan core CPI YoY | 1.6% | — | 約 2% |
| USD/JPY | 159.6 | 147.9 | +7.9% 日圓轉弱 |

來源把美國孳息率上升、息差擴闊及日圓偏弱的組合，解讀為可加強 BOJ 正常化及日本孳息率上升的外部壓力。

![美國與日本長期孳息](../../../../assets/usecases/quick/RX-USECASE-0054/01-us-japan-long-yields.webp)

![USD/JPY 與 Nikkei 225](../../../../assets/usecases/quick/RX-USECASE-0054/03-usdjpy-nikkei.webp)

## 為何先看 FX 才看板塊

孳息差重要的一部分，是它對日圓的影響。

較弱日圓可以支持出口商換算盈利，但同時提高進口成本。進口成本又會影響家庭、內需、通脹及 BOJ 的政策取捨。

因此，研究由利率先走到 FX，再討論股票板塊。

## 傳導到政策及經濟

來源分三個渠道：

1. **日圓偏弱與 BOJ 政策** — 息差擴闊及日圓轉弱可以增加進口價格壓力，加強進一步正常化的理據；
2. **日本長期孳息率上升** — 全球 duration 壓力與日本本土正常化可以互相加強；
3. **雙向經濟影響** — 出口及 inbound-sensitive 業務可能受惠於弱日圓，但家庭及內需面對較高進口成本。

![銀行、地產與汽車主題表現](../../../../assets/usecases/quick/RX-USECASE-0054/02-theme-performance.webp)

## 來源快照中的板塊含義

| 主題 | 1 年回報 | 1 個月回報 | 來源中的利率敏感度 |
|---|---:|---:|---|
| 銀行 | +30.3% | +1.9% | 較闊 margin / 較高再投資收益有利 |
| 房地產 | +7.5% | -3.7% | 融資成本及 discount rate 構成逆風 |
| 汽車 / 出口商 | -4.7% | -5.6% | 日圓利好被美國增長及關稅憂慮抵銷 |

銀行可受惠於較高 lending margin 及債券再投資收益，但孳息急升亦可對證券組合造成 mark-to-market 壓力。房地產面對較高融資成本及 discount rate；出口商雖有弱日圓支持，但仍需與終端需求、貿易政策及行業特定因素一起檢查。

## 如何使用結果

不要把整條鏈簡化成「美國利率升對日本好／差」。應依次更新：

- 美國長端孳息率；
- 美日息差；
- USD/JPY；
- BOJ 反應及日本國內孳息率；
- 各板塊特定敏感度。

## 限制

- 來源主題回報使用 Reflexivity equal-weight basket，不是個股回報；
- 宏觀解讀是按當時可見關係建立的 scenario，不是確定性結論；

## 本使用案例說明了甚麼

這是一套可重複跨資產流程，用來追蹤海外利率衝擊如何經過息差、匯率、貨幣政策反應，再傳到本地板塊表現。

---

本內容由 QUICK 提供。

視乎國家或地區、語言環境、使用產品、權限及數據涵蓋範圍，未必可以完全按本文方式重現本案例。

[← 多資產使用案例](README.md) · [按資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)
