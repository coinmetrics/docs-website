# New Funded Addr Cnt

## **Definition**

The sum count of all unique addresses that were newly created and funded (e.g. have a non-zero balance) that interval.

## **Dictionary**

| Name          | **MetricID** | **Category** | **Sub-category** | **Type** | **Unit**  | **Interval** |
| ------------- | ------------ | ------------ | ---------------- | -------- | --------- | ------------ |
| New Addresses | AdrNewBalCnt | Addresses    | Activity         | Sum      | Addresses | 1 day        |

## **Details**

* [Addresses](../../on-chain-data/on-chain-basics.md#address) are the user-identifiers in a ledger change.
* New addresses are addresses identified in the blockchain that did not exist prior to the observation period (e.g. 1 day).
* Depending upon how a blockchain stores address information, new addresses might not be funded with any tokens. In other words, they have a balance of zero.
* This metric only accounts for new addresses that have been funded.

## **Chart**

[New Addr Cnt](https://docs.coinmetrics.io/asset-metrics/adresses/adrnewcnt) showcases all new addresses observed in the network over the previous day, and New Funded Addr Cnt is a subset of New Addr Cnt that only counts addresses with a balance greater than 0.

![Source: CM Network Data Charts](<../../.gitbook/assets/9 - New Addresses.png>)

## **Asset-Specific Details**

This metric is not available for assets that have full privacy, like Monero and Grin. For assets that have opt-in privacy features, like ZCash, it only takes the non-private activities into account.

## **Examples**

Consider the following example:&#x20;

* Both Addreses A and Address B are seen on the ledger for the first time.
* Address A was referred by a smart contract application, perhaps as user identifier, but it was not funded or otherwise engaged by the smart contract. Its balance is zero.
* During that same interval, Address B received funds from an exhange for the first time. Its balance is 0.002.

If the above was the only activity observed in the network during that interval, AdrNewCnt would showcase a value of 1. This value only aggregates activity that is economically relevant (Address B), and excludes non-monetary activity (Address A).

## **Release History**

* Release Version: 5.0 (August, 2021)

## **Interpretation**

Like Active Addresses, New Funded Addresses is a popular measure to proxy the number of new users on a blockchain. Unlike New Addr Cnt, this only showcases addresses with a non-zero balance .

## **See Also**

* [New Addr Cnt](adrnewcnt.md)
* [Address](../../on-chain-data/on-chain-basics.md#address)
* [Active Addresses (Received)](adractreccnt.md)
* [Active Addresses (Sent)](adractsentcnt.md)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/AdrActCnt" %}

