# Real-Time Reference Rates Methodology

The full text of this methodology can be downloaded as a pdf document using the link below.&#x20;

{% file src="../../.gitbook/assets/rtrr-methodology (2).pdf" %}

## Introduction

Coin Metrics produces the Coin Metrics Real-Time Reference Rates (the “Real-Time Reference Rates”), a collection of reference rates quoted in U.S. dollars and other currencies, published once per second, for a set of cryptocurrencies and fiat currencies. The Real-Time Reference Rates are designed to serve as a transparent and independent pricing source that promotes the functioning of efficient markets, reduces information asymmetries among market participants, facilitates trading in standardized contracts, and accelerates the adoption of cryptocurrencies as an asset class with the highest standards. The Real-Time Reference Rates are calculated using a robust and resilient methodology that is resistant to manipulation and adheres to international best practices for financial benchmarks, including the International Organization of Securities Commissions’ (IOSCO) Principles for Financial Benchmarks. The Coin Metrics Oversight Committee (the “Oversight Committee”) and an independent governance structure protect the integrity of the Real-Time Reference Rates and ensure the Real-Time Reference Rates serve as a source of transparent and independent pricing.

## Description

The Real-Time Reference Rates are published once per second, every day of the year, and represent the reference rate of one unit of the asset quoted in U.S. dollars or other currency.

## Coverage Universe

The set of assets included in the Real-Time Reference Rates coverage universe are included in Appendix A.

## Data and Calculation Methodology

### Data Sources

The input data source for the Real-Time Reference Rates are markets traded on cryptocurrency exchanges that are approved to serve as pricing sources by the Oversight Committee. The Oversight Committee evaluates markets using a Market Selection Framework that assesses markets along a wide set of criteria to determine if the data source reflects trading activity in a transparent and representative manner. The Oversight Committee evaluates new markets for inclusion as constituent markets and evaluates existing constituent markets using the Market Selection Framework on a quarterly basis or as market conditions warrant. Markets that are approved by the Oversight Committee are added to a list of constituent markets (the “Constituent Markets”). A separate list of Constituent Markets is maintained for each of the Real-Time Reference Rates in the coverage universe.

A candidate market can be nominated for inclusion and an existing constituent market can be nominated for exclusion by any member of the public or member of the Oversight Committee. Public nominations for inclusion or exclusion of a market can be submitted in writing to `support@coinmetrics.io`. The Oversight Committee may convene to apply the Market Selection Framework to evaluate the inclusion or exclusion of a market between regularly-scheduled quarterly meetings if market conditions or circumstances warrant. Coin Metrics publishes a current list of Constituent Markets for each asset in the Real-Time Reference Rates coverage universe, updates on inclusions or exclusions of constituent markets, and the rationale for making any change.

### Market Selection Framework

The Market Selection Framework consists of a fully-systematized process for evaluating markets to serve as input pricing sources for the calculation of the Reference Rates. It produces a unique set of candidate selected markets for each asset in the coverage universe that are then subsequently reviewed by the Oversight Committee. The market selection framework evaluates markets based on the following criteria:

1. _Technology_: An assessment of whether the technology infrastructure of the market’s exchange provides sufficient availability and reliability for input data collection. Evaluates whether the exchange offers a REST API, Websocket feed, or FIX API suitable for data collection. Evaluates the performance of the API in terms of reliability and latency.
2. _Legal and Compliance_: An assessment of whether the market’s exchange complies with laws and regulations. Evaluates the exchange’s legal risk exposure, and whether it adheres to regulatory best practices. Evaluates whether the exchange has publicly-disclosed trading policies, uses market surveillance technology, and complies with national regulatory organizations, and enforces KYC and AML requirements. Evaluates whether the exchange has functioning fiat and cryptocurrency withdrawals processed within a normal timeframe. Evaluates whether a data sharing license can be executed with the exchange.
3. _Business Model_: An assessment of the market’s exchange with respect to its business model, including its fee structure and asset listing standards.
4. _Data Availability_: An assessment of the available data the market’s exchange offers for the given asset, including the number of markets where the given asset is the base currency, whether the markets are quoted in fiat currencies or other cryptocurrencies, and the type of markets offered.
5. _Price_: An assessment of the quality of the market’s price data, including testing for the occurrence of price outliers and impactful price deviations from other markets, and implementing tests that determine whether the market functions as an active market in the underlying asset and are anchored by observable transactions entered into at arm’s length between buyers and sellers.
6. _Volume_: An assessment of the quality of the market’s volume data, including testing for manipulated volume figures, and implementing tests that determine whether the market functions as an active markets in the underlying asset and are anchored by observable transactions entered into at arm’s length between buyers and sellers. The size of the exchange’s markets are also considered.
7. _Order Book_: An assessment of the quality of the market’s order book data, including tests for manipulated orders, and implementing tests that determine whether the market functions as an active market in the underlying asset and are anchored by observable transactions entered into at arm’s length between buyers and sellers. The liquidity of the market is also considered.

The full Market Selection Framework can be found [here](https://docs.coinmetrics.io/methodologies/reference-rates/market-selection-framework).

### Data Inputs

The data inputs for the calculation of the Real-Time Reference Rates are observable transactions in an active market where the given asset is traded. The pool of candidate markets that are evaluated by the Market Selection Framework are determined by a hierarchy of data inputs that varies depending on the given asset.

#### Bitcoin (BTC) and Ethereum (ETH)

The pool of candidate markets that are evaluated for the calculation of the Real-Time Reference Rates for Bitcoin (BTC) and Ethereum (ETH) are determined using the following data hierarchy:

1. The primary data input is observable transactions in an active market where the given cryptocurrency is the base currency and the quote currency is U.S. dollars.
2. Markets where the given cryptocurrency is the base currency and the quote currency is not U.S. dollars are not considered, including markets quoted in other fiat currencies or markets quoted in stablecoins.

#### Other Cryptocurrencies Excluding Stablecoins

The pool of candidate markets that are evaluated for the calculation of the Real-Time Reference Rates for other cryptocurrencies, excluding Bitcoin (BTC), Ethereum (ETH), and stablecoins are determined using the following data hierarchy:

1. The primary data input is observable transactions in an active market where the given cryptocurrency is the base currency and the quote currency is U.S. dollars.
2. If the above data inputs do not exist or the Oversight Committee makes a determination that the above data inputs are insufficient to calculate the reference rate, the universe of data inputs will expand to include observable transactions in an active market where the given cryptocurrency is the base currency and quote currency is Bitcoin (BTC).
3. If the above data inputs do not exist or the Oversight Committee makes a determination that the above data inputs are insufficient to calculate the reference rate, the universe of data inputs will expand to include observable transactions in an active market where the given cryptocurrency is the base currency and quote currency is Ethereum (ETH).
4. If the above data inputs do not exist or the Oversight Committee makes a determination that the above data inputs are insufficient to calculate the reference rate, the universe of data inputs will expand to include observable transactions in an active market where the given cryptocurrency is the base currency and quote currency is USD Coin (USDC).
5. If the above data inputs do not exist or the Oversight Committee makes a determination that the above data inputs are insufficient to calculate the reference rate, the universe of data inputs will expand to include observable transactions in an active market where the given cryptocurrency is the base currency and quote currency is Tether (USDT).

#### Stablecoins

The pool of candidate markets that are evaluated for the calculation of the Real-Time Reference Rates for stablecoins are determined using the following data hierarchy:

1. The primary data input is observable transactions in an active market where the given stablecoin is the base currency and the quote currency is U.S. dollars.
2. If the above data inputs do not exist or the Oversight Committee makes a determination that the above data inputs are insufficient to calculate the reference rate, the universe of data inputs will expand to include observable transactions in an active market where Bitcoin (BTC) is the base currency and quote currency is the given stablecoin.
3. If the above data inputs do not exist or the Oversight Committee makes a determination that the above data inputs are insufficient to calculate the reference rate, the universe of data inputs will expand to include observable transactions in an active market where Ethereum (ETH) is the base currency and quote currency is the given stablecoin.
4. If the above data inputs do not exist or the Oversight Committee makes a determination that the above data inputs are insufficient to calculate the reference rate, the universe of data inputs will expand to include observable transactions in an active market where the given stablecoin is the base currency and quote currency is USD Coin (USDC).
5. If the above data inputs do not exist or the Oversight Committee makes a determination that the above data inputs are insufficient to calculate the reference rate, the universe of data inputs will expand to include observable transactions in an active market where the given stablecoin is the base currency and quote currency is Tether (USDT).

The data hierarchy for stablecoins differs from other cryptocurrencies because market convention sets stablecoins as the quote currency for the majority of active markets. The following assets in the coverage universe are considered to be stablecoins:

| Name           | Ticker |
| -------------- | ------ |
| Tether         | usdt   |
| TrueUSD        | tusd   |
| USD Coin       | usdc   |
| Paxos Standard | pax    |
| Gemini Dollar  | gusd   |
| HUSD           | husd   |
| Binance USD    | busd   |
| Dai            | dai    |
| USDK           | usdk   |
| Binance IDR    | bidr   |
| sUSD           | susd   |
| Neutrino USD   | usdn   |
| TerraUSD       | ust    |
| mStable USD    | musd   |
| USD Paxos      | usdp   |

#### Fiat Currencies

The pool of candidate markets that are evaluated for the calculation of the Reference Rates for fiat currencies are determined using the following data hierarchy:

1. The primary data input is observable transactions in an active market where the given fiat currency is the base currency and the quote currency is U.S. dollars.
2. If the above data inputs do not exist or the Oversight Committee makes a determination that the above data inputs are insufficient to calculate the reference rate, the universe of data inputs will expand to include observable transactions in an active market where Bitcoin (BTC) is the base currency and quote currency is the given fiat currency.
3. If the above data inputs do not exist or the Oversight Committee makes a determination that the above data inputs are insufficient to calculate the reference rate, the universe of data inputs will expand to include observable transactions in an active market where Ethereum (ETH) is the base currency and quote currency is the given fiat currency.

The data hierarchy for fiat currencies differs from other cryptocurrencies because market convention sets fiat currencies as the quote currency for the majority of active markets. The following assets in the coverage universe are considered to be fiat currencies:

| Name              | Ticker |
| ----------------- | ------ |
| Euro              | eur    |
| British Pound     | gbp    |
| Japanese Yen      | jpy    |
| Canadian Dollar   | cad    |
| Korean won        | krw    |
| Russian Ruble     | rub    |
| Ukrainian Hryvnia | uah    |
| Turkish Lira      | try    |
| Australian Dollar | aud    |
| Brazilian Real    | brl    |
| Swiss Franc       | chf    |
| Hong Kong Dollar  | hkd    |
| Nigerian Naira    | ngn    |
| Singapore Dollar  | sgd    |

### Calculation Algorithm

The calculation algorithm of the Real-Time Reference Rates is described below.

1. Calculate the volume denominated in units of the given asset from observable transactions that occurred over the trailing 60 minutes for each of the Constituent Markets. Calculate the volume weight for each of the Constituent Markets by dividing the volume figure for each of the Constituent Markets by the total volume across all Constituent Markets. The resulting figure is referred to as the volume weight.
2. Convert the trade price of all observable transactions over the trailing 60 minutes for each of the Constituent Markets to U.S. dollars if necessary using the Real-Time Reference Rate calculated for Bitcoin (BTC) or Ethereum (ETH). Calculate the inverse variance of the trade price converted to U.S. dollars for each of the Constituent Markets using the population mean in the calculation of variance, where the population mean is defined as the mean price of all trades from Constituent Markets over the trailing 60 minutes. If a Constituent Market has an infinite or undefined inverse price variance, the inverse price variance for that Constituent Market is set to zero. Calculate the inverse price variance weight for each of the Constituent Markets by dividing the inverse price variance by the total inverse price variance across all Constituent Markets. The resulting figure is referred to as the inverse price variance weight.
3. Calculate the final weight for each of the Constituent Markets by taking a mean of the volume weight and the inverse price variance weight.
4. Extract the most recent observable transaction from each of the Constituent Markets. Convert the trade price of the most recent observable transactions to U.S. dollars if necessary using the Real-Time Reference Rate calculated for Bitcoin (BTC) or Ethereum (ETH).
5. Calculate the weighted median price of the most recent observable transactions using the price calculated in step 4 and the final weight calculated in step 3. The weighted median price is calculated by ordering the transactions from lowest to highest price, and identifying the price associated with the trades at the 50th percentile of final weight. The resulting figure is the Real-Time Reference Rate for the given asset.

### Data Contingency Rules

The following contingency rules are followed to address situations where data is delayed, missing, or unavailable due to periods of illiquidity, extraordinary market circumstances, or outside factors beyond the control of Coin Metrics.

1. If observable transactions from a constituent market are unable to be collected due to technical problems specific to the constituent market’s exchange during the calculation of a real-time reference rate, the observable transactions from the constituent market are not included in the calculation of the specific instance of the given real-time reference rate.
2. If no observable transactions from constituent markets exist during the trailing 60 minutes, the value of the real-time reference rate will be determined to equal the value calculated during the previous second.

### Data Exclusion Rules

All observable transactions from constituent markets are evaluated using a systematic data quality control process. If potential errors or anomalies in the data are detected, the exercise of expert judgment will be applied to determine if the potentially erroneous data is included in the calculation of the real-time reference rate. The exercise of expert judgment in this circumstance is used to determine if the potentially erroneous data reflects observable transactions that are entered into at arm’s length between buyers and sellers and constitute an active market in the underlying asset, whether the observable transactions in question are formed by the competitive forces of supply and demand, and whether the observable transactions in question are a credible indicator of executable prices in the underlying asset. An investigation into the causes of the potential error, including whether any price deviations are specific to the exchange itself, is conducted. Any exercise of expert judgment is subject to dual approval by staff members, and is logged and reported to the Oversight Committee which periodically reviews the application of expert judgment to ensure consistency.

## Recalculations

If errors are discovered in the calculation process subsequent to the publication of the real-time reference rate, a recalculated real-time reference rate may be published. Such errors can include the following events:

1. A constituent market begins trading at a spread against other constituent markets due to a temporary halting of withdrawals or deposits or an increase in solvency risk for a specific exchange
2. A constituent market is temporarily halted due to unplanned exchange maintenance
3. Data from constituent markets is interrupted due to network delays or instability
4. Data from constituent markets is interrupted due to an unplanned change in an exchange’s API
5. Suspected trade manipulation is observed on a constituent market
6. A ticker change or token swap for a constituent market is missed or misapplied
7. Calculation methodology is incorrectly applied

Recalculations to the real-time reference rates are assessed on a case-by-case basis in consultation with the Oversight Committee. Decisions regarding recalculations take into consideration all the available data and the potential negative impact or disruption involved in a recalculation. All recalculations are announced simultaneously to all clients.

## Administration

Coin Metrics serves as the administrator for the Real-Time Reference Rates and has primary responsibility for all aspects of the Real-Time Reference Rates determination process, including the development, definition, determination, dissemination, operation, and governance of the Real-Time Reference Rates. All aspects of the production of the Real-Time Reference Rates are carried out by Coin Metrics, and Coin Metrics does not rely on any third parties for the determination of the Real-Time Reference Rates.

Coin Metrics ensures that transparency regarding significant decisions and associated rationale are published and made available to external stakeholders. Data contingency and data exclusion rules are in place to handle certain extraordinary circumstances and external factors beyond the control of Coin Metrics. The Oversight Committee reviews and provides challenge on the Real-Time Reference Rates production process.

## Internal Oversight

The Oversight Committee provides independent oversight over the production of the Real-Time Reference Rates. The Oversight Committee’s responsibilities include regular reviews of the Real-Time Reference Rate production process, the Real-Time Reference Rate definition and calculation methodology, the selection of data sources and data inputs, any uses of expert judgment or non-standard procedures, conflicts of interest, material changes to or termination of the Real-Time Reference Rates, reviewing the results of external and internal audits, and any complaints or questions regarding the Real-Time Reference Rates from external stakeholders. Additional information regarding the responsibilities and membership of the Oversight Committee can be found in the Coin Metrics Oversight Committee Charter document.

## Conflicts of Interest

Coin Metrics enforces policies and procedures relating to conflicts of interest in connection with the production of the Real-Time Reference Rates. The conflicts of interest policy addresses the identification, disclosure, management, and mitigation of conflicts of interest. These policies and procedures are periodically reviewed by the Oversight Committee. Coin Metrics is committed to disclosing any material conflicts of interest to external stakeholders and to regulatory authorities.

## Material Changes or Termination

Coin Metrics may initiate material changes to or terminate a real-time reference rate due to certain extraordinary market circumstances or external factors. These circumstances or external factors include, but are not limited to:

1. The real-time reference rate no longer serves, and could not be modified to serve, as a transparent and independent pricing source for the underlying asset
2. The market liquidity in the underlying asset declines to an extent that the input data sources no longer function as active markets
3. The underlying asset experiences a contentious hard fork in which both forks survive

In such circumstances, Coin Metrics will review the Real-Time Reference Rates to ensure the Real-Time Reference Rates are properly reflecting their underlying assets, and if necessary, make changes to the methodology or definition of the Real-Time Reference Rates to properly account for changing market structure, circumstances, and industry conventions in the underlying asset. Any such change or termination will be reviewed and approved by the Oversight Committee. Any approved change or termination will be publicly disclosed to external stakeholders with a detailed explanation of the rationale. In a manner appropriate to the circumstances, Coin Metrics will develop a plan to notify, solicit comments from, and consult with external stakeholders before implementing any material change or termination. Any change or termination will include a timeline explaining the timing of changes or termination and include steps to mitigate any negative effects on external stakeholders.

## Internal Controls

Coin Metrics has implemented internal controls to protect the integrity of the Real-Time Reference Rates. These controls cover the selection of input data sources, the collection of data from input data sources, and maintaining the integrity of collected data. Staff involved with the production of the Real-Time Reference Rates have been trained in the proper usage of the data and maintain proper segregation of responsibilities. Any exercise of expert judgment or non-standard procedures is subject to dual approval by staff members, and is logged and reported to the Oversight Committee which periodically reviews any incidents. In addition, Coin Metrics maintains a whistleblowing mechanism to facilitate the reporting of any potential misconduct.

## Complaints

Complaints about the calculation methodology of the Real-Time Reference Rates or the value of a published real-time reference rate should be submitted in writing to `support@coinmetrics.io`. Coin Metrics will investigate any complaints and respond to the complainant in a fair and timely manner. Any investigation of the complaint will adhere to the following procedures:

1. The personnel receiving and investigating the complaint will be independent of any personnel who may have been involved in the subject of the complaint.
2. All records and documents submitted by the complainant and related to the investigation into the complaint will be retained for a period of at least five years and submitted to the Oversight Committee for review.
3. Any complaint that results in a change in the determination of the Real-Time Reference Rates, its calculation methodology, or its policies will be publicly disclosed and will explain the action taken.

## Internal Audit

The Oversight Committee appoints an independent internal auditor to review the Real-Time Reference Rates’ adherence to its stated methodology, compliance with policies, and adherence to the IOSCO’s Principles of Financial Benchmarks. The frequency of the independent internal audit is once annually.

## Record Retention

Coin Metrics retains records, for at least five years, on the following items:

1. All market data that is collected and used in the calculation of the Real-Time Reference Rates
2. Any use of expert judgment in the calculation of the Real-Time Reference Rates
3. Any use of non-standard procedures in the calculation of the Real-Time Reference Rates
4. The identities of staff responsible for the calculation of the Real-Time Reference Rates
5. Any responses, questions, or complaints received in connection with the calculation of the Real-Time Reference Rates

## Compliance

Coin Metrics maintains records and has processes in place to comply with requests for information from regulatory authorities. Coin Metrics commits to full cooperation with any regulatory authority in carrying out their regulatory or supervisory duties.

## Change Log

1. **Version 0.13 on July 1, 2022**: The coverage universe is expanded to include the following assets: `fei`, `op`, `usdd`, `xch`, `gmt`, `bico`, `ctk`, `flm`, `sfp`, `starl`, `glmr`, `tulip`, `astro`, `sfi`, `gst`, `mob`, `bit`, `vgx`, `auction`, `pundix`, `stg`, `ata`, `bel`, `dar`, `gal`, `astr`, `cqt`, `cspr`, `metis`, `boba`, `twt`, `aca`, `dao`, `xprt`, `cube`. The publication of reference rates is terminated for the following assets: `gxs`, `dgtx`, `wluna`, `dgd`, `foam`, `csp`, `cnn`, `bft`.
2. **Version 0.12 on February 15, 2022**: The coverage universe is expanded to include the following assets: `xec`, `kda`, `mina`, `xdc`, `elon`, `flux`, `movr`, `ceek`, `win_wink`, `dvi`, `dusk`, `asd`, `gala`, `spell`, `ens`, `tru`, `alcx`, `clv`, `imx`, `agld`, `jasmy`, `farm`, `alice`, `chr`, `dydx`, `tlm`, `mdt`, `gtc`, `sun`, `c98`, `people`, `lina`, `rndr`, `ach`, `super`, `mask`, `quick`, `arpa`, `qi`, `idex`, `rad`, `bond`, `mir`, `joe`, `gods`, `front`, `pla`, `orn`, `ramp`, `rgt`, `fida`, `forth`, `tribe`, `wluna`, `coval`, `rbn`, `lcx`, `asm`, `ddx`, `suku`, `krl`, `rari`, `mco2`, `gyen`, `btrst`, `api3`, `rly`, `wcfg`, `musd`, `ilv`, `atlas`, `usdp`, `joe`, `ldo`, `cvx`, `fxs`, `kp3r`, `alpaca`, `bnx`, `boson`, `dora`, `ghst`, `nft`, `ohm`, `om`, `pond`, `rare`, `revv`, `stpt`, `torn`, `tvk`, `wncg`, `xym`, `ygg`. The publication of reference rates is terminated for the following assets: `hedg`, `eurs`, `bzrx`, `poa`, `wpr`, `dmg`, `cdt`, `phx`, `appc`, `btt`, `idrt`, `rdn`, `via`, `evx`. The section “Data Inputs”, subsections “Other Cryptocurrencies Excluding Stablecoins” and “Stablecoins”, was modified to consider markets quoted in USD Coin or Tether to serve as constituent markets. The constituent markets for all assets in the coverage universe are updated.
3. **Version 0.11 on September 28, 2021**: The coverage universe is expanded to include the following assets: `amp`, `axs`, `shib`, `audio`, `bake`, `med`, `dag`, `slp`, `xdb`. The publication of reference rates is terminated for the following assets: `agi` ,`btmx`, `dgx`, `ethos`, `mco`, `sngls`, `cpay`, `eng`, `lun`, `pnt`. The constituent markets for all assets in the coverage universe are updated.
4. **Version 0.10 on May 27, 2021**: The coverage universe is expanded to include the following assets: `icp`, `cope`, `maps`, `btcst`, `ctsi`, `erg`, `woo`, `prom`, `strax`, `usdn`, `cfx`, `mdx`, `nkn`, `sand`, `fx`, `pha`. The publication of reference rates is terminated for the following assets: `tnt`, `npxs`, `zar`. The constituent markets for all assets in the coverage universe are updated.
5. **Version 0.9 on April 25, 2021**: The methodology was modified to add fiat currencies to the coverage universe. The coverage universe is expanded to include the following assets: `eur`, `krw`, `gbp`, `jpy`, `aud`, `try`, `brl`, `rub`, `sgd`, `bidr`, `ngn`, `cad`, `chf`, `zar`, `idrt`, `hkd`, `uah`, `qc`, `klay`, `cake`, `btmx`, `flow`, `zks`, `stmx`, `skl`, `reef`, `dodo`, `coti`, `bora`, `cream`, `ray`, `tryb`, `rook`. The publication of reference rates is terminated for the following assets: `xzc`, `bcpt`, `yamv2`, `xns`, `tmtg`, `kp3r`.
6. **Version 0.8 on February 23, 2021**: The coverage universe is expanded to include the following assets: `1inch`, `alpha`, `octo`, `perp`, `scrt`, `grt`, `keep`, `xvs`, `nu`, `tel`, `badger`.
7. **Version 0.7 on January 26, 2021**: The coverage universe is expanded to include the following assets: `susd`, `pols`, `ust`, `lto`, `swap`, `nim,` `lbc`, `mta`, `kp3r`, `glm`, `near`, `noia`, `rose`, `inj`. The publication of reference rates is terminated for the following assets: `gnt`, `fxc`, `bht`, `cmct`, `strat`, `loki`. The constituent markets for all assets in the coverage universe are updated.
8. **Version 0.6 on October 14, 2020**: The coverage universe is expanded to include the following assets: `akro`, `ampl`, `ar`, `bal`, `bzrx`, `celo`, `comp`, `crv`, `csp`, `dmg`, `dot`, `foam`, `kin`, `oxt`, `rune`, `sol`, `srm`, `vtho`, `wbtc`, `wnxm`, `xhv`, `xyo`, `yamv2`, `yfi`, `yfii`, `uma`, `ewt`, `rev`, `rsr`, `avax`, `tmtg`, `jst`, `hnt`, `trac`, `vlx`, `mxc`, `fet`, `aoa`, `iris`, `pnk`, `mln`, `shr`, `uqc`, `one_harmony`, `trb`, `ogn`, `ava`, `loki`, `hxro`, `wxt`, `cpay`, `fil`, `uni`, `swrv`, `sushi`, `aave`, `egld`, `hns`, `dia`, `boa`, `uos`, `ctc`, `renbtc`. The publication of reference rates is terminated for the following assets: `arn`, `pma`, `erd`, `man`, `iq`, `lend`. The Market Selection Framework was amended such that extremely low volume markets are less likely to be selected as a constituent market if higher volume markets of similar quality are available. The constituent markets for all assets in the coverage universe are updated.
9. **Version 0.5 on July 29, 2020**: The coverage universe is expanded to include the following assets: `wrx`, `band`, `ksm`, `usdk`, `snx`, `stx`, `fxc`, `kcs`, `hive`, `nrg`, `cel`, `ubt`, `chsb`, `crpt`, `bht`, `cvt`, `data`, `eurs`, `xns`, `gt`, `dgtx`, `kava`, `tt`, `sxp`, `mx`, `ocean`, `erd`, `lpt`. The publication of reference rates is terminated for the following assets: `storm`, `gto`. A revision policy was amended. The constituent markets for all assets in the coverage universe are updated.
10. **Version 0.4 on February 27, 2020**: The coverage universe is expanded to include the following assets: `xaut`, `paxg`, `husd`, `dgx`, `busd`, `ftt`, `hedg`, `okb`, `zb`, `hbar`, `ckb`, `mof`, `vsys`, `cennz`, `luna`, `chz`, `seele`, `dx`, `matic`, `abbc`, `rif`, `tomo`, `hpt`, and `ant`.
11. **Version 0.3 on February 6, 2020**: The constituent markets for all assets in the coverage universe are updated. The coverage universe is adjusted to remove the following assets: `box`, `cosm`, `fsn`, `medx`, `pst`, and `ttc_protocol`. The coverage universe was expanded to include Dai and the previous asset with this name was renamed to Sai to appropriately reflect MakerDAO’s transition from Single-Collateral Dai (Sai) to Multi-Collateral Dai (Dai).
12. **Version 0.2 on December 9, 2019**: Updated calculation methodology to include price inverse variance weighting to reduce the impact of outliers. The coverage universe is expanded to include the following assets: `algo` and `beam`.
13. **Version 0.1 on August 30, 2019**: Initial publication of Real-Time Reference Rates Methodology.

## Appendix A

The following table lists the current coverage universe:

| Name                                 | Ticker                  |
| ------------------------------------ | ----------------------- |
| Bitcoin                              | btc                     |
| Bitcoin Cash                         | bch                     |
| Litecoin                             | ltc                     |
| Euro                                 | eur                     |
| XRP                                  | xrp                     |
| Ethereum                             | eth                     |
| Ethereum Classic                     | etc                     |
| British Pound                        | gbp                     |
| Zcash                                | zec                     |
| Monero                               | xmr                     |
| Dash                                 | dash                    |
| Japanese Yen                         | jpy                     |
| IOTA                                 | miota                   |
| EOS                                  | eos                     |
| OMG Network                          | omg                     |
| Neo                                  | neo                     |
| Metaverse ETP                        | etp                     |
| Qtum                                 | qtum                    |
| Aventus                              | avt                     |
| Bitcoin Gold                         | btg                     |
| Streamr                              | data                    |
| QASH                                 | qash                    |
| Status                               | snt                     |
| Basic Attention Token                | bat                     |
| Decentraland                         | mana                    |
| FUNToken                             | fun                     |
| 0x                                   | zrx                     |
| Time New Bank                        | tnb                     |
| TRON                                 | trx                     |
| iExec RLC                            | rlc                     |
| Augur                                | rep                     |
| aelf                                 | elf                     |
| IOST                                 | iost                    |
| Aion                                 | aion                    |
| Request                              | req                     |
| Loopring                             | lrc                     |
| WAX                                  | waxp                    |
| Aragon                               | ant                     |
| Mithril                              | mith                    |
| Storj                                | storj                   |
| Stellar                              | xlm                     |
| Verge                                | xvg                     |
| Lympo                                | lym                     |
| Maker                                | mkr                     |
| VeChain                              | vet                     |
| Kyber Network Crystal                | knc                     |
| Utrust                               | utk                     |
| Ripio Credit Network                 | rcn\_ripiocreditnetwork |
| Polymath                             | poly                    |
| Nucleus Vision                       | ncash                   |
| Cortex                               | ctxc                    |
| Project Pai                          | pai                     |
| DATA                                 | dta                     |
| Zilliqa                              | zil                     |
| Bancor                               | bnt                     |
| MonaCoin                             | mona                    |
| NEM                                  | xem                     |
| Binance Coin                         | bnb                     |
| Gas                                  | gas                     |
| Tether                               | usdt                    |
| OAX                                  | oax                     |
| district0x                           | dnt                     |
| Waltonchain                          | wtc                     |
| Chainlink                            | link                    |
| Moeda Loyalty Points                 | mda                     |
| Metal                                | mtl\_metal              |
| AirSwap                              | ast                     |
| Viberate                             | vib                     |
| Power Ledger                         | powr                    |
| Ark                                  | ark                     |
| Enjin Coin                           | enj                     |
| Komodo                               | kmd                     |
| NULS                                 | nuls                    |
| Ambrosus                             | amb                     |
| Quantstamp                           | qsp                     |
| BitShares                            | bts                     |
| Lisk                                 | lsk                     |
| Bitcoin Diamond                      | bcd                     |
| AdEx                                 | adx                     |
| Cardano                              | ada                     |
| Populous                             | ppt                     |
| CyberMiles                           | cmt                     |
| Waves                                | waves                   |
| ICON                                 | icx                     |
| PIVX                                 | pivx                    |
| OST                                  | ost                     |
| Navcoin                              | nav                     |
| ChatCoin                             | chat                    |
| Civic                                | cvc                     |
| Steem                                | steem                   |
| Nano                                 | nano                    |
| Bluzelle                             | blz                     |
| Aeternity                            | ae                      |
| Ontology                             | ont                     |
| Wanchain                             | wan                     |
| Syscoin                              | sys                     |
| Ardor                                | ardr                    |
| Groestlcoin                          | grs                     |
| Holo                                 | hot\_holo               |
| Loom Network                         | loom                    |
| Bytecoin                             | bcn                     |
| TrueUSD                              | tusd                    |
| Horizen                              | zen                     |
| THETA                                | theta                   |
| IoTeX                                | iotx                    |
| QuarkChain                           | qkc                     |
| Selfkey                              | key                     |
| Hifi Finance                         | mft                     |
| Siacoin                              | sc                      |
| Nebulas                              | nas                     |
| Dent                                 | dent                    |
| Dock                                 | dock                    |
| Gnosis                               | gno                     |
| Canadian Dollar                      | cad                     |
| Enzyme                               | mln                     |
| Dogecoin                             | doge                    |
| Bytom                                | btm                     |
| BitKan                               | kan                     |
| Arcblock                             | abt                     |
| CyberVein                            | cvt                     |
| Decred                               | dcr                     |
| DigiByte                             | dgb                     |
| IoT Chain                            | itc                     |
| Cred                                 | lba                     |
| Measurable Data Token                | mdt                     |
| Molecular Future                     | mof                     |
| TenX                                 | pay                     |
| Revain                               | rev                     |
| Ren                                  | ren                     |
| Nxt                                  | nxt                     |
| Odyssey                              | ocn                     |
| Huobi Token                          | ht                      |
| Elastos                              | ela                     |
| WaykiChain                           | wicc                    |
| SIRIN LABS Token                     | srn                     |
| DeepBrain Chain                      | dbc                     |
| Propy                                | pro                     |
| Bibox Token                          | bix                     |
| HyperCash                            | hc\_hypercash           |
| MaidSafeCoin                         | maid                    |
| Amp                                  | amp                     |
| Pluton                               | plu                     |
| Tezos                                | xtz                     |
| Stacks                               | stx                     |
| Ignis                                | ignis                   |
| PolySwarm                            | nct                     |
| Kin                                  | kin                     |
| SwissBorg                            | chsb                    |
| Centrality                           | cennz                   |
| OriginTrail                          | trac                    |
| Nexo                                 | nexo                    |
| Telcoin                              | tel                     |
| Crypterium                           | crpt                    |
| IHT Real Estate Protocol             | iht                     |
| VeThor Token                         | vtho                    |
| DxChain Token                        | dx                      |
| CEEK VR                              | ceek                    |
| UNUS SED LEO                         | leo                     |
| Factom                               | fct                     |
| Vertcoin                             | vtc                     |
| Game.com                             | gtc\_gamecom            |
| MediBloc                             | med                     |
| Creditcoin                           | ctc                     |
| NKN                                  | nkn                     |
| Uquid Coin                           | uqc                     |
| Korean won                           | krw                     |
| Ravencoin                            | rvn                     |
| LBRY Credits                         | lbc                     |
| ReddCoin                             | rdd                     |
| Numeraire                            | nmr                     |
| Russian Ruble                        | rub                     |
| Ukrainian Hryvnia                    | uah                     |
| Turkish Lira                         | try                     |
| Aurora                               | aoa                     |
| Australian Dollar                    | aud                     |
| Brazilian Real                       | brl                     |
| Swiss Franc                          | chf                     |
| Ethernity                            | ern                     |
| Hong Kong Dollar                     | hkd                     |
| Singapore Dollar                     | sgd                     |
| OpenDAO                              | sos                     |
| Dragonchain                          | drgn                    |
| Kleros                               | pnk                     |
| USD Coin                             | usdc                    |
| KuCoin Token                         | kcs                     |
| Paxos Standard                       | pax                     |
| Gemini Dollar                        | gusd                    |
| Constellation                        | dag                     |
| Nimiq                                | nim                     |
| GoChain                              | go                      |
| Electroneum                          | etn                     |
| Bitcoin SV                           | bsv                     |
| ZB Token                             | zb                      |
| Qcash                                | qc                      |
| MXC                                  | mxc                     |
| TomoChain                            | tomo                    |
| Livepeer                             | lpt                     |
| RIF Token                            | rif                     |
| v.systems                            | vsys                    |
| Grin                                 | grin                    |
| Seele                                | seele                   |
| HUSD                                 | husd                    |
| Lambda                               | lamb                    |
| Huobi Pool Token                     | hpt                     |
| Dora Factory                         | dora                    |
| Beam                                 | beam                    |
| Unibright                            | ubt                     |
| FTX Token                            | ftt                     |
| Kryll                                | krl                     |
| Fetch.ai                             | fet                     |
| Ontology Gas                         | ong\_ontologygas        |
| Ankr                                 | ankr                    |
| Metadium                             | meta                    |
| Haven Protocol                       | xhv                     |
| Quant                                | qnt                     |
| SOLVE                                | solve                   |
| Aergo                                | aergo                   |
| Circuits of Value                    | coval                   |
| Chronos                              | cro                     |
| Hxro                                 | hxro                    |
| Cosmos                               | atom                    |
| Orbs                                 | orbs                    |
| Theta Fuel                           | tfuel                   |
| BORA                                 | bora                    |
| Function X                           | fx                      |
| IRISnet                              | iris                    |
| Celer Network                        | celr                    |
| ABBC Coin                            | abbc                    |
| Wrapped Bitcoin                      | wbtc                    |
| Polygon                              | matic                   |
| Fantom                               | ftm                     |
| Algorand                             | algo                    |
| Dusk Network                         | dusk                    |
| XYO                                  | xyo                     |
| Ocean Protocol                       | ocean                   |
| Celsius                              | cel                     |
| Synthetix                            | snx                     |
| Thunder Token                        | tt                      |
| Reserve Rights                       | rsr                     |
| Standard Tokenization Protocol       | stpt                    |
| Harmony                              | one\_harmony            |
| ARPA Chain                           | arpa                    |
| WINk                                 | win\_wink               |
| Binance USD                          | busd                    |
| Dai                                  | dai                     |
| Tether Gold                          | xaut                    |
| PAX Gold                             | paxg                    |
| OKB                                  | okb                     |
| Hedera Hashgraph                     | hbar                    |
| Nervos Network                       | ckb                     |
| Swipe                                | sxp                     |
| Terra                                | luna                    |
| Chiliz                               | chz                     |
| Orchid                               | oxt                     |
| LCX                                  | lcx                     |
| USDK                                 | usdk                    |
| WazirX                               | wrx                     |
| Band Protocol                        | band                    |
| Kusama                               | ksm                     |
| Hive                                 | hive                    |
| Energi                               | nrg                     |
| GateToken                            | gt                      |
| Kava                                 | kava                    |
| MX Token                             | mx                      |
| Arweave                              | ar                      |
| Compound                             | comp                    |
| NuCypher                             | nu                      |
| Keep Network                         | keep                    |
| Origin Protocol                      | ogn                     |
| Render Token                         | rndr                    |
| LTO Network                          | lto                     |
| COTI                                 | coti                    |
| Solana                               | sol                     |
| Cartesi                              | ctsi                    |
| Chromia                              | chr                     |
| StormX                               | stmx                    |
| Binance IDR                          | bidr                    |
| Polkadot                             | dot                     |
| Celo                                 | celo                    |
| Filecoin                             | fil                     |
| sUSD                                 | susd                    |
| Travala.com                          | ava                     |
| Wirex Token                          | wxt                     |
| Syntropy                             | noia                    |
| Akropolis                            | akro                    |
| Ampleforth                           | ampl                    |
| DigitalBits                          | xdb                     |
| Neutrino USD                         | usdn                    |
| Energy Web Token                     | ewt                     |
| yearn.finance                        | yfi                     |
| UMA                                  | uma                     |
| renBTC                               | renbtc                  |
| Avalanche                            | avax                    |
| BOSAGORA                             | boa                     |
| JUST                                 | jst                     |
| DIA                                  | dia                     |
| Green Satoshi Token                  | gst                     |
| Helium                               | hnt                     |
| IDEX                                 | idex                    |
| Kadena                               | kda                     |
| Klaytn                               | klay                    |
| mStable Governance Token: Meta (MTA) | mta                     |
| MANTRA DAO                           | om                      |
| Orion Protocol                       | orn                     |
| Prometeus                            | prom                    |
| THORChain                            | rune                    |
| ShareToken                           | shr                     |
| Serum                                | srm                     |
| SUKU                                 | suku                    |
| Tellor                               | trb                     |
| BiLira                               | tryb                    |
| Curve DAO Token                      | crv                     |
| Velas                                | vlx                     |
| Wrapped NXM                          | wnxm                    |
| DFI.Money                            | yfii                    |
| Balancer                             | bal                     |
| SushiSwap                            | sushi                   |
| Swerve                               | swrv                    |
| Cream Finance                        | cream                   |
| SUN                                  | sun                     |
| Elrond                               | egld                    |
| Uniswap                              | uni                     |
| Alchemy Pay                          | ach                     |
| Bella Protocol                       | bel                     |
| Frontier                             | front                   |
| TrustSwap                            | swap                    |
| TerraUSD                             | ust                     |
| Handshake                            | hns                     |
| Ultra                                | uos                     |
| BakeryToken                          | bake                    |
| Aavegotchi                           | ghst                    |
| Rarible                              | rari                    |
| Aave                                 | aave                    |
| PancakeSwap                          | cake                    |
| DODO                                 | dodo                    |
| Harvest Finance                      | farm                    |
| Polkastarter                         | pols                    |
| Secret                               | scrt                    |
| Venus                                | xvs                     |
| Ergo                                 | erg                     |
| NEAR Protocol                        | near                    |
| RAMP                                 | ramp                    |
| Audius                               | audio                   |
| Axie Infinity                        | axs                     |
| Conflux                              | cfx                     |
| Shentu                               | ctk                     |
| Injective Protocol                   | inj                     |
| Keep3rV1                             | kp3r                    |
| mStable USD                          | musd                    |
| Smooth Love Potion                   | slp                     |
| Flamingo                             | flm                     |
| Oasis Network                        | rose                    |
| TrueFi                               | tru                     |
| Unifi Protocol DAO                   | unfi                    |
| Golem                                | glm                     |
| API3                                 | api3                    |
| Badger DAO                           | badger                  |
| MobileCoin                           | mob                     |
| Synapse                              | syn                     |
| Terra Virtua Kolect                  | tvk                     |
| The Graph                            | grt                     |
| 1inch                                | 1inch                   |
| Alpha Finance Lab                    | alpha                   |
| OctoFi                               | octo                    |
| saffron.finance                      | sfi                     |
| Perpetual Protocol                   | perp                    |
| BarnBridge                           | bond                    |
| Bonfida                              | fida                    |
| Frax Share                           | fxs                     |
| Linear                               | lina                    |
| Mdex                                 | mdx                     |
| Mirror Protocol                      | mir                     |
| Marlin                               | pond                    |
| REVV                                 | revv                    |
| KeeperDAO                            | rook                    |
| Trust Wallet Token                   | twt                     |
| ZKSwap                               | zks                     |
| Flow                                 | flow                    |
| Stratis                              | strax                   |
| Reef                                 | reef                    |
| Bitcoin Standard Hashrate Token      | btcst                   |
| The Sandbox                          | sand                    |
| SafePal                              | sfp                     |
| SKALE Network                        | skl                     |
| Phala Network                        | pha                     |
| WOO Network                          | woo                     |
| Raydium                              | ray                     |
| Alchemix                             | alcx                    |
| DAO Maker                            | dao                     |
| DerivaDAO                            | ddx                     |
| Inverse Finance                      | inv                     |
| MAPS                                 | maps                    |
| Mask Network                         | mask                    |
| BENQI                                | qi                      |
| Radicle                              | rad                     |
| Rally                                | rly                     |
| SuperFarm                            | super                   |
| Tornado Cash                         | torn                    |
| AIOZ Network                         | aioz                    |
| Alpaca Finance                       | alpaca                  |
| Anchor Protocol                      | anc                     |
| Boson Protocol                       | boson                   |
| Cope                                 | cope                    |
| Fei USD                              | fei                     |
| Flux                                 | flux                    |
| Project Galaxy                       | gal                     |
| Illuvium                             | ilv                     |
| Jasmy                                | jasmy                   |
| Alien Worlds                         | tlm                     |
| Tribe                                | tribe                   |
| Symbol                               | xym                     |
| Internet Computer                    | icp                     |
| Shiba Inu                            | shib                    |
| Somnium Space Cubes                  | cube                    |
| Dogelon Mars                         | elon                    |
| Ampleforth Governance Token          | forth                   |
| Gitcoin                              | gtc                     |
| Liquity                              | lqty                    |
| APENFT                               | nft                     |
| QuickSwap                            | quick                   |
| Rari Governance Token                | rgt                     |
| Persistence                          | xprt                    |
| Lido DAO                             | ldo                     |
| BitDAO                               | bit                     |
| Coin98                               | c98                     |
| Clover Finance                       | clv                     |
| Covalent                             | cqt                     |
| Convex Finance                       | cvx                     |
| Dvision Network                      | dvi                     |
| Gala                                 | gala                    |
| Goldfinch                            | gfi                     |
| Moonriver                            | movr                    |
| PlayDapp                             | pla                     |
| SuperRare                            | rare                    |
| StarLink                             | starl                   |
| Wrapped NCG                          | wncg                    |
| eCash                                | xec                     |
| Yield Guild Games                    | ygg                     |
| USD Paxos                            | usdp                    |
| My Neighbor Alice                    | alice                   |
| ASD                                  | asd                     |
| XDC Network                          | xdc                     |
| Mina                                 | mina                    |
| Adventure Gold                       | agld                    |
| dYdX                                 | dydx                    |
| Spell Token                          | spell                   |
| Assemble Protocol                    | asm                     |
| AstroSwap                            | astro                   |
| Star Atlas                           | atlas                   |
| BinaryX                              | bnx                     |
| Braintrust                           | btrst                   |
| Gods Unchained                       | gods                    |
| Highstreet                           | high                    |
| JOE                                  | joe                     |
| Moss Carbon Credit                   | mco2                    |
| Marinade Staked SOL                  | msol                    |
| Olympus                              | ohm                     |
| Orca                                 | orca                    |
| Ribbon Finance                       | rbn                     |
| Samoyedcoin                          | samo                    |
| Saber                                | sbr                     |
| Wrapped Centrifuge                   | wcfg                    |
| Mines of Dalarnia                    | dar                     |
| Ethereum Name Service                | ens                     |
| GYEN                                 | gyen                    |
| Immutable X                          | imx                     |
| Boba Network                         | boba                    |
| Maple                                | mpl                     |
| ConstitutionDAO                      | people                  |
| Casper                               | cspr                    |
| Automata Network                     | ata                     |
| ApeCoin                              | ape                     |
| LooksRare                            | looks                   |
| Moonbeam                             | glmr                    |
| Tulip Protocol                       | tulip                   |
| STEPN                                | gmt                     |
| Biconomy                             | bico                    |
| Astar                                | astr                    |
| Optimism                             | op                      |
| Stargate Finance                     | stg                     |
| Acala                                | aca                     |
| Bounce Finance Governance Token      | auction                 |
| MetisDAO                             | metis                   |
| Pundix X                             | pundix                  |
| Voyager Token                        | vgx                     |
| USDD                                 | usdd                    |
| Chia                                 | xch                     |
