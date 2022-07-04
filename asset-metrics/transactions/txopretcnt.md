# OP\_RETURN Tx Cnt

## Definition

The sum count of transactions in that interval that included at least one OP\_RETURN output. OP\_RETURN outputs are used to embed data into the blockchain database.

| Name              | MetricID   | Category     | Subcategory  | Type | Unit         | Interval |
| ----------------- | ---------- | ------------ | ------------ | ---- | ------------ | -------- |
| OP\_RETURN Tx Cnt | TxOpRetCnt | Transactions | Transactions | Sum  | Transactions | 1 day    |

## Details

* Coinbase (i.e., miner reward) transactions are not included.
* This metric is only available for Bitcoin and its forks/derivatives.

## Release History

* Version 4.2 of CM Network Data Pro Daily Macro (End of Day)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/TxOpRetCnt" %}
