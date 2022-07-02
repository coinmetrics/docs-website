# Exchange Tx Cnt

## Definition

The sum count of transactions that involved any address belonging to an exchange, as a sender or recipient of a non-zero transfer of native units, in that interval. If a transaction involves multiple exchanges, it is only counted once.

| Name            | ID      | Category     | Subcategory  | Type | Unit         | Interval |
| --------------- | ------- | ------------ | ------------ | ---- | ------------ | -------- |
| Exchange Tx Cnt | TxExCnt | Transactions | Transactions | Sum  | Transactions | 1 day    |

## Details

* Coinbase (i.e., miner reward) transactions are not counted.
* Only exchanges and their addresses that Coin Metrics has identified are included (i.e., not all exchanges and their addresses have been identified) so this metric should be thought of as a minimum potential value.

## Release History

* Version 4.2 of CM Network Data Pro Daily Macro (End of Day)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/TxExCnt" %}
