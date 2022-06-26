# Wallets w/ Bal > 0 Cnt

## **Definition**

The sum count of unique wallets with a balance greater than 0 that can be observed in the blockchain. Wallets represent groups of addresses that we estimate are owned by the same entity. They provide a better proxy for user behavior since users often own more than one blockchain address.

## **Dictionary**

| Name                         | **MetricID** | **Category** | **Sub-category** | **Type** | **Unit** | **Interval** |
| ---------------------------- | ------------ | ------------ | ---------------- | -------- | -------- | ------------ |
| Wallets, with balance, count | WalBalCnt    | Wallets      | Activity         | Sum      | Wallets  | 1 day        |

## **Details**

* Wallets represent groups of addresses that we estimate are owned by the same entity. In order to group addresses together, we employ a clustering methodology based on well-established industry standards.

## **Asset-Specific Details**

This metric is not available for assets that have full privacy, like Monero and Grin. For assets that have opt-in privacy features, like ZCash, it only takes the non-private activities into account.

## **Release History**

* Released in version 5.1 of Network Data Pro

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/WalBalCnt" %}
