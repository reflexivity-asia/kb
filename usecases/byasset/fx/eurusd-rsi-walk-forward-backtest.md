<!--
id: RX-USECASE-0037
type: use-case
language: en
locale: en
author: Reflexivity Research
status: published
translation_status: canonical
original_language: en
source_text_status: canonicalized_from_platform_research_with_reviewed_editorial_clarification
asset_class: FX (EUR/USD)
roles: FX PM, Quant, Systematic Investor
publication_mode: faithful-source-preserving
-->

# Test a EUR/USD RSI Strategy Across Parameters and Out of Sample

**Author:** Reflexivity Research  
**Primary asset:** FX (EUR/USD)  
**Intended users:** FX PMs, Quants, Systematic Investors  
**Analysis type:** Backtest, walk-forward analysis, robustness testing

> This page preserves the underlying Reflexivity research while incorporating the reasoning bridges validated in the reviewed Japanese edition. Figures and market conditions are historical snapshots from the original research, not current investment advice.

## Research objective

An RSI strategy can look attractive if a particular lookback period or threshold is chosen after seeing the historical data. A single “best parameter” therefore does not tell us whether the strategy has a repeatable edge or is simply overfit to the sample.

The research first compares multiple lookback periods, thresholds, and trading rules under the same assumptions to see whether performance survives small parameter changes. It then splits the sample into calibration and out-of-sample periods to test whether combinations that looked strong in the first period still work in the second.

The objective is therefore not to search for the most flattering backtest. It is to measure **parameter sensitivity, robustness, and the degree of overfitting**.

## Backtest design

The study tests a two-year mean-reversion strategy on EUR/USD spot using RSI as the only signal.

- RSI lookback: **7 / 14 / 21**
- Threshold pairs: **30/70, 25/75, 20/80**
- Trading rules: **Touch / Crossback**
- Total combinations: **18**
- Trading cost: **1 pip round trip**
- Walk-forward structure: year one for calibration, year two for out-of-sample validation

## Important data limitation

The request also included four-hour bars, but only daily EUR/USD data was available. The research explicitly **did not synthesize or fabricate four-hour data** and ran the test on daily data only.

## Main findings

1. **Intermediate lookbacks were the most stable.** Short lookbacks produced higher turnover and more noise, while long lookbacks generated relatively few trades.
2. **Walk-forward testing exposed overfitting.** The calibration-best Sharpe of **2.47** fell to **0.57** out of sample, a decline of **1.90**.
3. Because EUR/USD spreads were narrow in this sample, trading costs reduced CAGR by only about **0.11 percentage points on average**. The larger problem was the weakness of the underlying edge rather than transaction costs.
4. Even the strongest full-sample combination produced only a low-single-digit net CAGR, so the absolute edge was not large.

A combination that looks best over the full period therefore needs to be read together with its buy-and-hold comparison and, more importantly, how much its performance deteriorates out of sample.

## Representative walk-forward results

Full-sample performance alone cannot rule out the possibility that the chosen parameters simply fit that particular period. The next step is therefore to compare the calibration result with the following year's out-of-sample result and measure the deterioration in Sharpe and CAGR.

| Combo | Cal Sharpe Y1 | Cal Net CAGR | OOS Sharpe Y2 | OOS Net CAGR | Sharpe drop |
|---|---:|---:|---:|---:|---:|
| RSI-14 20/80 crossback | 2.47 | 3.5% | 0.57 | 1.4% | 1.90 |
| RSI-14 30/70 crossback | 1.66 | 6.3% | 0.61 | 1.8% | 1.05 |
| RSI-14 25/75 crossback | 1.47 | 4.5% | 0.67 | 2.2% | 0.80 |
| RSI-14 25/75 touch | 1.38 | 2.5% | 0.71 | 1.3% | 0.67 |
| RSI-21 20/80 touch | 1.37 | 0.6% | 0.33 | 0.4% | 1.04 |
| RSI-21 25/75 touch | 1.20 | 1.0% | -0.64 | -0.9% | 1.84 |

## Method

- Sample: **520 daily observations**, September 9, 2024 to September 4, 2026
- Walk-forward split: **September 7, 2025**
- RSI calculation: Wilder smoothing
- Touch rule: long at or below the oversold threshold; short at or above the overbought threshold
- Crossback rule: enter when RSI crosses back through the threshold; exit at the neutral line
- Trades are executed on the following bar to avoid look-ahead bias

## Limitations

- Daily data only; no four-hour validation
- Two years is a short sample for an exhaustive parameter search
- Some parameter combinations generate few signals, leaving limited observations for win rate and average P&L
- Slippage, financing costs, and position-size adjustments are not included
- In markets with higher realized trading costs, short-lookback and high-turnover variants would deteriorate first

## How to read the result

The research story is not “find the best backtest.” It is **use parameter sensitivity and out-of-sample deterioration to find where the strategy is weak**.

The calibration-best setting itself is less important than whether the result survives a different period and whether the conclusion remains similar when the rules are changed slightly. Those are the next tests before treating the strategy as a durable signal.

## What this use case demonstrates

This example preserves a reusable research process: the question, test design, parameter sweep, out-of-sample challenge, limitations, and the interpretation of what failed to hold up.

---

[← FX use cases](README.md) · [Browse by asset class](../README.md) · [All use cases](../../README.md)
