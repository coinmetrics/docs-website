# Exchange Withdrawal Cnt, Incl EtoE

## Definition

The sum count of transfers from any address belonging to an exchange in that interval. Transfers between exchanges are counted.

| Name | MetricID | Category | Subcategory | Type | Unit | Interval |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Exchange Withdrawal Cnt, Incl EtoE | FlowTfrFromExInclCnt | Exchange | Withdrawals | Sum | Transfers | 1 block, 1 day |

## Details

* Coinbase \(i.e., miner reward\) transactions are not counted.
* Transfers between exchanges are counted.

## Asset-Specific Details

* For UTXO-based protocols, this metric applies the following logic:
* * If the input addresses belong to X, then only the outputs where the address doesn’t belong to any exchange are counted as transfers from X
* For account-based protocols, if both sender and recipient belong to the same exchange, the transfer is not counted.

## Release History

* Version 4.2 of CM Network Data Pro Daily Macro \(End of Day\)

## Availability for Assets

{% embed url="https://docs.coinmetrics.io/info/metrics/FlowTfrFromExInclCnt" %}

