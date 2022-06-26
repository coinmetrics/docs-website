# Free Float NVT

## Definition

The ratio of the free float network value (or market capitalization, free float) divided by the adjusted transfer value. Also referred to as FFNVT.



| Name           | MetricID | Category  | Subcategory | Type  | Unit          | Interval |
| -------------- | -------- | --------- | ----------- | ----- | ------------- | -------- |
| Free Float NVT | NVTAdjFF | Valuation | Valuation   | Ratio | Dimensionless | 1 day    |

## Details

* This metric provides an important adjustment to the Network Value to Transaction (NVT) Ratio using Free Float Supply (SplyFF)
* For more details on the significance of this improvement, please refer to the following [blog post](https://coinmetrics.io/introducing-free-float-supply/).
* This metric uses the native units network value and adjusted transaction volume. It is therefore available at the asset’s genesis, unlike if it was using USD values.
* It can be thought of as a rough P/E (price to earnings) ratio proxy for crypto assets.
* NVT was first conceptualized by Willy Woo (2017) with the introduction of the network value to transactions (NVT) ratio, calculated as a cryptoasset’s market capitalization divided by its daily value transacted over the network. The logic behind the ratio is that value transacted over an asset’s network represents the utility of a cryptoasset. High values of the NVT ratio have detected bubbles and low values have indicated attractive entry points in the past.

## **Release History**

* Release Version: NDP-EOD 4.8 (Nov, 2020)

## Interpretation

NVT has been much discussed; in short, it compares market capitalization to on-chain transactional usage. Blockchains with low usage relative to market cap have a higher NVT. In this sense it can be understood as the opposite of velocity. Due to structural dissimilarities in blockchain usage modes, NVTs among all assets are not directly comparable. Our formulation employs adjusted transaction volume, as we understand this to be a purer measure of the actual usage of the chain.

## See Also

* [NVT](nvtadj.md)
* [Free Float NVT 90-day Moving Avg](nvtadjff90.md)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/NVTAdjFF" %}
[\
](https://docs.coinmetrics.io/asset-metrics/economics/nvtadjff)
{% endembed %}
