# Fully Shielded Tx Cnt

## Definition

The sum count of transactions using fully shielding privacy features that interval. Only fully shielding transactions are included (transactions with partial or mixed shielding are not included). Transactions represent a bundle of intended actions to alter the ledger initiated by a user (human or machine). Fully shielding a transaction hides all of the activity of a transaction (except for the miner fee it paid).

| Name                  | MetricID      | Category     | Subcategory  | Type | Unit         | Interval |
| --------------------- | ------------- | ------------ | ------------ | ---- | ------------ | -------- |
| Fully Shielded Tx Cnt | TxShldFullCnt | Transactions | Transactions | Sum  | Transactions | 1 day    |

## Details

* Transactions in assets with opt-in privacy features can be of several types:
  * Fully shielding: all senders and all recipients are unknown
  * Shielding: all senders are known, all recipients are unknown
  * Deshielding: all senders are unknown, all recipients are known
  * Mixed: some senders are unknown or/and some recipients are unknown
  * Transparent: all senders and recipients are known
* This metric includes all transaction types except transparent

## Asset-Specific Details

* This metric is only available for assets that have opt-in privacy features like ZCash and its derivatives

## Release History

* Version 4.5 of CM Network Data Pro Daily Macro (End of Day)
* Date Last Modified: 2019-01-10

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/TxShldFullCnt" %}
