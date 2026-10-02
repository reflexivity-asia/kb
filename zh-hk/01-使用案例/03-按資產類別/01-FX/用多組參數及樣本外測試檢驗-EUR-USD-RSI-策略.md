<!--
id: RX-USECASE-0037
type: use-case
language: zh
locale: zh-HK
author: Reflexivity Research
status: published
translation_status: current
original_language: en
source_text_status: canonicalized_from_platform_research_with_reviewed_editorial_clarification
asset_class: FX (EUR/USD)
roles: FX PM, Quant, Systematic Investor
publication_mode: faithful-source-preserving
prompt_status: not_provided
-->

# 用多組參數及樣本外測試檢驗 EUR/USD RSI 策略

<!-- locale-switcher:start -->
**Languages:** [English](../../../../en/01-use-cases/03-asset-class/01-FX/eurusd-rsi-walk-forward-backtest.md) · [日本語](../../../../ja/01-ユースケース/03-運用資産別/01-FX/EUR-USDのRSI戦略をパラメータ別・アウトオブサンプルで検証する.md) · [한국어](../../../../ko/01-유스케이스/03-운용자산별/01-FX/EUR-USD-RSI-전략을-파라미터와-아웃오브샘플로-검증하기.md) · [简体中文](../../../../zh-cn/01-使用案例/03-按资产类别/01-FX/用多组参数和样本外测试检验-EUR-USD-RSI-策略.md) · [繁體中文（台灣）](../../../../zh-tw/01-使用案例/03-依資產類別/01-FX/跨參數與樣本外測試-EUR-USD-RSI-策略.md) · **繁體中文（香港）**
<!-- locale-switcher:end -->

[← FX 使用案例](README.md) · [按資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)

**作者：** Reflexivity Research  
**主要資產：** FX（EUR/USD）  
**適用使用者：** FX PM、Quant、Systematic Investor  
**分析類型：** 回測、walk-forward analysis、穩健性測試

> 本頁保留 Reflexivity 原始研究，並納入經審閱版本已確認的解釋橋樑。數字及市場狀況均為原始研究的歷史快照，不是現時投資建議。

**[在 Reflexivity 中開啟這個研究示例 →](https://app.reflexivity.com/app/alfred?mode=research&conversationId=ad0d9afd-4ff6-4197-9bee-7075996df654&scrollTo=top)**

## 研究目標

RSI 策略如果在看過歷史數據後才挑選 lookback period 或 threshold，很容易出現漂亮但過度配合樣本的結果。單一「最佳參數」因此不能證明策略具有可重複的 edge。

研究先在相同假設下比較多組 lookback、threshold 及交易規則，檢查小幅改動參數後績效是否仍然存在；之後再把樣本分為 calibration 與 out-of-sample 期間，測試第一段表現較強的組合能否在第二段維持。

目標不是找最漂亮的 backtest，而是量度**參數敏感度、穩健性及 overfitting 程度**。

## 回測設計

研究以 EUR/USD spot 測試兩年 mean-reversion 策略，唯一訊號為 RSI。

- RSI lookback：**7 / 14 / 21**
- Threshold pairs：**30/70、25/75、20/80**
- Trading rules：**Touch / Crossback**
- 總組合：**18**
- 交易成本：**1 pip round trip**
- Walk-forward：第一年 calibration，第二年 out-of-sample validation

## 重要數據限制

原始要求亦包括四小時 bars，但當時只有每日 EUR/USD 數據可用。研究明確**沒有合成或虛構四小時數據**，只用 daily data 進行測試。

## 主要發現

1. **中等 lookback 最穩定。** 較短 lookback turnover 較高、雜訊較多；較長 lookback 則交易次數偏少。
2. **Walk-forward 測試揭示 overfitting。** Calibration 最佳 Sharpe 為 **2.47**，樣本外跌至 **0.57**，下降 **1.90**。
3. 由於樣本內 EUR/USD spread 較窄，交易成本平均只令 CAGR 減少約 **0.11 個百分點**。更大的問題是底層 edge 本身偏弱，而不是成本。
4. 即使全樣本表現最好的組合，淨 CAGR 亦只有低單位數，因此絕對 edge 並不大。

所以，全期間「最好」的組合必須連同 buy-and-hold 比較，以及更重要的樣本外衰退一併閱讀。

## 代表性 walk-forward 結果

| Combo | Cal Sharpe Y1 | Cal Net CAGR | OOS Sharpe Y2 | OOS Net CAGR | Sharpe drop |
|---|---:|---:|---:|---:|---:|
| RSI-14 20/80 crossback | 2.47 | 3.5% | 0.57 | 1.4% | 1.90 |
| RSI-14 30/70 crossback | 1.66 | 6.3% | 0.61 | 1.8% | 1.05 |
| RSI-14 25/75 crossback | 1.47 | 4.5% | 0.67 | 2.2% | 0.80 |
| RSI-14 25/75 touch | 1.38 | 2.5% | 0.71 | 1.3% | 0.67 |
| RSI-21 20/80 touch | 1.37 | 0.6% | 0.33 | 0.4% | 1.04 |
| RSI-21 25/75 touch | 1.20 | 1.0% | -0.64 | -0.9% | 1.84 |

## 方法

- 樣本：**520 個每日觀察值**，2024-09-09 至 2026-09-04
- Walk-forward 分界：**2025-09-07**
- RSI 計算：Wilder smoothing
- Touch rule：RSI 低於或等於 oversold threshold 時做多；高於或等於 overbought threshold 時做空
- Crossback rule：RSI 穿回 threshold 時入場；回到 neutral line 時離場
- 所有交易於下一個 bar 執行，以避免 look-ahead bias

## 限制

- 只有 daily data，沒有四小時 validation
- 兩年樣本對全面參數搜索而言偏短
- 部分參數組合訊號很少，win rate 及 average P&L 的觀察數不足
- 未計 slippage、financing cost 及 position-size adjustment
- 若實際交易成本較高，短 lookback、高 turnover 版本會最先惡化

## 如何閱讀結果

研究故事不是「找出最佳回測」，而是**利用參數敏感度及樣本外績效衰退，找出策略在哪裡脆弱**。

Calibration 最佳設定本身並非最重要；更重要的是結果能否跨期間維持，以及輕微改變規則後結論是否仍相近。這些才是把策略視為較持久訊號之前應做的下一輪測試。

## 本使用案例說明了甚麼

這個例子保留了可重複的研究過程：問題、測試設計、參數 sweep、樣本外挑戰、限制，以及對失效部分的解讀。


---

[← FX 使用案例](README.md) · [按資產類別瀏覽](../README.md) · [全部使用案例](../../README.md)
