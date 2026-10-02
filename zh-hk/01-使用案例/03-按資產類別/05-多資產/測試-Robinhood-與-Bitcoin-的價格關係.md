<!--
id: RX-USECASE-0050
type: use-case
language: zh
locale: zh-HK
provider: QUICK Corporation
provided: 2026-08-24
status: published
translation_status: current
source_type: partner-provided-use-case
asset_class: equities, crypto, multi-asset
publication_mode: faithful-source-preserving
prompt_status: present
-->

# 測試 Robinhood 與 Bitcoin 的價格關係

<!-- locale-switcher:start -->
**Languages:** [English](../../../../en/01-use-cases/03-asset-class/05-multi-asset/robinhood-bitcoin-correlation.md) · [日本語](../../../../ja/01-ユースケース/03-運用資産別/05-マルチアセット/Robinhood株とビットコインの価格連動性を検証する.md) · [한국어](../../../../ko/01-유스케이스/03-운용자산별/05-멀티에셋/Robinhood와-Bitcoin의-가격-관계를-검증하기.md) · [简体中文](../../../../zh-cn/01-使用案例/03-按资产类别/05-多资产/检验-Robinhood-与-Bitcoin-的价格关系.md) · [繁體中文（台灣）](../../../../zh-tw/01-使用案例/03-依資產類別/05-多資產/檢驗-Robinhood-與-Bitcoin-的價格關係.md) · **繁體中文（香港）**
<!-- locale-switcher:end -->

[← 多資產使用案例](README.md) · [按資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)

**提供日期：** 2026-08-24  
**主要資產：** 股票、crypto、多資產

> 本頁保留 QUICK 提供的使用案例。數字及市場觀察均屬來源日期快照。

## 使用的提示詞
> [!IMPORTANT]
> 分析 `@HOOD` 與 Bitcoin 價格的 correlation。用 `@` 加 ticker 可在公司名稱相似時提高 entity resolution 準確度。
![Robinhood 與 Bitcoin 的價格關係](../../../../assets/usecases/quick/RX-USECASE-0050/source-visuals.webp)

## 研究要建立甚麼

兩張價格圖都大致向上，不代表每天都緊密同步。價格**水平**的高 correlation 亦可能只是因為兩個資產共享長期趨勢。

因此研究分四步：

1. 比較過去一年主要高低位及急升急跌日期；
2. 比較 price-level correlation 與 daily-return correlation；
3. 找出 HOOD 與 Bitcoin 出現背離的時期；
4. 再問哪些經濟機制可以同時解釋 correlation 及關係破裂。

即：**視覺共振 → 數量 correlation → 例外 → 經濟解讀**。

## 來源快照：2025 年 8 月至 2026 年 8 月

| Episode | 時間 | HOOD | Bitcoin | 方向 |
|---|---|---|---|---|
| 起點 | 2025 年 8 月下旬 | ~108 | ~110,000 | — |
| 高位 | 2025 年 10 月初 | ~150 | ~124,800 | 同處高位附近 |
| 急跌 | 2026 年 2 月初 | 72 | ~63,300 | 同時大跌 |
| 次低位 | 2026 年 6 月 | ~93 | ~58,500 | 部分背離 |
| 近期反彈 | 2026-08-21 | 108 | ~78,400 | 同時急彈 |

QUICK 來源描述期內存在較強正向關係，估算 price-level correlation 約 **+0.8**，daily-return correlation 約 **+0.5 至 +0.6**。

## 為何要分開 levels 與 returns

高水平 correlation 可能只是兩個資產長期都向上。Daily-return correlation 問的是更嚴格的問題：**每日價格變動本身是否真的同步？**

兩者一起看，較容易區分共享長期趨勢與短期共振。

## 背離與 correlation 同樣重要

來源特別指出 2026 年 6 月：Bitcoin 繼續下跌，但 HOOD 回升至約 105–108。

這顯示 HOOD 並非簡單的 Bitcoin proxy。業績、交易活動、business mix 或 guidance 等公司因素，在某些時期可以壓過 crypto 關係。

## 經濟解讀

來源把關係連到兩個渠道：

- Robinhood 對 crypto trading activity 有 exposure，因此 Bitcoin 環境可影響 transaction revenue 及 engagement 預期；
- HOOD 與 Bitcoin 都可以像較高 beta 的 risk asset，對利率及 risk appetite 等共同宏觀因素作出反應。

兩個渠道都不代表永久一對一關係。

## 如何使用結果

不要把高 correlation 當成 HOOD 永遠與 Bitcoin 同步的證明。更有用的是監察關係何時穩定、何時破裂，並跟進：

- crypto trading volume；
- Robinhood 業績及 guidance；
- business mix 變化；
- 利率及 broader risk appetite。

## 限制

- 來源 correlation 估算為近似值；
- correlation 依賴 sample 及 horizon；
- 共同宏觀驅動因素可以提高 correlation，而不代表直接因果；

## 本使用案例說明了甚麼

這套流程由表面跨資產共振走到 return-based correlation，再主動找出破壞關係的時期。

---

本內容由 QUICK 提供。

視乎國家或地區、語言環境、使用產品、權限及數據涵蓋範圍，未必可以完全按本文方式重現本案例。

[← 多資產使用案例](README.md) · [按資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)
