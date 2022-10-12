# EIP1559 Tx Cnt

## Definition

The sum count of transactions that have natively adopted EIP-1559 features by featuring a Base Fee and Miner Tip.

EIP1559 introduced a host of changes to Ethereum's fee mechanism. While this proposal was implemented as a hard fork, not all wallets have adopted this new transaction type upon activation.

Transactions that are EIP1559-compliant have two portions: a Miner Tip and a Base Fee. Miner Tips represent the portion of the total transaction fees that rewards miners. This serves as an optinal incentive mechanism for miners to prioritize transactions that have opted-in and paid a tip. Base Fees, on the other hand, are mandatory and represent the minimum amount needed to be paid for a transaction to be included in a block. After inclusion, the Base Fee is effectively taken out of circulation, and it is burnt (destroyed).&#x20;

| Name           | MetricID     | Category     | Subcategory  | Type | Unit         | Interval |
| -------------- | ------------ | ------------ | ------------ | ---- | ------------ | -------- |
| EIP1559 Tx Cnt | TxEIP1559Cnt | Transactions | Transactions | Sum  | Transactions | 1 day    |

## Details

* EIP1559 was a highly anticipated proposal that changes how transaction fees are priced in Ethereum, as well as the dynamics of block sizes.
* The proposal activated on the Ethereum Network in August of 2021 and marks one of the biggest changes in monetary policy in the history of cryptoassets.
* Instead of the legacy _gas price_, 1559 splits transaction fees into two distinct fields: a Base Fee and an optional Tip (also known as a _Priority Fee_).
* This metric calculates the total number of native EIP-1559 transactions that have occurred in the network over the measuring period (e.g. 1 day).
* For a thorough review of EIP1559 and the design of its pricing mechanism, please refer to [this paper](https://arxiv.org/pdf/2012.00854.pdf).

## Chart

{% file src="../../.gitbook/assets/Coin_Metrics_Network_Data_2022-09-14T15-07.png" %}
Source: CM Network Data Charts
{% endfile %}

## Interpretation

* Not all wallets have implemented EIP-1559 upon activation, so this metric serves as a proxy for the native adoption of this new transaction type.
* While all transactions must abide by EIP-1559 at the blockchain consensus layer (and at the very least carry a Base Fee), not all wallets have natively adopted this transaction fomat.
* This metric serves a proxy to measure the native adoption of EIP1559 by wallets across the network.&#x20;
* The ratio of TxEIP1559Cnt and Tx Cnt provides a view of the adoption of 1559 natively, relative to all other transactiosn that have taken place in the network.&#x20;

## Release History

* Released in the 5.0 release of NDP (August, 2021)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/TxEIP1559Cnt" %}
