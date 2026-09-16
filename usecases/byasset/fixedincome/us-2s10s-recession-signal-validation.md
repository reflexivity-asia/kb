<!--
id: RX-USECASE-0031
type: use-case
language: en
locale: en
author: Reflexivity Research
published: 2026-09-15
status: published
translation_status: canonical
original_language: en
source_text_status: canonicalized_from_platform_research_with_reviewed_editorial_clarification
asset_class: Fixed Income (US Rates), Macro
roles: Fixed Income PM, Macro Strategist, Asset Allocator
publication_mode: faithful-source-preserving
-->

# Test Whether the US 2s10s Curve Historically Predicted Recessions

**Author:** Reflexivity Research  
**Primary assets:** Fixed Income (US Rates), Macro  
**Intended users:** Fixed Income PMs, Macro Strategists, Asset Allocators  
**Analysis type:** Hypothesis testing, time-series analysis

> This page preserves a dated Reflexivity research output and its limitations. One statistic in the source appears to require revalidation, so the results below should not be treated as independently verified historical facts.

## Research question

**Has an inversion of the US 2-year / 10-year Treasury spread historically predicted a recession nine to twelve months later?**

The source examines 1976–2025 and tests the familiar yield-curve rule across several lead windows. The broader purpose is to ask whether a widely repeated market heuristic survives an explicit data test — including false positives and missed recessions.

> **Data-quality caution:** the source contains values whose construction and definitions should be rechecked. In particular, its statement that the curve was inverted for **83.5% of the period since 1976** appears unusual and requires revalidation. This page records the research output faithfully; it does not present that statistic as a verified general fact.

## Results by lead window in the source

| Metric | 9 months | 10 months | 11 months | 12 months |
|---|---:|---:|---:|---:|
| Sensitivity | 56.9% | 55.2% | 50.0% | 44.8% |
| Precision | 6.8% | 6.6% | 6.0% | 5.4% |
| False-positive rate | 86.5% | 86.7% | 87.3% | 87.9% |
| Accuracy | 17.9% | 17.5% | 16.5% | 15.4% |

The source highlights the ten-month window, where precision is reported at **6.6%** and the false-positive rate at **86.7%**. Its conclusion is that treating “the curve inverted” as a directly actionable recession signal would have generated many false alarms under the source's definitions.

## Recession-by-recession review in the source

| Recession | Period | Inversion 9–12 months before? | Source average spread |
|---|---|---|---:|
| 1980-02 to 1980-08 | 6 months | No | 0.60% |
| 1981-08 to 1982-12 | 16 months | Yes | 0.53% |
| 1990-08 to 1991-04 | 8 months | Yes | 0.04% |
| 2001-04 to 2001-12 | 8 months | No | 0.36% |
| 2008-01 to 2009-07 | 18 months | Yes | 0.03% |
| 2020-03 to 2020-05 | 2 months | Yes | -0.21% |

## Main points from the source

1. **Low reported precision** means that recession warnings greatly outnumbered realized recessions under the test setup.
2. The source classifies four of six recessions as captured while missing the 1980 and 2001 episodes.
3. It notes that QE, global demand for Treasuries, and changes in market structure could alter the relationship across regimes.
4. It recommends comparing 2s10s with other curve definitions and with unemployment, credit spreads, and leading indicators rather than using one spread in isolation.

## Additional tests proposed by the source

- compare predictive performance with changes in unemployment, credit spreads, and leading economic indicators;
- test alternative curve definitions such as 3m10y and 1y10y;
- split the sample around major structural shifts, including the introduction of QE around the global financial crisis.

## How to read the result

The useful lesson is not “the inverted curve is right” or “the inverted curve is wrong.” It is to take a market rule that is often repeated as conventional wisdom and **force it through explicit definitions, lead windows, false-positive accounting, and regime checks**.

Because the source itself contains at least one statistic that appears questionable, the next step before relying on the reported performance should be to reproduce the data construction and verify the recession labeling and inversion definition.

## What this use case demonstrates

This example shows both the value and the limits of automated hypothesis testing: Reflexivity can structure the historical test and expose false positives, while the analyst still has to interrogate surprising statistics and validate the data definition before treating the output as established evidence.

---

[← Fixed income use cases](README.md) · [Browse by asset class](../README.md) · [All use cases](../../README.md)
