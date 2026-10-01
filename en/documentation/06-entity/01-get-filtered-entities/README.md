<!--
id: RX-PRODUCT-1057
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a269fb8e429230e769e416b
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: entity/get-filtered-entities
-->

# Get filtered entities

**Method:** `POST`

**Endpoint:** `/entity/v2/filtered`

#### Body Parameters

filterinteger

- 2 - FilterTag

Enum values:

`2`

argsarray

Show child attributes

### Response

200

Object

Return list of entities.

#### Response Attributes

tagstring

idstring

known_asstring

namestring

name_fullstring

name_shortstring

activeboolean

asset_classinteger

- 0 - ASSET_CLASS_UNSPECIFIED
- 1 - ASSET_CLASS_COMMODITY
- 2 - ASSET_CLASS_FX
- 3 - ASSET_CLASS_EQUITY
- 4 - ASSET_CLASS_FI
- 5 - ASSET_CLASS_CURRENCY

Enum values:

`0``1``2``3``4``5`

classinteger

- 0 - CLASS_UNSPECIFIED
- 1 - CLASS_ECO
- 2 - CLASS_COMMODITY
- 3 - CLASS_CREDIT
- 4 - CLASS_EQUITY
- 5 - CLASS_ETF
- 6 - CLASS_FI
- 7 - CLASS_FUTURE
- 8 - CLASS_FX
- 9 - CLASS_STOCK
- 10 - CLASS_CURRENCY
- 11 - CLASS_MUTUAL_FUND

countryobject

currencystring

exchangeobject

gicsobject

has_newsboolean

isinstring

market_classificationinteger

mnemonicstring

mnemonic_ibesstring

primary_methodstring

priorityinteger

regionobject

searchobject

spxobject

sub_classinteger

overview_disabledboolean | null

tickerstring

ticker_bloombergstring

default_snakestring

connectedobject

popularboolean

company_descriptionstring

logo_urlstring

gatedboolean

american_deposit_receiptboolean

polygon_tickerstring

fx_currencyobject

trading_countryobject

cusipstring

sedolstring

figistring

subscribable_tickerstring

logo_urlsobject

400

Object

Bad request.

---

[← Documentation](../../README.md)
