# Median Tx Size (USD)

## Definition

The median USD value transferred per transfer (i.e., the median "size" in USD of a transfer) that interval.

| Name                 | MetricID       | Category     | Subcategory    | Type   | Unit | Interval      |
| -------------------- | -------------- | ------------ | -------------- | ------ | ---- | ------------- |
| Median Tx Size (USD) | TxTfrValMedUSD | Transactions | Transfer value | Median | USD  | 1 day, 1 hour |

## Details

* Transfers are movement of native units.
* Only non-zero value, successful, transfers with distinct sender/recipient, are considered.

## Asset-Specific Details

* For assets that have opt-in privacy features, like ZCash, it only takes the non-private activity.

## Release History

* Released in the 1.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/TxTfrValMedUSD" %}
