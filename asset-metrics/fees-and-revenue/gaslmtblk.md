# Block Gas Limit

## Definition

The sum gas limit of all blocks that day.

| Name            | MetricID  | Category         | Subcategory | Type | Unit | Interval       |
| --------------- | --------- | ---------------- | ----------- | ---- | ---- | -------------- |
| Block Gas Limit | GasLmtBlk | Fees and revenue | Fees        | Sum  | Gas  | 1 block, 1 day |

## Details

* Gas is a dimensionless unit measuring the computational cost of operations for ETH-based assets. Each transaction spends gas when being processed.
* Each block has a limit of how much gas can be expanded when processing its operations. It is the scaling limit for ETH-based assets, just as block size is for BTC-based ones.

## Chart

![](<../../.gitbook/assets/Screen Shot 2021-05-24 at 6.00.07 PM.png>)

## Asset-Specific Details

* Only relevant for ETH and ETC.

## Interpretation

*   Ethereum blocks are mined roughly every 15 seconds. Each Ethereum block has a maximum size, which limits the amount of data that can be included. The current maximum block size is set at  about 15M gas per block on April 22 (seen in green on the chart above).  Prior to that, the gas limit was 12.5M per block, which set in July 2020. Since the maximum block size is denominated in gas and different transactions have different gas usages based on complexity, there isn’t a consistent maximum number of transactions that can be included in a block. But on average, about 160-200 transactions are included per block.


* The greater the gas limit, the more space is available per block, which can help push down the average gas price.

## Release History

* Released in the 1.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/GasLmtBlk" %}
