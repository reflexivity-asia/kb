<!--
id: RX-USECASE-0047
type: use-case
language: en
locale: en
author: QUICK Inc.
provider: QUICK Inc.
provided: 2025-12-26
status: published
translation_status: canonical
source_type: partner-provided-use-case
asset_class: Equities
roles: Long-only Asset Manager, Hedge Fund Tier 2, Hedge Fund Tier 3
publication_mode: faithful-source-preserving
-->

# Turn Strong Themes into US and Japanese Company Candidates

**Author:** QUICK Inc.  
**Provided:** December 26, 2025  
**Primary asset:** Equities  
**Intended users:** Long-only Asset Managers, Hedge Fund Tier 2, Hedge Fund Tier 3

> This page is based on a use case provided by QUICK Inc. Customer names, recipients, email addresses, signatures, and private URLs have been removed while preserving the source question, candidate list, and screening logic. The list is a research-universe starting point, not a recommendation list.

## When this workflow is useful

A theme leaderboard can tell an investor which areas are performing well, but it does not directly identify the companies worth researching.

The source uses the strongest one-month US equity themes as the starting point, then asks Alfred for related US and Japanese organizations. The purpose is to build a **research universe**, not to select final investments.

The workflow is:

**strong theme → related company candidates → investability / financial filters → deeper company research.**

The original prompt did not require listed companies only and did not yet apply financial-quality filters, which is why a non-listed institution such as JAXA appears in the source output.

## Original research prompt

> For the themes gene editing, satellite technology, space exploration, copper mining, and gold production, list three related organizations in the US and three in Japan for each category.

## Candidate universe from the source

### Gene editing

**United States**
- CRISPR Therapeutics — gene-editing therapies using CRISPR-Cas9
- Intellia Therapeutics — CRISPR-based genome-editing medicines
- Editas Medicine — gene-editing therapies for genetic disease

**Japan**
- Takara Bio — gene-transfer and analysis technologies; gene / regenerative medicine research
- SanBio — regenerative-medicine product development
- Gene Techno Science — gene-therapy development and manufacturing-related activity in the source

### Satellite technology

**United States**
- Maxar Technologies — Earth-observation imagery and geospatial services
- Planet Labs — small-satellite constellations and frequent Earth imaging
- SpaceX — Starlink satellite internet

**Japan**
- Mitsubishi Electric — satellite buses and onboard equipment
- NEC — satellite communications, ground systems, and onboard equipment
- Canon Electronics — small-satellite development and manufacturing

### Space exploration

**United States**
- SpaceX — reusable launch systems and space transportation
- Blue Origin — launch vehicles and space infrastructure
- Lockheed Martin — spacecraft and systems for exploration missions

**Japan**
- Mitsubishi Heavy Industries — launch systems and launch services
- JAXA — public space agency; included because the source prompt was not limited to listed companies
- IHI — rocket-engine and space-development exposure

### Copper mining

**United States / North America-oriented candidates in the source**
- Freeport-McMoRan
- Southern Copper
- Kennecott / Rio Tinto

**Japan**
- Sumitomo Metal Mining
- Mitsui Mining & Smelting
- JX Advanced Metals

The Japanese candidates are generally exposed through overseas resource development, smelting, or related materials businesses rather than large domestic copper mines.

### Gold production

**United States / North America-oriented candidates in the source**
- Barrick Gold
- Newmont
- Kinross Gold

**Japan**
- Sumitomo Metal Mining
- TANAKA Precious Metals
- Mitsubishi Materials

The source notes that Japan has relatively few large domestic gold or copper mines, so many Japanese candidates are exposed through overseas development, refining, recycling, or precious-metals processing.

## What to check next

This candidate list answers only “which organizations are related?” The source explicitly notes that the screen has not yet been restricted to listed companies or evaluated on financial quality.

A practical next-stage filter can add:

- listed companies only;
- percentage of revenue or profit actually exposed to the theme;
- market capitalization and liquidity;
- balance-sheet quality and earnings outlook;
- valuation;
- target market or geography.

This prevents a strong theme from being converted directly into a “buy list.” The theme first expands the search space; investment constraints then narrow it.

## Source-visual status

The reviewed Japanese publication contains a verified QUICK source screen for this use case. It has not yet been byte-synchronized into the English repository, so no broken or substitute visual is published here.

## What this use case demonstrates

This workflow starts with market leadership and turns it into a cross-market research universe. It is useful for discovering less-obvious company candidates before applying investability, fundamentals, and valuation filters.

---

[← Equities use cases](README.md) · [Browse by asset class](../README.md) · [All use cases](../../README.md)
