<!--
id: RX-USECASE-0067
type: use-case
language: en
locale: en
provider: QUICK Inc.
provided: 2026-09-25
status: published
translation_status: canonical
original_language: ja
source_text_status: translated_from_partner_source_reconciled_with_original
revised: 2026-09-27
editorial_reviewed: 2026-09-27
source_type: partner-provided-use-case
asset_class: Fixed Income, Macro
publication_mode: faithful-source-preserving
-->
# Analyze the US Bond-Issuance Market by Issuer, Use of Proceeds, Supply-Demand, and Yield

<!-- locale-switcher:start -->
**Languages:** **English** · [日本語](../../../../ja/ユースケース/運用資産別/債券/us-bond-issuance-market-analysis.md) · [한국어](../../../../ko/유스케이스/운용자산별/채권/us-bond-issuance-market-analysis.md) · [简体中文](../../../../zh-cn/使用案例/按资产类别/固定收益/us-bond-issuance-market-analysis.md) · [繁體中文（台灣）](../../../../zh-tw/使用案例/依資產類別/固定收益/us-bond-issuance-market-analysis.md) · [繁體中文（香港）](../../../../zh-hk/使用案例/按資產類別/固定收益/us-bond-issuance-market-analysis.md)
<!-- locale-switcher:end -->

[← Fixed income use cases](README.md) · [Browse by asset class](../README.md) · [All use cases](../../README.md)

**Provided:** 2026-09-25
**Primary assets:** Fixed Income, Macro

> Figures and market conditions in this example reflect the provided date.

> ### [Open this research example in Reflexivity →](https://app.reflexivity.com/alfred?mode=research&conversationId=71c1788f-7e54-4620-a6b2-ab163bd6762f&scrollTo=top)

## Question

**Bond issuance in the United States has been increasing. Analyze the main issuers and their uses of proceeds, and also examine supply-demand conditions and changes in yields.**

## Start with who is issuing and why

The source describes US bond issuance as expanding across both Treasuries and corporate bonds.

The main issuers are the **US Treasury**, financing a large fiscal deficit, and large **investment-grade companies** funding AI and data-center investment. Alphabet and Oracle are cited as examples of large technology issuers bringing jumbo deals.

The uses of proceeds are grouped into several categories:

- US Treasury: financing the fiscal deficit;
- corporates: AI and data-center capital expenditure;
- refinancing before borrowing costs rise further;
- M&A and LBO financing;
- shareholder returns such as buybacks.

## Yields rose, especially further out the curve

![US Treasury yields and the effective fed funds rate](../../../assets/usecases/quick/RX-USECASE-0067/01-us-treasury-fed-funds.webp)

| Indicator | Latest (2026-09-23) | One year earlier | Change |
| --- | ---: | ---: | ---: |
| 2-year Treasury yield | 4.85% | 3.53% | +1.32 pp |
| 10-year Treasury yield | 5.11% | 4.12% | +0.99 pp |
| 30-year Treasury yield | 5.40% | 4.73% | +0.67 pp |
| Effective fed funds rate | 3.63% | 4.33% | -0.70 pp |
| IG corporate OAS | 0.77% | 0.75% | +0.02 pp |
| HY corporate OAS | 2.73% | 2.71% | +0.02 pp |
| IG effective yield | 5.83% | 4.76% | +1.07 pp |
| HY effective yield | 7.68% | 6.40% | +1.28 pp |

The source interprets falling short-term policy rates alongside higher long-term Treasury yields as a form of **bear steepening**.

## Credit spreads stayed tight despite heavy supply

![Investment-grade and high-yield credit spreads](../../../assets/usecases/quick/RX-USECASE-0067/02-credit-spreads.webp)

Despite record supply, IG and HY spreads remained historically tight as of the source date.

That means the increase in issuance should not be read automatically as weak demand. The source instead interprets **high absolute yields as attracting enough investor demand to absorb the heavy supply**.

## Approximate supply with growth in debt outstanding

![Growth in bond supply](../../../assets/usecases/quick/RX-USECASE-0067/03-bond-supply.webp)

Federal debt is described as having expanded to roughly $39 trillion, while nonfinancial corporate bonds outstanding reached roughly $16 trillion.

The source could not obtain a direct time series for gross issuance, so it approximates supply using the **year-over-year net increase in debt outstanding, which is a stock measure**. That is conceptually different from gross issuance flow and should be kept in mind when interpreting the result.

## Read supply, demand, and yields together

The point of the workflow is not to look at issuance volume in isolation. It follows the market in this sequence:

**issuer → use of proceeds → Treasury and corporate supply → long-term yields → credit spreads → investor demand.**

The source links the rise in long-term yields, despite Fed rate cuts, to heavy Treasury and corporate issuance together with a higher term premium. At the same time, tight credit spreads indicate that **large supply and strong demand were coexisting**.

## Limitations

- Supply is approximated using the year-over-year increase in debt outstanding rather than direct gross-issuance flow.
- Some investment-grade issuance figures come from secondary market commentary rather than a primary issuance database.
- Debt-outstanding data are quarterly while yields and spreads are daily, so observation dates differ.
- For specific figures, the source recommends checking the relevant FRED and SIFMA series and their dates.

A useful follow-up is to examine issuance by AI-related companies or Treasury-auction bid-to-cover ratios to deepen the supply-demand analysis.

---

This content was provided by QUICK.

Depending on country or region, language environment, product used, entitlements, and data coverage, the example may not be directly reproducible as written.

[← Fixed income use cases](README.md) · [Browse by asset class](../README.md) · [All use cases](../../README.md)
