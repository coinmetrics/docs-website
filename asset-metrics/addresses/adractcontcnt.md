# Active Smart Contract Addr Cnt

## **Definition**

The sum count of unique smart contract addresses that were active in the network (either as a recipient or originator of a ledger change) that interval. All unique smart contracts involved in a ledger change action (recipients and originators) are counted. This metric does not double-count contracts. In other words, if a contract has been deemed active by being part of a ledger change, it is not counted again if is subsequently invoked during the same time interval.

## **Dictionary**

| Name                           | **MetricID**  | **Category** | **Sub-category** | **Type** | **Unit**                 | **Interval** |
| ------------------------------ | ------------- | ------------ | ---------------- | -------- | ------------------------ | ------------ |
| Active Smart Contract Addr Cnt | AdrActContCnt | Addresses    | Active           | Sum      | Smart Contract Addresses | 1 day        |

## **Details**

* Active smart contact [address](../../on-chain-basics.md#address) count represents the number of unique smart contract addresses that participated in a ledger change.
* For this unadjusted version of the metric, all ledger changes are considered.
* Ledger changes can include activities such as Decentralized Finance (DeFi) trades, DAO votes, token transfers, as well as any other activity facilitated by a smart contract.&#x20;
* All participants of a ledger change activity are included.
* If an address was active multiple times during the aggregation interval (e.g., 1 day), it is counted only once.

## **Asset-Specific Details**

* This metric is only available for assets that feature the notion of smart contract addresses, such as Ethereum.

## **Release History**

* Released in Network Data Pro (NDP) version 5.1

## **See Also**

* [Address](../../on-chain-basics.md#address)
* [Active Addresses (Received)](adractreccnt.md)
* [Active Addresses (Sent)](adractsentcnt.md)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/AdrActContCnt" %}
