# Active Wallets Cnt (Received)

## **Definition**

The sum count of unique wallets that were active in the network as a recipient of funds. All unique wallets that have received funds in transactions are counted. This metric does not double-count wallets. In other words, if a wallet has been deemed active by receiving funds, it is not counted again if it receives funds again during the same time interval. Wallets represent groups of addresses that we estimate are owned by the same entity. They provide a better proxy for user behavior since users often own more than one blockchain address.

## **Dictionary**

| Name                             | **MetricID** | **Category** | **Sub-category** | **Type** | **Unit** | **Interval** |
| -------------------------------- | ------------ | ------------ | ---------------- | -------- | -------- | ------------ |
| Wallets, active, received, count | WalActRecCnt | Wallets      | Activity         | Sum      | Wallets  | 1 day        |

## **Details**

* Wallets represent groups of addresses that we estimate are owned by the same entity. In order to group addresses together, we employ a clustering methodology based on well-established industry standards.

## **Asset-Specific Details**

This metric is not available for assets that have full privacy, like Monero and Grin. For assets that have opt-in privacy features, like ZCash, it only takes the non-private activities into account.

## **Release History**

* Released in version 5.1 of Network Data Pro

## Availability for Assets

{% embed url="https://docs.coinmetrics.io/info/metrics/WalActCnt" %}



