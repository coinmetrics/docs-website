# Active Wallets Cnt

## **Definition**

The sum count of unique wallets that were active in the network (either as a destination or source of a ledger change) that day. All unique wallets involved in a ledger change action (recipients and originators) are counted. This metric does not double-count wallets. In other words, if a wallet has been deemed active by being part of a ledger change, it is not counted again if is subsequently involved in a transaction during the same time interval. Wallets represent groups of addresses that we estimate are owned by the same entity. They provide a better proxy for user behavior since users often own more than one blockchain address.

## **Dictionary**

| Name                   | **MetricID** | **Category** | **Sub-category** | **Type** | **Unit** | **Interval** |
| ---------------------- | ------------ | ------------ | ---------------- | -------- | -------- | ------------ |
| Wallets, active, count | WalActCnt    | Wallets      | Activity         | Sum      | Wallets  | 1 day        |

## **Details**

* Wallets represent groups of addresses that we estimate are owned by the same entity. In order to group addresses together, we employ a clustering methodology based on well-established industry standards.

## **Asset-Specific Details**

This metric is not available for assets that have full privacy, like Monero and Grin. For assets that have opt-in privacy features, like ZCash, it only takes the non-private activities into account.

## **Release History**

* Released in version 5.1 of Network Data Pro

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/WalActCnt" %}
