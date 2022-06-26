# SOPR Out

## Definition

The ratio of the sum of spent value over the sum of creation value of all spent and created outputs for that interval. There are two versions of this metric. For this version, a spent output’s “spent value” is the market value of that output (i.e., price multiplied by 1). A created output’s “creation value” is the market value of that output (i.e., price multiplied by 1).

| Name     | MetricID | Category  | Subcategory | Type  | Unit          | Interval |
| -------- | -------- | --------- | ----------- | ----- | ------------- | -------- |
| SOPR Out | SOPROut  | Valuation | Valuation   | Ratio | Dimensionless | 1 day    |

## Details

* SOPR was introduced by Renato Shirakashi.
* This version was our first implementation of it that doesn’t weight outputs by their value.
* It oscillates around 1, if below it, people spending are realizing losses, above it, realizing gains.

## Asset-Specific Details

* This metric is not available for assets that have full privacy, like Monero, Grin.
* For assets that have opt-in privacy features, like ZCash, it only takes the non-private balances into account.

## Example

* If in a given day, 3 outputs are spent: \*\* Output A, value 10 BTC, created when BTC was worth $10 \*\* Output B, value 1 BTC, created when BTC was worth $500 \*\* Output C, value 2 BTC, created when BTC was worth $20,000
* If market price is $7,500, SOPRCM for that day is computed as: \*\* Sum spent values: $10 + $500 + $20,000 = $20,510 \*\* Sum creation values: $7,500 + $7,500 + $7,500 = $22,500 \*\* SOPR = $22,500 / $20,510 = 1.097

## Release History

* Released in the 4.0 release of NDP

## See Also

* [SOPR](sopr.md)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/SOPROut" %}
