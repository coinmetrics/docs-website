# Bitstamp Deposit Cnt

## Definition

The sum count of transfers to any address belonging to exchange Bitstamp in that interval. If the sender address also belongs to Bitstamp, the transfer is not counted.

| Name                 | MetricID        | Category | Subcategory | Type | Unit         | Interval       |
| -------------------- | --------------- | -------- | ----------- | ---- | ------------ | -------------- |
| Bitstamp Deposit Cnt | FlowTfrInBSPCnt | Exchange | Deposits    | Sum  | Native units | 1 block, 1 day |

## Details

* Coinbase (i.e., miner reward) transactions are not counted.

## Asset-Specific Details

* For UTXO-based protocols, this metric does not count change outputs:
*
  * If the input addresses belong to Bitstamp, then the outputs belonging to Bitstamp are not counted as transfers to Bitstamp.
* For account-based protocols, if both sender and recipient belong to Bitstamp, then the transfer is not counted.

## Release History

* Version 4.2 of CM Network Data Pro Daily Macro (End of Day)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/FlowTfrInBSPCnt" %}
