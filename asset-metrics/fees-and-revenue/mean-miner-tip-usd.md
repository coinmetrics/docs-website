# Mean Miner Tip \(USD\)

## Definition

The average \(mean\) Miner Tip, a.k.a. _priority fee,_ paid for transactions during a time interval \(e.g. 1 day\), shown in USD.

The concept of a Miner Tip was introduced as part of [EIP-1559](https://notes.ethereum.org/@vbuterin/eip-1559-faq) and it represents the portion of the total transaction fees that rewards miners. This serves as an added incentive so that miners prioritize transactions that have opted-in and paid a tip. The other portion is called the Base Fee, and it is burnt \(destroyed\) after the transaction is included in a block.

Ethereum post-1559 requires users to pay for a Base Fee as a prerequisite to include transactions in a block. The Base Fee can go up or down on the basis of the size \(in gas units\) of the previous block. In times of congestion, where blocks are sequentially increasing in size, paying a Base Fee does not guarantee that a transaction will be included in a block. In such events, users can optionally pay an additional miner tip to nudge miners to include their transactions in their block.

| Name | MetricID | Category | Subcategory | Type | Unit | Interval |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Mean Miner Tip | FeePrioMeanUSD | Fees and revenue | Fees | Mean | USD | 1 day |

## Details

* EIP1559 was a highly anticipated proposal that changes how transaction fees are priced in Ethereum, as well as the dynamics of block sizes.
* The proposal activated on the Ethereum Network in August of 2021 and marks one of the biggest changes in monetary policy in the history of cryptoassets.
* Instead of the legacy _gas price_, 1559 splits transaction fees into two distinct fields: a Base Fee and an optional Tip \(also known as a _Priority Fee_\).
* This metric calculates the average Tip in transactions that have occurred in the network over the measuring period \(e.g. 1 day\).
* For a thorough review of EIP1559 and the design of its pricing mechanism, please refer to [this paper](https://arxiv.org/pdf/2012.00854.pdf).

## Interpretation

* Miner tips are optional and showcase demand for block space \(i.e. transaction settlement\) in the short-term.
* Changes in average miner tip over time can depict changes in demand for block space. When miner tips have to be used due to Base Fees not being enough, the fee market reverts back to first-price auction \(like other cryptoassets\).
* In such scenarios, this metric should see an increase as users bid up fees as they did prior to the activation of EIP1559.

## Release History

* Released in the 5.0 release of NDP \(August, 2021\)

## Availability for Assets

{% embed url="https://docs.coinmetrics.io/info/metrics/FeePrioMeanUSD" %}



