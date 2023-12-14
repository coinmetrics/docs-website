# Median Tx Size (native units)

## Definition

The median count of native units transferred per transfer (i.e., the median "size" of a transfer) that interval.

## Dictionary

| Name                          | MetricID       | Category     | Subcategory    | Type   | Unit         | Interval      |
| ----------------------------- | -------------- | ------------ | -------------- | ------ | ------------ | ------------- |
| Median Tx Size (native units) | TxTfrValMedNtv | Transactions | Transfer value | Median | Native units | 1 day, 1 hour |

## Details

* Transfers are movement of native units.
* Only non-zero value, successful, transfers with distinct sender/recipient, are considered.

## Asset-Specific Details

* For assets that have opt-in privacy features, like ZCash, it only takes the non-private activity.

## Release History

* Released in the 1.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/TxTfrValMedNtv" %}
