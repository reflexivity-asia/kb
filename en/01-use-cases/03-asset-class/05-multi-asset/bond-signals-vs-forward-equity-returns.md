<!--
id: RX-USECASE-0033
type: use-case
language: en
locale: en
author: Reflexivity Research
published: 2026-09-15
status: published
translation_status: canonical
original_language: en
source_text_status: canonicalized_from_reviewed_ja_rendering
publication_mode: faithful-source-preserving
-->

# Test whether bond-market signals relate to forward equity returns

<!-- locale-switcher:start -->
**Languages:** **English** · [日本語](../../../../ja/01-ユースケース/03-運用資産別/05-マルチアセット/債券市場の動きが株式の先行リターンと関係するか検証する.md) · [한국어](../../../../ko/01-유스케이스/03-운용자산별/05-멀티에셋/채권시장-신호가-이후-주식-수익률과-관계있는지-검증하기.md) · [简体中文](../../../../zh-cn/01-使用案例/03-按资产类别/05-多资产/检验债券市场信号是否与未来股票收益有关.md) · [繁體中文（台灣）](../../../../zh-tw/01-使用案例/03-依資產類別/05-多資產/檢驗債券市場訊號是否與未來股票報酬相關.md) · [繁體中文（香港）](../../../../zh-hk/01-使用案例/03-按資產類別/05-多資產/測試債券市場指標與未來股票回報是否有關.md)
<!-- locale-switcher:end -->

[← Multi-Asset use cases](README.md) · [Browse by asset class](../README.md) · [All use cases](../../README.md)
**Author:** Reflexivity Research  
**Primary asset classes:** Fixed income, equities, cross-asset  
**Intended users:** Multi-asset PMs, quants, asset allocators  
**Analysis type:** Cross-asset analysis, time-series analysis, hypothesis testing

> This page preserves the logic of an actual Reflexivity research output rather than reducing it to a conclusion. The figures and market observations are tied to the original research date.

**[Open this research example in Reflexivity →](https://app.reflexivity.com/app/alfred?conversationId=1ae89f55-bd78-4dfe-a303-65f8d4843d05&mode=research&activeHistorySidebarCategory=all)**

## What the research tested

The question was whether large moves in a bond-market spread were associated with a recognizable pattern in subsequent S&P 500 returns.

Rather than treating the current spread level as a trading signal by itself, the research placed the current observation inside its historical distribution and asked: **when the spread was at comparable levels in the past, what happened to equities over the next 20 trading days?**

## How the scatter plot was constructed

- Sample: **1,244 daily observations**
- Period: **September 2021 through August 2026**
- X-axis: the target spread, ordered from low to high
- Y-axis: **S&P 500 return over the following 20 trading days**
- Latest spread: highlighted separately to show its location in the historical distribution

This setup makes two things visible at the same time: where today's reading sits historically, and how dispersed the later equity outcomes were around similar spread levels.

## What the original research found

- Latest spread: **+7.72** as of 2026-09-01
- Five-year correlation between the spread and 20-trading-day-forward S&P 500 returns: **-0.22**
- Higher spread readings leaned somewhat toward lower subsequent returns on average, but the dispersion of forward equity outcomes at similar X-values was very wide

The research therefore characterized the relationship as **weak**, rather than turning a modest negative correlation into a stronger predictive claim.

That is the core of the use case: quantify the hypothesis and retain the possibility that the signal is not very useful.

## How to read the latest-value marker

The marker for the latest spread is plotted at Y=0 only as a visual reference showing where the current X-value sits.

It is **not** a forecast of the still-unobserved next-20-day equity return.

## Analytical caveats

- The 20-trading-day forward windows overlap.
- A correlation of -0.22 compresses a complex relationship into one linear statistic.
- The sample may be dominated by particular market regimes.
- Results may change materially if the spread definition, horizon, or sample period changes.

The practical lesson is to test cross-asset rules of thumb on actual time series and preserve weak or negative results instead of forcing a compelling narrative.

## What this use case demonstrates

This research shows how to move from a cross-asset intuition to a measurable test, place the current observation in historical context, and evaluate whether the apparent relationship is strong enough to deserve further use.


---

[← Multi-Asset use cases](README.md) · [Browse by asset class](../README.md) · [All use cases](../../README.md)
