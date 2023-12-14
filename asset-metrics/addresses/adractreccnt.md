# Active Addr Cnt (Received)

## **Definition**

The sum count of unique addresses that were active in the network (as a recipient of a ledger change) that day.  Individual destination addresses are counted.  Individual addresses are not double-counted if previously active.&#x20;

**Dictionary**

| **Name**                    | Metric ID    | **Category** | **Sub-category** | **Type** | **Unit**  | **Interval**  |
| --------------------------- | ------------ | ------------ | ---------------- | -------- | --------- | ------------- |
| Active Addresses (Received) | AdrActRecCnt | Addresses    | Activity         | Sum      | Addresses | 1 day, 1 hour |

## **Details**

* Active Addresses (Received) is the sum count of unique addresses that where the receiving end of a ledger change
* For this unadjusted version of the metric, all ledger change scenarios are considered.
* Such ledger changes can include mining, staking, transacting, account creation, etc..
* If an address was active multiple times as recipient during that interval, it is counted only once.
* For ETH, miners receiving fees from the original sender of a failed transaction are counted as active receiving addresses.

## **Asset-Specific Details**

* This metric is not available for assets that have full privacy, like Monero, Grin. For assets that have opt-in privacy features, like ZCash, it only takes the non-private activities into account.

## **Examples**

In a given day:

* Address A mines 10 coins
  * A was recipient, no sender
* Address B sends 2 coins to each C and D
  * C and D were recipients, B was sender
* Address D delegates 20 coins to E
  * D is the sender, E is recipient
* Address A burns 1 coin
  * A is the sender, no recipient
* Address F votes on a protocol change
  * F is the sender/initiator

We would count as active recipients: A, C, D and E. The value of the metric would therefore be: 4.

## **Release History**

* Released in the 1.0 release of NDP

## **See Also**

* [Active Addresses](adractcnt.md)
* [Active Addresses (Sent)](adractsentcnt.md)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/AdrActRecCnt" %}
