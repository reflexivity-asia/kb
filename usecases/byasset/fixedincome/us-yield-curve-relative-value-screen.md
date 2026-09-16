<!--
id: RX-USECASE-0030
type: use-case
language: en
locale: en
author: Reflexivity Research
published: 2026-09-15
status: published
translation_status: canonical
original_language: en
source_text_status: canonicalized_from_platform_research_with_reviewed_editorial_clarification
asset_class: Fixed Income (US Rates)
roles: Fixed Income PM, Rates Investor, Relative-Value Investor
publication_mode: faithful-source-preserving
-->

# Screen the US Yield Curve for Steepener and Flattener Candidates

**Author:** Reflexivity Research  
**Primary asset:** Fixed Income (US Rates)  
**Intended users:** Fixed Income PMs, Rates Investors, Relative-Value Investors  
**Analysis type:** Yield curve, relative value, screening

> This source is a correction follow-up, not the complete original research package. The page preserves the corrected screening table and decision logic that were actually provided rather than reconstructing missing earlier output.

## What this source corrects

The earlier output had a mismatch between some displayed trade labels and the underlying logic. This follow-up corrects that inconsistency.

The key lesson is that a curve segment cannot be classified from historical percentile alone. A spread may look unusually flat or inverted relative to history while **carry and rolldown make the apparent trade unattractive**.

## Corrected screening table

| Pair | Curve spread | Annualized spread | Historical percentile | Rolldown | Corrected view |
|---|---:|---:|---:|---:|---|
| 3y-2y | -9.7 bp | -9.7 bp | 9.6% | 23.6 bp | Neutral |
| 4y-3y | -0.9 bp | -0.9 bp | 15.2% | 8.8 bp | Neutral |
| 5y-4y | 3.3 bp | 3.3 bp | 28.7% | 4.2 bp | Steepener / pay |
| 7y-5y | 11.8 bp | 5.9 bp | 37.4% | 8.5 bp | Neutral |
| 8y-7y | 5.6 bp | 5.6 bp | 39.9% | -6.2 bp | Neutral |
| 12y-8y | 20.0 bp | 5.0 bp | 45.5% | 14.4 bp | Flattener / receive |
| 20y-12y | 20.3 bp | 2.5 bp | 51.9% | 0.2 bp | Neutral |
| 25y-20y | -0.7 bp | -0.1 bp | 21.9% | -21.0 bp | Steepener / pay |
| 30y-25y | -4.7 bp | -0.9 bp | 12.9% | -4.0 bp | Steepener / pay |

## Why 3y-2y and 4y-3y are neutral

The original error came from focusing on their low historical percentiles and coloring them as steepener candidates without reflecting the offsetting rolldown.

In the corrected logic:

- **3y-2y** sits at the 9.6th percentile, but rolldown is 23.6 bp
- **4y-3y** sits at the 15.2nd percentile, but rolldown is 8.8 bp

The apparent valuation signal and the carry/rolldown signal work against each other, so both pairs are reclassified as neutral.

## Corrected distribution

- **Steepener / pay:** 3 pairs — 5y-4y, 25y-20y, 30y-25y
- **Flattener / receive:** 1 pair — 12y-8y
- **Neutral:** 5 pairs — 3y-2y, 4y-3y, 7y-5y, 8y-7y, 20y-12y

## How to read the screen

The value of the example is not the individual trade labels themselves. It is the discipline of combining **historical relative value with carry and rolldown** before deciding whether a curve segment is actually attractive.

A low percentile can make a steepener look compelling at first glance. If holding the position imposes enough adverse rolldown, however, the more defensible conclusion may be neutral. The screen is therefore a starting point for deeper trade construction rather than an automatic signal generator.

## What this use case demonstrates

This correction is useful because it shows a research process that can revise its own output when display logic and economics disagree. The reusable pattern is: historical position → carry/rolldown → combined trade classification → correction when the components do not support the headline signal.

---

[← Fixed income use cases](README.md) · [Browse by asset class](../README.md) · [All use cases](../../README.md)
