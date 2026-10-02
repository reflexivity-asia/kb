<!--
id: RX-USECASE-0051
type: use-case
language: zh
locale: zh-TW
provider: QUICK Inc.
provided: 2026-08-05
status: published
translation_status: current
source_type: partner-provided-use-case
asset_class: Equities
roles: Long-only Asset Manager, Hedge Fund Tier 2, Hedge Fund Tier 3
publication_mode: faithful-source-preserving
-->

# 比較 S&P 500 與 Russell 2000，並找出小型股領先者

<!-- locale-switcher:start -->
**Languages:** [English](../../../../en/01-use-cases/03-asset-class/04-equities/sp500-vs-russell2000-leaders.md) · [日本語](../../../../ja/01-ユースケース/03-運用資産別/04-株式/S&P-500とRussell-2000を比較し-小型株の上昇銘柄を特定する.md) · [한국어](../../../../ko/01-유스케이스/03-운용자산별/04-주식/S&P-500과-Russell-2000을-비교하고-소형주-주도주를-찾기.md) · [简体中文](../../../../zh-cn/01-使用案例/03-按资产类别/04-股票/比较-S&P-500-与-Russell-2000-并找出小盘股领涨者.md) · **繁體中文（台灣）** · [繁體中文（香港）](../../../../zh-hk/01-使用案例/03-按資產類別/04-股票/比較-S&P-500-與-Russell-2000-並找出小型股領先者.md)
<!-- locale-switcher:end -->

[← 股票使用案例](README.md) · [依資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)

**提供日期：** 2026-08-05  
**主要資產：** 股票  
**適用使用者：** Long-only 資產管理人、對沖基金

> QUICK 原資料只提供研究問題與私有 Research 結果連結；該私有結果並未公開。以下工作流程說明是**對原始問題研究邏輯的編輯性澄清，不是對不可存取 Research 輸出的重建**。

## 問題

> 比較並分析 2026 年 1 月至今 S&P 500 與 Russell 2000 的表現，再找出 Russell 2000 中表現最好的五家公司，說明其股價上漲原因。

## 研究目標

只比較兩個指數，可以知道大型股與小型股誰相對較強，但無法說明真正推動小型股結果的是什麼。反過來，如果只看表現最好的個股，又可能忽略這些贏家到底代表廣泛的 size rotation，還是少數個別事件。

因此，原始問題自然形成一個逐步縮小範圍的研究順序：

**指數層級相對表現 → 小型股 universe 內的領先者 → 公司特有 catalyst。**

## 研究工作流程

### 1. 用同一期間比較兩個指數

以相同起始日與結束日衡量 S&P 500 與 Russell 2000 的表現。先確認市場是大型股相對強勢還是小型股相對強勢，再進入個股解釋。

### 2. 排出 Russell 2000 中最強的成分股

找出小型股基準中表現最好的五家公司。這可以看出 universe 內真正出現極端上行的是哪些公司，而不是假設指數漲跌平均分布於所有成分股。

### 3. 解釋每個領先股的走勢

可調查的公司特有因素包括：

- earnings 與 guidance；
- 產品或合約公告；
- M&A；
- 產業或主題曝險；
- 其他重大公司 catalyst。

目的在於確認前五名是否具有共同驅動因素，或只是因不同公司事件各自上漲。

### 4. 把公司證據重新連回指數比較

如果多個領先股都屬於同一產業或因子，小型股走勢可能代表指數內較廣泛的主題；如果原因高度個別化，那麼最強個股對 Russell 2000 整體 regime 的代表性就較低。

## 如何使用這個工作流程

這個研究模式的價值，在於不把指數比較與個股篩選當成兩個彼此分離的練習。

先看 size rotation，再找出報酬來自哪裡，最後檢驗領先股是否共享同一主題。同樣的模式也可套用於：

- growth vs value；
- 美國 vs 日本；
- large cap vs mid/small cap；
- sector index vs broad benchmark。

## 本使用案例說明了什麼

因為原始私有 Research 結果沒有在此重建，本頁只展示原始問題能支持的可重複分析順序：**benchmark comparison → leader extraction → catalyst analysis → breadth interpretation**。

---








本內容由 QUICK 提供。

依國家或地區、語言環境、使用產品、權限與資料涵蓋範圍不同，可能無法完全依照本文方式重現本案例。

[← 股票使用案例](README.md) · [依資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)
