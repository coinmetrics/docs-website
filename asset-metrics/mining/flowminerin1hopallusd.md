# Flows Received One Hop from Miners (USD)

## Defintion

The sum of block rewards, fees, and other transfers received by all addresses within one hop of a mining entity during an interval, excluding transfers from another address within one hop of a mining entity. An address within one hop of a mining entity is defined as an address that has been credited from a transaction debiting the 'FEES' or 'ISSUANCE' accounts in accordance with Coin Metric’s Universal Blockchain Data Model (UBDM).

| Name                                     | MetricID              | Category | Subcategory | Type | Unit | Interval |
| ---------------------------------------- | --------------------- | -------- | ----------- | ---- | ---- | -------- |
| Flows Received One Hop from Miners (USD) | FlowMinerIn1HopAllUSD | Miners   | Flows In    | Sum  | USD  | 1 day    |

## Details

* This metric is not computed as the sum of block rewards and fees collected by addresses within one hop of a mining entity during an interval.
* For more details on how this metric is computed, please refer to our blog post introducing [Miner Flows](https://coinmetrics.substack.com/p/coin-metrics-state-of-the-network-3e2)

## Asset-Specific Details

* This metric will initially only be available for Bitcoin.

## Release History

* Release Version: NDP-EOD 4.8 (Nov, 2020)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/FlowMinerIn1HopAllUSD" %}
