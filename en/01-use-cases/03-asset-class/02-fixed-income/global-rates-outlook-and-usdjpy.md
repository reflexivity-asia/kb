<!--
id: RX-USECASE-0070
type: use-case
language: en
locale: en
provider: QUICK Inc.
source_created: 2026-09-30
provided: 2026-09-30
status: published
translation_status: canonical
source_type: partner-provided-use-case
source_manifest: RX-USECASE-0070
asset_class: Fixed Income, FX, Macro
insight_type: Scenario Insight
publication_mode: faithful-source-preserving
prompt_status: present
-->
# Analyze the Global Rates Outlook and the Implications for USD/JPY

<!-- locale-switcher:start -->
**Languages:** **English** · [日本語](../../../../ja/01-ユースケース/03-運用資産別/02-債券/金利上昇の見通しとドル円.md) · [한국어](../../../../ko/01-유스케이스/03-운용자산별/02-채권/금리상승-전망과-달러엔.md) · [简体中文](../../../../zh-cn/01-使用案例/03-按资产类别/02-固定收益/利率上升展望与美元日元.md) · [繁體中文（台灣）](../../../../zh-tw/01-使用案例/03-依資產類別/02-固定收益/利率上升展望與美元日圓.md) · [繁體中文（香港）](../../../../zh-hk/01-使用案例/03-按資產類別/02-固定收益/利率上升展望與美元日圓.md)
<!-- locale-switcher:end -->

[← Fixed Income use cases](README.md) · [Browse by asset class](../README.md) · [All use cases](../../README.md)

**Provided:** 2026-09-30  
**Primary assets:** Fixed Income, FX, Macro

> Figures and market conditions are historical snapshots from the supplied analysis, not current forecasts.

**[Open this research example in Reflexivity →](https://app.reflexivity.com/alfred?mode=research&conversationId=121c67ec-ef7a-4ad4-8526-608cf402fdd0&scrollTo=top)**

## Prompt used

> [!IMPORTANT]
> With US and European rates back near pre-financial-crisis levels and inflation still elevated, how might rates evolve? Use 30 years of history and examine the implications for rate differentials and USD/JPY.
## Historical comparison

The source compared current levels with 2007 and the broader 30-year range. Selected figures included:

| Source metric | Value |
|---|---:|
| US 10Y | 5.23% |
| 2007 US 10Y peak | 5.29% |
| Japan 10Y | 3.10% |
| Japan policy rate | 1.25% |
| US-Japan 10Y spread | +2.14 percentage points |
| 30-year peak in US-Japan 10Y spread | +4.95 percentage points (2000) |
| 30-year correlation of spread level with USD/JPY | 0.46 |
| USD/JPY in the source | 157.38 |

The source used monthly/annual history to place the current regime in context rather than reading the latest rate move alone.

![Historical 10-year government yields in the US, Germany, UK and Japan](../../../../assets/use-cases/RX-USECASE-0070/01-global-10y-yields.webp)

![Japan 10-year yield and USD/JPY in the source analysis](../../../../assets/use-cases/RX-USECASE-0070/02-japan-10y-usdjpy.webp)

![Policy-rate history used in the source scenario analysis](../../../../assets/use-cases/RX-USECASE-0070/03-policy-rates.webp)

## Scenario interpretation in the source

- **United States:** restrictive policy could give way to shallow easing, while the longer-run rate regime remains above the 2010s.
- **Euro area / United Kingdom:** additional modest easing was considered possible as disinflation progresses, without assuming a return to the prior zero-rate regime.
- **Japan:** the source scenario assumed gradual normalization could continue if the wage-price cycle persists.
- **USD/JPY:** narrowing US-Japan and Europe-Japan rate differentials would create medium-term yen-appreciation pressure, but the timing depends on the pace of BoJ normalization and the persistence of US long yields.

## What the workflow connects

The analysis combines sovereign yields, policy rates, CPI series, FX prices, historical rate-spread calculations and central-bank guidance. It then separates observed history from scenario inference.

## Limitations

The source explicitly states that the future rate path and USD/JPY view are analytical scenarios, not certain forecasts. Some CPI series have shorter histories; the UK 10-year series was monthly with the latest observation lagging the analysis date; and daily/monthly frequency differences can affect comparisons.

## Source note

This page is based on a QUICK-provided Reflexivity usage example dated 2026-09-30.

This content was provided by QUICK.

Depending on country or region, language environment, product used, entitlements, and data coverage, the example may not be directly reproducible as written.

[← Fixed Income use cases](README.md) · [All use cases](../../README.md)
