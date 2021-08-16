# New Addr Cnt

## **Definition**

The sum count of all unique addresses that were newly created that interval.

## **Dictionary**

| Name | **MetricID** | **Category** | **Sub-category** | **Type** | **Unit** | **Interval** |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| New Addresses | AdrNewCnt | Addresses | Activity | Sum | Addresses | 1 day |

## **Details**

* [Addresses](../../on-chain-basics.md#address) are the user-identifiers in a ledger change.
* New addresses are addresses identified in the blockchain that did not exist prior to the observation period \(e.g. 1 day\).
* Depending upon how a blockchain stores address information, new addresses might not be funded with any tokens. In other words, they have a balance of zero.
* As such, a caveat of this metric is that it can be inflated by activity that is not economicallt relevant.
* For new addresses that are funded and are economically relevant, please refer to New Funded Adrr Cnt \(AdrNewBalCnt\).

## **Asset-Specific Details**

This metric is not available for assets that have full privacy, like Monero and Grin. For assets that have opt-in privacy features, like ZCash, it only takes the non-private activities into account.

## **Examples**

Consider the following example: 

* Both Addreses A and Address B are seen on the ledger for the first time.
* Address A was referred by a smart contract application, perhaps as user identifier, but it was not funded or otherwise engaged by the smart contract. Its balance is zero.
* During that same interval, Address B received funds from an exhange for the first time. Its balance is 0.002.

If the above was the only activity observed in the network during that interval, AdrNewCnt would showcase a value of 2. This value aggregates activity that is economically relevant \(Address B\) as well as non monetary \(Address A\).

## **Release History**

* Release Version: 5.0 \(August, 2021\)

## **Interpretation**

Like Active Addresses, New Addresses is a popular measure to proxy the number of _new_ users on a blockchain. However, in blockchains where address creation is cheap, or free, new addresses can still be trivially forged.

## **See Also**

* [New Funded Addr Cnt](new-funded-addr-cnt.md)
* [Address](../../on-chain-basics.md#address)
* [Active Addresses \(Received\)](adractreccnt.md)
* [Active Addresses \(Sent\)](adractsentcnt.md)

## Availability for Assets

{% embed url="https://docs.coinmetrics.io/info/metrics/AdrActCnt" %}





