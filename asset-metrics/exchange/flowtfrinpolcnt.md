# Poloniex Deposit Cnt

## Definition

The sum count of transfers to any address belonging to exchange Poloniex in that interval. If the sender address also belongs to Poloniex, the transfer is not counted.

| Name                 | MetricID        | Category | Subcategory | Type | Unit         | Interval       |
| -------------------- | --------------- | -------- | ----------- | ---- | ------------ | -------------- |
| Poloniex Deposit Cnt | FlowTfrInPOLCnt | Exchange | Deposits    | Sum  | Native units | 1 block, 1 day |

## Details

* Coinbase (i.e., miner reward) transactions are not counted.

## Asset-Specific Details

* For UTXO-based protocols, this metric does not count change outputs:
  * If the input addresses belong to Poloniex, then the outputs belonging to Poloniex are not counted as transfers to Poloniex.
* For account-based protocols, if both sender and recipient belong to Poloniex, then the transfer is not counted.

## Release History

* Version 4.2 of CM Network Data Pro Daily Macro (End of Day)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/FlowTfrInPOLCnt" %}
