<!--
id: RX-USECASE-0065
type: use-case
language: en
locale: en
provider: QUICK Inc.
provided: 2026-09-18
status: published
translation_status: canonical
original_language: ja
source_text_status: translated_from_partner_source_reconciled_with_original
revised: 2026-09-27
editorial_reviewed: 2026-09-27
source_type: partner-provided-use-case
asset_class: Equities
publication_mode: faithful-source-preserving
prompt_status: present
-->
# Find Japanese Companies Related to Rising US Stocks

<!-- locale-switcher:start -->
**Languages:** **English** · [日本語](../../../../ja/01-ユースケース/03-運用資産別/04-株式/上昇中の米国株から関連する日本企業を探す.md) · [한국어](../../../../ko/01-유스케이스/03-운용자산별/04-주식/상승한-미국-종목에서-관련-일본-기업을-찾기.md) · [简体中文](../../../../zh-cn/01-使用案例/03-按资产类别/04-股票/从上涨的美国股票中寻找相关日本公司.md) · [繁體中文（台灣）](../../../../zh-tw/01-使用案例/03-依資產類別/04-股票/從上漲的美國股票尋找相關日本公司.md) · [繁體中文（香港）](../../../../zh-hk/01-使用案例/03-按資產類別/04-股票/從上漲的美國股票尋找相關日本公司.md)
<!-- locale-switcher:end -->

[← Equities use cases](README.md) · [Browse by asset class](../README.md) · [All use cases](../../README.md)

**Provided:** 2026-09-18
**Primary assets:** Equities

> Figures and market conditions in this example reflect the provided date.

> ### [Open this research example in Reflexivity →](https://app.reflexivity.com/alfred?mode=research&conversationId=8d4011b7-597b-4361-ad87-501046a67b28&scrollTo=top)

## Prompt used
> Between the beginning of September and yesterday, identify the US industries and major stocks that have risen, then list Japanese companies related to those firms.

## Start by narrowing the US market leaders

The analysis first identifies stocks that rose in the US market between September 1 and September 17, 2026, then uses those leaders as the starting point for tracing links into the Japanese supply chain.

Semiconductors were a major source of strength, led by Intel, AMD, and Qualcomm. Meta rose in AI/platforms and Oracle in AI/cloud. Nvidia was roughly flat over the same period, showing that performance differed even within the semiconductor complex.

![Performance of selected US stocks](../../../../assets/usecases/quick/RX-USECASE-0065/01-us-stock-performance.webp)

| Company | Theme / industry | Return | Price, Sep. 1 → Sep. 17 |
| --- | --- | ---: | --- |
| Intel | Semiconductors | +22.3% | $88.97 → $108.80 |
| AMD | Semiconductors | +18.6% | $459.61 → $545.09 |
| Meta | AI / platforms | +17.9% | $578.54 → $682.31 |
| Qualcomm | Semiconductors | +13.3% | $166.61 → $188.71 |
| Oracle | AI / cloud | +6.6% | $141.32 → $150.59 |
| Micron | Memory semiconductors | +4.7% | $933.44 → $977.50 |
| TSMC | Foundry | +3.9% | $414.00 → $430.26 |

## How the workflow connects those moves to Japan

The next step breaks the rising US names into supply-chain categories such as **semiconductor manufacturing equipment, materials and substrates, memory, foundry exposure, and AI-chip back-end processing**.

### Semiconductor manufacturing equipment

The US-side demand drivers include capital spending by Intel, AMD, Nvidia, TSMC, and related semiconductor companies. The Japanese names identified in the source include:

- Tokyo Electron (8035)
- Lasertec (6920)
- Disco (6146)
- Advantest (6857)
- Kokusai Electric (6525)
- Towa (6315)
- Tokyo Seimitsu (7729)
- SCREEN Holdings (7735)

### Semiconductor materials and substrates

- SUMCO (3436)
- Tokyo Ohka Kogyo (4186)
- Shin-Etsu Chemical (4063)
- Ibiden (4062)
- Fujimi Incorporated (5384)
- Taiyo Holdings (4626)
- C. Uyemura (4966)
- HOYA (7741)

### Memory and back-end processing

The source also groups Kioxia, Kokusai Electric, Towa, Advantest, Disco, and Lasertec around memory-industry exposure and AI-chip back-end or inspection demand.

## Why this workflow is useful

The point is not to begin with a static list of Japanese semiconductor stocks. The sequence is:

**identify US stocks showing current price strength → classify the industries/themes behind the move → use the knowledge graph to expand into related Japanese companies.**

That turns a generic sector screen into a research path anchored in companies that are already showing meaningful market movement.

## Limitations

- The Japanese-company relationships reflect general supply-chain and thematic links represented in the knowledge graph.
- The analysis does not verify specific order values or revenue impact for each Japanese company.
- The observation window is short, at roughly two weeks, and stock performance varies materially even within the same industry.
- Prices and returns are based on the daily closes reported in the provided Reflexivity analysis.

The workflow can be extended by tracing competitors and suppliers for specific US companies such as Intel, AMD, or Qualcomm.

---

This content was provided by QUICK.

Depending on country or region, language environment, product used, entitlements, and data coverage, the example may not be directly reproducible as written.

[← Equities use cases](README.md) · [Browse by asset class](../README.md) · [All use cases](../../README.md)
