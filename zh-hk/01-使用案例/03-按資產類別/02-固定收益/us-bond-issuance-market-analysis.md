<!--
id: RX-USECASE-0067
type: use-case
language: zh
locale: zh-HK
provider: QUICK Inc.
provided: 2026-09-25
status: published
translation_status: current
original_language: en
source_text_status: localized_from_en_canonical
source_type: partner-provided-use-case
asset_class: Fixed Income, Macro
publication_mode: faithful-source-preserving
-->

# 從發行人、資金用途、供需與孳息分析美國債券發行市場

<!-- locale-switcher:start -->
**Languages:** [English](../../../../en/02-use-cases/03-asset-class/02-fixed-income/us-bond-issuance-market-analysis.md) · [日本語](../../../../ja/02-ユースケース/03-運用資産別/02-債券/us-bond-issuance-market-analysis.md) · [한국어](../../../../ko/01-유스케이스/03-운용자산별/02-채권/us-bond-issuance-market-analysis.md) · [简体中文](../../../../zh-cn/01-使用案例/03-按资产类别/02-固定收益/us-bond-issuance-market-analysis.md) · [繁體中文（台灣）](../../../../zh-tw/01-使用案例/03-依資產類別/02-固定收益/us-bond-issuance-market-analysis.md) · **繁體中文（香港）**
<!-- locale-switcher:end -->

[← 固定收益使用案例](README.md) · [按資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)

**提供日期：** 2026-09-25  
**主要資產：** 固定收益、宏觀

> 本案例中的數據及市場環境反映提供日期當時的情況。

> ### [在 Reflexivity 開啟這個研究範例 →](https://app.reflexivity.com/alfred?mode=research&conversationId=71c1788f-7e54-4620-a6b2-ab163bd6762f&scrollTo=top)

## 問題

**美國債券發行正在增加。請分析主要發行人與資金用途，並同時觀察供需狀況與孳息變化。**

## 先看誰在發行，以及為甚麼發行

原始資料把美國債券發行描述為在國債與公司債兩個市場同步擴大。

主要發行人包括為龐大財政赤字融資的**美國財政部**，以及為 AI 與數據中心投資籌資的大型**投資級企業**。Alphabet 與 Oracle 被列為發行大額債券的科技公司案例。

資金用途可以分成幾類：

- 美國財政部：為財政赤字融資；
- 企業：AI 與數據中心資本支出；
- 在融資成本進一步上升前進行再融資；
- M&A 與 LBO 融資；
- 股份回購等股東回饋。

## 孳息上升，長期尤其明顯

![美國國債孳息與有效聯邦基金利率](../../../../assets/usecases/quick/RX-USECASE-0067/01-us-treasury-fed-funds.webp)

| 指標 | 最新值（2026-09-23） | 一年前 | 變化 |
| --- | ---: | ---: | ---: |
| 美國 2 年期國債孳息 | 4.85% | 3.53% | +1.32 pp |
| 美國 10 年期國債孳息 | 5.11% | 4.12% | +0.99 pp |
| 美國 30 年期國債孳息 | 5.40% | 4.73% | +0.67 pp |
| 有效聯邦基金利率 | 3.63% | 4.33% | -0.70 pp |
| IG 公司債 OAS | 0.77% | 0.75% | +0.02 pp |
| HY 公司債 OAS | 2.73% | 2.71% | +0.02 pp |
| IG 有效孳息 | 5.83% | 4.76% | +1.07 pp |
| HY 有效孳息 | 7.68% | 6.40% | +1.28 pp |

原始資料把短期政策利率下降、長期國債孳息上升的組合，解讀為一種**熊市陡峭化（bear steepening）**。

## 發行量很大，但信用利差仍然很窄

![投資級與高收益信用利差](../../../../assets/usecases/quick/RX-USECASE-0067/02-credit-spreads.webp)

儘管供給創下高點，截至原始資料日期，IG 與 HY 利差仍處在歷史偏窄水準。

因此，發行增加不能自動解讀為需求疲弱。原始資料反而認為，**較高的絕對孳息吸引了足夠的投資需求，來吸收大量供給**。

## 用債務餘額成長近似供給

![債券供給成長](../../../../assets/usecases/quick/RX-USECASE-0067/03-bond-supply.webp)

聯邦政府債務被描述為已擴大到約 39 兆美元，非金融企業債券餘額約為 16 兆美元。

原始資料無法取得直接的總發行量時間序列，因此用**債務餘額年增淨額這個存量指標**近似供給。這和總發行量這個流量概念不同，解讀結果時需要區分。

## 把供給、需求與孳息放在一起看

這個工作流程的重點不是孤立地看發行規模，而是依下列順序連結市場：

**發行人 → 資金用途 → 國債與公司債供給 → 長期孳息 → 信用利差 → 投資需求。**

原始資料把 Fed 降息期間長期孳息仍上升的背景，與大量國債、公司債發行及較高期限溢價連結起來。同時，偏窄的信用利差說明**大量供給與強勁需求可以同時存在**。

## 限制

- 供給使用債務餘額年增近似，而不是直接的總發行量流量。
- 部分投資級債券發行規模來自次級市場評論，而不是初級發行資料庫。
- 債務餘額是季資料，孳息與利差是日資料，因此觀測日期不同。
- 核對具體數值時，應同時查看相關 FRED、SIFMA 序列及其日期。

下一步可進一步分析 AI 相關企業的發行，或美國國債標售的 bid-to-cover ratio，以深入研究供需。

---




本內容由 QUICK 提供。

視乎國家或地區、語言環境、使用產品、權限及數據涵蓋範圍，未必可以完全按本文方式重現本案例。

[← 固定收益使用案例](README.md) · [按資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)
