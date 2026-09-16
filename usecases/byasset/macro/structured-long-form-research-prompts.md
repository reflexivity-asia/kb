<!--
id: RX-USECASE-0039
type: use-case
language: en
locale: en
author: QUICK Inc.
provider: QUICK Inc.
provided: 2026-06-18
status: published
translation_status: canonical
source_type: partner-provided-use-case
asset_class: Macro, Equities, Multi-Asset
roles: Long-only Asset Manager, Hedge Fund Tier 1, Hedge Fund Tier 2
publication_mode: faithful-source-preserving
-->

# Structure Complex Research with Long-Form Instructions

**Author:** QUICK Inc.  
**Provided:** June 18, 2026  
**Primary assets:** Macro, Equities, Multi-Asset  
**Intended users:** Long-only Asset Managers, Hedge Fund Tier 1, Hedge Fund Tier 2

> This page is based on a use case provided by QUICK Inc. Customer names, recipients, email addresses, signatures, and private Conversation URLs have been removed while preserving the source prompt examples and their intent as closely as possible.

## When this approach is useful

For a broad research topic, a one-line instruction such as “analyze this theme” can leave the scope, comparison framework, and intended conclusion ambiguous.

The source shows a different approach: put **what to compare, the order in which to investigate it, and the desired final decision format** into the research instruction itself.

The purpose of a long prompt is not length. It is decomposition. A complex research task becomes easier to control when the instruction explicitly defines:

1. the target sectors or entities;
2. a common set of evaluation dimensions;
3. second-order effects such as geography or value-chain exposure;
4. the final synthesis, such as a matrix or prioritized list.

## Example 1: compare decarbonization needs across sectors

The source prompt asks for a global ranking across power generation, oil and gas, steel, cement, chemicals, transport, agriculture, and buildings. It specifies a common research sequence:

- absolute Scope 1/2/3 emissions and emissions intensity;
- technical abatement pathways and maturity;
- marginal abatement cost curves where available;
- regional policy risk;
- second-order effects on suppliers, customers, and substitution risk;
- a final priority matrix separating the largest emitters from the hardest-to-abate sectors.

The important design choice is the progression:

**emissions scale → abatement technology → abatement cost → policy differences → value chain → prioritization.**

That keeps “largest emitter” separate from “hardest to decarbonize” until the final synthesis.

The original material linked to a private Research result. This public page does not reconstruct that unavailable output.

## Example 2: expand from an event to affected companies

The source also gives prompt patterns for major corporate events, including planned large US IPOs.

The research instruction can explicitly move through:

**event → direct beneficiaries / negatively affected companies → historical analogues → broader market impact.**

This is more useful than asking only which companies are related to an event because it defines how the event should be translated into a research map.

## Example 3: use historical events to identify current beneficiaries

Another prompt asks which US and Japanese companies or industries could benefit from a football World Cup, using the previous five tournaments as the evidence base.

The sequence is deliberately:

**historical examples → recurring beneficiary pattern → apply the pattern to the current US and Japanese markets.**

This reduces the risk of inventing beneficiaries directly from the current event without checking precedent.

## Example 4: divide a political event into scenarios

The source includes an example asking for multiple possible scenarios around the 2026 US midterm elections and for analysis of how those scenarios could affect the US economy and equity market.

The useful prompt-design principle is not to assume one electoral outcome. It is to define **multiple scenarios first and then trace the economic and market transmission channels under each scenario**. The source example is a research-structure pattern, not an endorsement or prediction of any political outcome.

## How to use the workflow

For complex topics, the key is not writing a long paragraph. It is making four things explicit before the research starts:

**scope → comparison dimensions → investigation sequence → final output.**

If the resulting research misses the user's intent, this structure also makes it easier to see whether the problem was an omitted scope, a missing comparison dimension, or the wrong synthesis format.

## What this use case demonstrates

This workflow shows how to design the research process in the prompt itself so that complex multi-step analysis remains connected to the final decision question rather than becoming a collection of unrelated facts.

---

[← Macro use cases](README.md) · [Browse by asset class](../README.md) · [All use cases](../../README.md)
