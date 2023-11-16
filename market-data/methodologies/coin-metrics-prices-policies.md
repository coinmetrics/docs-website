# Coin Metrics Prices Policies

The full text of this document can be downloaded as a pdf document using the link below.&#x20;

{% file src="../../.gitbook/assets/coin-metrics-prices-policies.pdf" %}

## Introduction

Coin Metrics publishes a collection of prices for a set of cryptocurrencies and fiat currencies consisting of the Coin Metrics Reference Rates ("CM Reference Rates") and the Coin Metrics Principal Market Prices ("CM Principal Market Prices"), which are collectively referred to as the Coin Metrics Prices ("CM Prices"). This document describes the policies that are used to govern and administer the CM Prices.

The Coin Metrics Hourly Reference Rates is published once an hour and utilizes volume-weighted median and time-weighted average techniques over a 61-minute calculation window. Common use cases for the Coin Metrics Hourly Reference Rates include research, backtesting, or calculating net asset value for investment funds.

The Coin Metrics Real-Time Reference Rates is published once a second and once every 200 milliseconds and utilizes volume-weighted median and inverse price variance-weighted median techniques. Common use cases for the Coin Metrics Real-Time Reference rates include serving as a data source for on-chain price oracles, risk management, indicative intraday values for investment funds and financial benchmarks, and any use cases where real-time pricing is needed.

The Coin Metrics Principal Market Prices is published once a second and adheres to the guidelines regarding fair value measurement issued by the International Financial Reporting Standards and the Association of International Certified Professional Accountants, specifically standards IFRS 13 and FASB ASC 820. The Coin Metrics Principal Market Prices identifies a principal market for each asset and utilizes the most recent price from this market. Common use cases are for fair value measurement and for preparing financial statements.

The CM Prices are designed to serve as a set of transparent and independent pricing sources that promote the functioning of efficient markets, reduce information asymmetries among market participants, facilitate trading in standardized contracts, and accelerate the adoption of cryptocurrencies as an asset class with the highest standards. The CM Prices are calculated using robust and resilient methodologies that are resistant to manipulation.&#x20;

## Other Documents

The CM Prices are collectively governed by rules-based methodologies described in [Coin Metrics Prices Methodology](https://docs.coinmetrics.io/market-data/methodologies/coin-metrics-prices-methodology) which describes our Market Selection Framework, a systematic method of producing a unique set of constituent markets for each asset, our data sources, calculation algorithm, and contingency rules. &#x20;

## Administration

Coin Metrics serves as the administrator for the CM Prices and has primary responsibility for all aspects of the CM Prices determination process, including the development, definition, determination, dissemination, operation, and governance of the CM Prices. All aspects of the production of the CM Prices are carried out by Coin Metrics, and Coin Metrics does not rely on any third parties for the determination of the CM Prices.

Coin Metrics ensures that transparency regarding significant decisions and associated rationale are published and made available to external stakeholders. Data contingency and data exclusion rules are in place to handle certain extraordinary circumstances and external factors beyond the control of Coin Metrics.&#x20;

## Conflicts of Interest

Coin Metrics enforces policies and procedures relating to conflicts of interest in connection with the production of the CM Prices. The conflicts of interest policy addresses the identification, disclosure, management, and mitigation of conflicts of interest. These policies and procedures are periodically reviewed by the CM Operating Committee. Coin Metrics is committed to disclosing any material conflicts of interest to external stakeholders and to regulatory authorities.

## Recalculations

If errors are discovered in the calculation process subsequent to the publication of a price, a recalculated price may be published. Such errors can include the following events:

1. A constituent market begins trading at a spread against other constituent markets due to a temporary halting of withdrawals or deposits or an increase in solvency risk for a specific exchange
2. A constituent market is temporarily halted due to unplanned exchange maintenance
3. Data from constituent markets is interrupted due to network delays or exchange instability
4. Data from constituent markets is interrupted due to an unplanned change in an exchange’s API
5. Suspected trade manipulation is observed on a constituent market
6. A ticker change or token swap for a constituent market is missed or misapplied
7. Calculation methodology is incorrectly applied

Recalculations to the prices are assessed on a case-by-case basis.  Decisions regarding recalculations take into consideration all the available data and the potential negative impact or disruption involved in a recalculation.&#x20;

## Internal Controls

Coin Metrics has implemented internal controls to protect the integrity of the CM Prices. These controls cover the selection of input data sources, the collection of data from input data sources, and maintaining the integrity of collected data. Staff involved with the production of the CM Prices have been trained in the proper usage of the data and maintain proper segregation of responsibilities. Any exercise of expert judgment or non-standard procedures is subject to dual approval by staff members, and is logged. In addition, Coin Metrics maintains a whistleblowing mechanism to facilitate the reporting of any potential misconduct.

## Complaints

Complaints about the calculation methodologies of the CM Prices or the value of a published price should be submitted in writing to `support@coinmetrics.io`. Coin Metrics will investigate any complaints and respond to the complainant in a fair and timely manner. Any investigation of the complaint will adhere to the following procedures:

1. The personnel receiving and investigating the complaint will be independent of any personnel who may have been involved in the subject of the complaint.
2. All records and documents submitted by the complainant and related to the investigation into the complaint will be retained for a period of at least five years.
3. Any complaint that results in a change in the determination of a price, its calculation methodology, or its policies will be publicly disclosed and will contain an explanation the action taken.

## Record Retention

Coin Metrics retains records, for at least five years, on the following items:

1. All market data that is collected and used in the calculation of the CM Prices
2. Any use of expert judgment in the calculation of the CM Prices
3. Any use of non-standard procedures in the calculation of the CM Prices
4. The identities of staff responsible for the calculation of the CM Prices
5. Any responses, questions, or complaints received in connection with the calculation of the CM Prices

## Compliance

Coin Metrics maintains records and has processes in place to comply with requests for information from regulatory authorities. Coin Metrics commits to full cooperation with any regulatory authority in carrying out their regulatory or supervisory duties.

## Change Log

1. **Version 1.1 on November 8, 2023:**  Changes to Coin Metrics Prices Policies to clarify distinctions between CMBI Single Asset Indexes and CM Prices.
2. **Version 1.0 on March 17, 2023**: Initial publication of the Coin Metrics Prices Policies. Previously, the contents of this document were contained within the Hourly Reference Rate Methodology and Real-Time Reference Rates Methodology documents.
