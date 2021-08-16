# Total Base Fees Burnt \(native units\)

## Definition

The total Base Fees paid for transactions during a time interval \(e.g. 1 day\), shown in native units \(i.e. in ETH terms\).

The concept of a Base Fee was introduced as part of [EIP-1559](https://notes.ethereum.org/@vbuterin/eip-1559-faq) and it represents the portion of the total transaction fees that is destroyed and taken out of circulation \(i.e. _burnt\)_. Ethereum post-1559 requires users to pay for a Base Fee as a prerequisite to include transactions in a block. The Base Fee can go up or down on the basis of the size \(in gas units\) of the previous block. In times of congestion, where blocks are sequentially increasing in size, paying a Base Fee does not guarantee that a transaction will be included in a block. In such events, users can optionally pay an additional Miner Tip to nudge miners to include their transactions in their block.

| Name | MetricID | Category | Subcategory | Type | Unit | Interval |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Total Base Fees Burnt Ntv | SplyBurntNtv | Supply | Burnt | Sum | Native Units | 1 day |

## Details

* EIP1559 was a highly anticipated proposal that changes how transaction fees are priced in Ethereum, as well as the dynamics of block sizes.
* The proposal activated on the Ethereum Network in August of 2021 and marks one of the biggest changes in monetary policy in the history of cryptoassets.
* Instead of the legacy _gas price_, 1559 splits transaction fees into two distinct fields: a Base Fee and an optional Tip \(also known as a _Priority Fee_\).
* This metric calculates the total Base Fees paid in transactions that have occurred in the network over the measuring period \(e.g. 1 day\).
* For a thorough review of EIP1559 and the design of its pricing mechanism, please refer to [this paper](https://arxiv.org/pdf/2012.00854.pdf).

## Interpretation

* Base Fees fluctuate on the basis of network utilization. If there is high demand for transaction settlement, Base Fees go up, and as demand fades, Base Fees go down. 
* The pricing of Base Fees is inextricably connected to size of blocks in the blockchain. Upon the the activation fo EIP-1559, the maximum size of blocks in Ethereum \(measured in units of gas\) was more than doubled to 30M.
* Although blocks are larger, this pricing mechanism attempts to target an average of 15M gas units per block, and an exponential function is used to increase or decrease Base Fees so that this target is hit.
* If, for example, the previous block was above 15M units of gas, the base fee is increased. If there are several sequential blocks above the 15M target, Base Fees increase exponentially which disincentivizes users from transacting. 
* Changes in Base Fees over time can depict changes in demand for block space. When miner tips have to be used due to Base Fees not being enough, this is a sign of network congestion. 

## Release History

* Released in the 5.0 release of NDP \(August, 2021\).

## Availability for Assets

{% embed url="https://docs.coinmetrics.io/info/metrics/SplyBurntNtv" %}



