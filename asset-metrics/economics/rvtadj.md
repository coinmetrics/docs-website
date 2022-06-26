# RVT

## Definition

The ratio of the network's realized value to its adjusted transfer value. Also referred to as RVT.

| Name | MetricID | Category  | Subcategory | Type  | Unit          | Interval |
| ---- | -------- | --------- | ----------- | ----- | ------------- | -------- |
| RVT  | RVTAdj   | Economics | Valuation   | Ratio | Dimensionless | 1 dayC   |

## Details

* Computed as realized value (aka realized market cap) over adjusted transfer value.
* [Checkmate (2019)](https://medium.com/@\_Checkmatey\_/the-bitcoin-rvt-ratio-a-high-conviction-macro-indicator-615b68715b77) formulates the realized capitalization to transaction value (RVT) ratio which uses the same fundamental principles behind the NVT ratio but uses realized capitalization instead of market capitalization in the numerator of the ratio.

## Release History

* Release Version: NDP-EOD 4.8 (Nov, 2020)

## Interpretation

RVT is based on the same principles as NVT but uses Realized Cap in the numerator.  Realized Cap can be a smoother measure of network valuation than the Market Cap as it is concerned with the price at which the coin was last moved on-chain.  As a result, both Realized Cap and the RVT are shielded from day-to-day market sentiment and speculation that are reflected in Market Cap. &#x20;

RVT can be a slower moving, higher conviction signal tuned to the macro sentiment of HODLers.&#x20;

## See Also

* [Realized Market Cap (USD)](../market/caprealusd.md)
* [RVT 90-day Moving Avg](rvtadj90.md)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/RVTAdj" %}
