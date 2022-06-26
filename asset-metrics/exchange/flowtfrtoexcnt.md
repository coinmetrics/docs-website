# Exchange Deposit Cnt

## Definition

The sum count of transfers to any address belonging to an exchange in that interval. Transfers between exchanges are not counted.

| Name                 | MetricID       | Category | Subcategory | Type | Unit      | Interval       |
| -------------------- | -------------- | -------- | ----------- | ---- | --------- | -------------- |
| Exchange Deposit Cnt | FlowTfrToExCnt | Exchange | Deposits    | Sum  | Transfers | 1 block, 1 day |

## Details

* Coinbase (i.e., miner reward) transactions are not counted.
* Exchange to exchange activity is excluded.
* Only exchanges and their addresses that Coin Metrics has identified are included (i.e., not all exchanges and their addresses have been identified) so this metric should be thought of as a minimum potential value.

## Asset-Specific Details

* For UTXO-based protocols, if any input address belongs to an exchange, the transaction’s outputs are not counted.
* For account-based protocols, if the sender is an exchange, the transfer is not counted.

## Release History

* Version 4.2 of CM Network Data Pro Daily Macro (End of Day)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/FlowTfrToExCnt" %}
