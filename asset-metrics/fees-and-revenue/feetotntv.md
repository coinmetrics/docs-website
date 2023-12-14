# Total Fees (native units)

## Definition

The sum of all fees paid to miners, transaction validators, stakers and/or block producers that interval. In certain cryptonetworks, fees might be burned (destroyed), but they are still accounted for in this metric.

| Name                      | MetricID  | Category         | Subcategory | Type | Unit         | Interval      |
| ------------------------- | --------- | ---------------- | ----------- | ---- | ------------ | ------------- |
| Total Fees (native units) | FeeTotNtv | Fees and revenue | Fees        | Sum  | Native units | 1 day, 1 hour |

## Details

* This metric includes fees that are burned as part of the protocol.
* For chains that use median time, the day is defined using it, otherwise, it’s defined using the block’s timestamps.

## Release History

* Released in the 1.0 release of NDP

## Interpretation

Fees in USD terms (see Fees, Transaction, Median, USD; Fees, Transaction, Mean, USD, and Fees, Total, USD) are often biased by volatility in unit price, making it difficult to determine trends in fee pressure. Evaluating fees in native unit terms removes the noise from exchange rate volatility and enables more consistent time series comparisons.

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/FeeTotNtv" %}
