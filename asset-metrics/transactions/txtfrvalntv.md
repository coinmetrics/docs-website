# Xfer'd Val (native units)

## Definition

The sum of native units transferred (i.e., the aggregate "size" of all transfers) that interval. Also known as Transfer Value (native units).

| Name                      | MetricID    | Category     | Subcategory    | Type | Unit         | Interval      |
| ------------------------- | ----------- | ------------ | -------------- | ---- | ------------ | ------------- |
| Xfer'd Val (native units) | TxTfrValNtv | Transactions | Transfer value | Sum  | Native units | 1 day, 1 hour |

## Details

* Transfers are movement of native units.
* Only non-zero value, successful, transfers with distinct sender/recipient, are considered.
* Failed transactions are not considered in TxTfrValNtv
* For ETH, the fees sent from the original sender to the miner for the failed transaction are not considered

## Asset-Specific Details

* For assets that have opt-in privacy features, like ZCash, it only takes the non-private activity.

## Release History

* Released in the 1.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/TxTfrValNtv" %}
