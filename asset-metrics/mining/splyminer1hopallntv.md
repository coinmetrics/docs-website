# Supply One Hop from Miners (native units)

## Definition

The sum of the balances of all addresses within one hop of a mining entity. An address within one hop of a mining entity is defined as an address that has been credited from a transaction debiting the 'FEES' or 'ISSUANCE' accounts in accordance with Coin Metric’s Universal Blockchain Data Model (UBDM), or any address that has been credited in a transaction sent by such an address.

| Name                                      | MetricID            | Category | Subcategory | Type | Unit         | Interval |
| ----------------------------------------- | ------------------- | -------- | ----------- | ---- | ------------ | -------- |
| Supply One Hop from Miners (native units) | SplyMiner1HopAllNtv | Mining   | Balances    | Sum  | Native units | 1 day    |

## Details

* For more details on how this metric is computed, please refer to our blog post introducing [Miner Flows](https://coinmetrics.substack.com/p/coin-metrics-state-of-the-network-3e2)
* This metric will initially only be available for Bitcoin.

## Release History

* Release Version: NDP-EOD 4.8 (Nov, 2020)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/SplyMiner1HopAllNtv" %}
