# Exchange Deposit Cnt, Incl EtoE

## Definition

The sum count of transfers to any address belonging to an exchange in that interval. Transfers between exchanges are counted.

| Name                            | MetricID           | Category | Subcategory | Type | Unit      | Interval       |
| ------------------------------- | ------------------ | -------- | ----------- | ---- | --------- | -------------- |
| Exchange Deposit Cnt, Incl EtoE | FlowTfrToExInclCnt | Exchange | Deposits    | Sum  | Transfers | 1 block, 1 day |

## Details

* Coinbase (i.e., miner reward) transactions are not counted.
* Transfers between exchanges are counted.
* Only exchanges and their addresses that Coin Metrics has identified are included (i.e., not all exchanges and their addresses have been identified) so this metric should be thought of as a minimum potential value.

## Asset-Specific Details

* For UTXO-based protocols, this metric does not count change outputs:
*
  * If the input addresses belong to X, then the outputs belonging to X are not counted as transfers to X
* For account-based protocols, if both sender and recipient belong to X, the transfer is not counted.

## Release History

* Version 4.2 of CM Network Data Pro Daily Macro (End of Day)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/FlowTfrToExInclCnt" %}
