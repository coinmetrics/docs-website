# Net Flows One Hop from Miners (USD)

## Definition

The difference between the sum of block rewards, fees, and other transfers received by all addresses within one hop of a mining entity during an interval, excluding transfers to another address within one hop of a mining entity, and those sent. An address within one hop of a mining entity is defined as an address that has been credited from a transaction debiting the 'FEES' or 'ISSUANCE' accounts in accordance with Coin Metric’s Universal Blockchain Data Model (UBDM), or any address that has been credited in a transaction sent by such an address.

| Name                                | MetricID               | Category | Subcategory | Type | Unit | Interval |
| ----------------------------------- | ---------------------- | -------- | ----------- | ---- | ---- | -------- |
| Net Flows One Hop from Miners (USD) | FlowMinerNet1HopAllUSD | Mining   | Flows Net   | Sum  | USD  | 1 day    |

## Details

* For more details on how this metric is computed, please refer to our blog post introducing [Miner Flows](https://coinmetrics.substack.com/p/coin-metrics-state-of-the-network-3e2)

## Asset-Specific Details

* This metric will initially only be available for Bitcoin.

## Release History

* Release Version: NDP-EOD 4.8 (Nov, 2020)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/FlowMinerNet1HopAllUSD" %}
