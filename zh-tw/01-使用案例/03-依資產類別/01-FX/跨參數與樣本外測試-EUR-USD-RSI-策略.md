<!--
id: RX-USECASE-0037
type: use-case
language: zh
locale: zh-TW
author: Reflexivity Research
status: published
translation_status: current
original_language: en
source_text_status: canonicalized_from_platform_research_with_reviewed_editorial_clarification
asset_class: FX (EUR/USD)
roles: FX PM, Quant, Systematic Investor
publication_mode: faithful-source-preserving
-->

# 跨參數與樣本外測試 EUR/USD RSI 策略

<!-- locale-switcher:start -->
**Languages:** [English](../../../../en/01-use-cases/03-asset-class/01-FX/eurusd-rsi-walk-forward-backtest.md) · [日本語](../../../../ja/01-ユースケース/03-運用資産別/01-FX/EUR-USDのRSI戦略をパラメータ別・アウトオブサンプルで検証する.md) · [한국어](../../../../ko/01-유스케이스/03-운용자산별/01-FX/EUR-USD-RSI-전략을-파라미터와-아웃오브샘플로-검증하기.md) · [简体中文](../../../../zh-cn/01-使用案例/03-按资产类别/01-FX/用多组参数和样本外测试检验-EUR-USD-RSI-策略.md) · **繁體中文（台灣）** · [繁體中文（香港）](../../../../zh-hk/01-使用案例/03-按資產類別/01-FX/用多組參數及樣本外測試檢驗-EUR-USD-RSI-策略.md)
<!-- locale-switcher:end -->

[← FX 使用案例](README.md) · [依資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)

**作者：** Reflexivity Research  
**主要資產：** FX（EUR/USD）  
**適用使用者：** FX PM、量化研究員、系統化投資人  
**分析類型：** 回測、walk-forward 分析、穩健性測試

> 本頁保留 Reflexivity 原始研究，並納入經日文審閱版本確認的推理銜接。數據與市場環境皆為原始研究時點的歷史快照，不是目前的投資建議。

**[在 Reflexivity 中開啟這個研究範例 →](https://app.reflexivity.com/app/alfred?mode=research&conversationId=ad0d9afd-4ff6-4197-9bee-7075996df654&scrollTo=top)**

## 研究目的

如果在看過歷史資料之後才挑選特定回看期或門檻，RSI 策略很容易顯得特別漂亮。因此，單一「最佳參數」無法告訴我們策略是否真的具有可重複的優勢，或只是過度貼合樣本。

研究先在相同假設下比較多種回看期、門檻與交易規則，檢查績效是否能承受小幅參數變動。接著把樣本分成校準期與樣本外期間，測試第一階段表現較好的組合，在第二階段是否仍然有效。

因此，目的不是找出最好看的回測，而是衡量**參數敏感度、穩健性，以及過度擬合的程度**。

## 回測設計

研究以 EUR/USD 即期匯率進行兩年期均值回歸策略測試，唯一訊號為 RSI。

- RSI 回看期：**7 / 14 / 21**
- 門檻組合：**30/70、25/75、20/80**
- 交易規則：**Touch / Crossback**
- 組合總數：**18**
- 交易成本：**來回 1 pip**
- Walk-forward 結構：第一年校準，第二年進行樣本外驗證

## 重要資料限制

原始需求也包含四小時 K 線，但當時只有 EUR/USD 日資料可用。研究明確選擇**不合成、不捏造四小時資料**，因此只以日資料進行測試。

## 主要發現

1. **中等長度的回看期最穩定。** 短回看期帶來更高換手與更多雜訊，長回看期則產生較少交易。
2. **Walk-forward 測試暴露過度擬合。** 校準期最佳 Sharpe **2.47**，樣本外降至 **0.57**，下降 **1.90**。
3. 由於樣本期間 EUR/USD 點差較窄，交易成本平均只讓 CAGR 降低約 **0.11 個百分點**。更大的問題是底層優勢本身偏弱，而不是交易成本。
4. 即使完整樣本中最強的組合，淨 CAGR 也只有低個位數，因此絕對優勢並不大。

所以，完整樣本中看起來最好的組合，必須和 buy-and-hold 比較一起看；更重要的是，要看它在樣本外惡化了多少。

## 代表性 walk-forward 結果

只看完整樣本績效，無法排除參數只是剛好貼合該期間的可能性。因此下一步是比較校準結果與下一年的樣本外結果，並衡量 Sharpe 與 CAGR 的惡化幅度。

| 組合 | 校準 Sharpe Y1 | 校準淨 CAGR | OOS Sharpe Y2 | OOS 淨 CAGR | Sharpe 降幅 |
|---|---:|---:|---:|---:|---:|
| RSI-14 20/80 crossback | 2.47 | 3.5% | 0.57 | 1.4% | 1.90 |
| RSI-14 30/70 crossback | 1.66 | 6.3% | 0.61 | 1.8% | 1.05 |
| RSI-14 25/75 crossback | 1.47 | 4.5% | 0.67 | 2.2% | 0.80 |
| RSI-14 25/75 touch | 1.38 | 2.5% | 0.71 | 1.3% | 0.67 |
| RSI-21 20/80 touch | 1.37 | 0.6% | 0.33 | 0.4% | 1.04 |
| RSI-21 25/75 touch | 1.20 | 1.0% | -0.64 | -0.9% | 1.84 |

## 方法

- 樣本：**520 個日觀察值**，2024-09-09 至 2026-09-04
- Walk-forward 分割日：**2025-09-07**
- RSI 計算：Wilder smoothing
- Touch 規則：RSI 等於或低於超賣門檻時做多；等於或高於超買門檻時做空
- Crossback 規則：RSI 穿回門檻時進場；回到中性線時出場
- 交易在下一根 bar 執行，以避免 look-ahead bias

## 限制

- 只有日資料，沒有四小時資料驗證
- 兩年樣本對完整參數搜尋而言偏短
- 部分參數組合訊號很少，因此勝率與平均 P&L 的觀察數有限
- 未納入滑價、融資成本與部位大小調整
- 在實際交易成本較高的市場中，短回看期與高換手版本會最先惡化

## 如何解讀結果

研究重點不是「找出最佳回測」，而是**利用參數敏感度與樣本外惡化，找到策略最脆弱的地方**。

校準期最佳設定本身沒有那麼重要。更重要的是，結果能否跨越不同期間，以及規則小幅改動後，結論是否仍然相似。這些才是在把策略視為持久訊號之前需要繼續驗證的項目。

## 本使用案例說明了什麼

這個例子保留了一套可重複使用的研究流程：問題、測試設計、參數掃描、樣本外挑戰、限制，以及對哪些地方沒有維持住的解讀。


---

[← FX 使用案例](README.md) · [依資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)
