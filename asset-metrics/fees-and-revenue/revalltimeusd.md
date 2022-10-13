# All Time Miner Revenue (USD)

## Definition

The sum USD value of all miner revenue (fees plus newly issued native units) for all time.

| Name                         | MetricID      | Category         | Subcategory | Type | Unit | Interval |
| ---------------------------- | ------------- | ---------------- | ----------- | ---- | ---- | -------- |
| All Time Miner Revenue (USD) | RevAllTimeUSD | Fees and revenue | Revenue     | Sum  | USD  | All time |

## Details

* This metric is defined as the cumulative sum of RevUSD.
* It’s also known as thermocap

## Release History

* Released in the 1.0 release of NDP

## Interpretation

* The cumulative miner revenue for an asset, also called Thermocap, can be interpreted as an estimate of fiat inflows into an asset. The assumption behind this is that miners have fiat expenses but crypto revenue. To cover their expenses (mining hardware, electricity, wages, etc..), they must sell some or most of their crypto revenue for fiat. Given that, we know that the other party of this transaction must sell fiat for crypto and is therefore a new inflow in the asset. While this holds for large assets, miners of smaller assets might sell their mined crypto for BTC/ETH and then sell this for USD. This is a naive heuristic and presumes that miners do not mine speculatively, hoarding their coins without selling them off.

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/RevAllTimeUSD" %}
