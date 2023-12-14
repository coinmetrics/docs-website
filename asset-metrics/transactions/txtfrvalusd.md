# Xfer'd Val (USD)

## Definition

The sum USD value of all native units transferred (i.e., the aggregate size in USD of all transfers) that interval. Also known as Transfer Value (USD).

| Name             | MetricID    | Category     | Subcategory    | Type | Unit | Interval      |
| ---------------- | ----------- | ------------ | -------------- | ---- | ---- | ------------- |
| Xfer'd Val (USD) | TxTfrValUSD | Transactions | Transfer value | Sum  | USD  | 1 day, 1 hour |

## Details

* Transfers are movement of native units.
* Only non-zero value, successful, transfers with distinct sender/recipient, are considered.

## Asset-Specific Details

* For assets that have opt-in privacy features, like ZCash, it only takes the non-private activity.

## Release History

* Released in the 1.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/TxTfrValUSD" %}
