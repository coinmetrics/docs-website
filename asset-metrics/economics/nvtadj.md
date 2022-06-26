# NVT

## Definition

The ratio of the network value (or market capitalization, current supply) divided by the adjusted transfer value. Also referred to as NVT.

| Name | MetricID | Category  | Subcategory | Type  | Unit          | Interval |
| ---- | -------- | --------- | ----------- | ----- | ------------- | -------- |
| NVT  | NVTAdj   | Valuation | Valuation   | Ratio | Dimensionless | 1 day    |

## Details

* This metric uses the native units network value and adjusted transaction volume. It is therefore available at the asset’s genesis, unlike if it was using USD values.
* It can be thought of as a rough P/E (price to earnings) ratio proxy for crypto assets.
* First conceptualized by Willy Woo (2017) with the introduction of the network value to transactions (NVT) ratio, calculated as a cryptoasset’s market capitalization divided by its daily value transacted over the network. The logic behind the ratio is that value transacted over an asset’s network represents the utility of a cryptoasset. High values of the NVT ratio have detected bubbles and low values have indicated attractive entry points in the past.

## **Release History**

* Released in the 1.0 release of NDP

## Interpretation

NVT has been much discussed; in short, it compares market capitalization to on-chain transactional usage. Blockchains with low usage relative to market cap have a higher NVT. In this sense it can be understood as the opposite of velocity. Due to structural dissimilarities in blockchain usage modes, NVTs among all assets are not directly comparable. Our formulation employs adjusted transaction volume, as we understand this to be a purer measure of the actual usage of the chain.

## See Also

* [NVT 90-day Moving Avg](nvtadj90.md)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/NVTAdj" %}
