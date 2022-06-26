# Miner Outflow to Miner Revenue (MOMR)

## Definition

The ratio of Miner Outflows over Miner Revenue at the end of that interval. Miner outflows represent the sum of funds being sent by miner addresses (1-hop from the coinbase) and are calculated as FlowMinerOut1HopAllNtv. Miner Revenue represents the sum of funds (new coins and transaction fees) sent to miners over a time window and is calculated as RevNtv.

| Name                                  | IMetricD | Category  | Subcategory | Type  | Unit          | Interval |
| ------------------------------------- | -------- | --------- | ----------- | ----- | ------------- | -------- |
| Miner Outflow to Miner Revenue (MOMR) | MOMR     | Economics | Mining      | Ratio | Dimensionless | 1 day    |

## Details

* This metric shows the ratio between the assets leaving miner addresses relative to how much miners have received as revenue.
* The FlowMinerOut1HopAllNtv is part of our Miner Flows family of metrics, which takes into account the custody structures within mining pools and their constituents who are individually mining.

## Chart

![](../../.gitbook/assets/MOMR\(1\).png)

## Interpretation

* When comparing the USD value of what miners are sending relative to the funds they are receiving, there appears to be a negative relationship with price.
* That makes intuitive sense as it might indicate that miners are sending more funds out (which might show higher willingness to sell) relative to what they are receiving as revenue.
* As such, this ratio might serve as a barometer for miner sentiment and identify liquidity events when miners might be bearish.
* It is important to note that the mere act of sending funds from one address to another does not necessary signify the act of selling.
* Only when there is a clear & noticeable uptick in this metric that the speculation that miners are selling is defensible, given that outflows might signify more mundane events such as a cold wallet shuffle.
* Miner outflows are naturally very volatile. As such, we recommend using a monthly (30d) Moving Average when visualizing this metric.&#x20;

## Asset-Specific Details

Only applicable to assets for which we have SplyMiner0HopAllUSD (supply held by mining pools), SplyMiner1HopAllUSD (supply held by miners) and Realized Cap (CapRealUSD).

## Release History

* Release Version: NDP 5.0 (August, 2021)

## See Also:

* [MCTC (Miner Cap / Thermo Cap)](mctc.md)
* [MVRV (Market Cap / Realized Market Cap)](../market/capmvrvcur.md)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/MOMR" %}
