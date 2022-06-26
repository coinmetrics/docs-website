# Miner Cap to Realized Cap (MCRC)

## Definition

The ratio of Miner Cap over Realized Cap at the end of that interval. Miner Cap represents all funds held by mining pools and miners and is calculated as the sum of SplyMiner0HopAllUSD (supply held by mining pools) and SplyMiner1HopAllUSD (supply held by miners). [Realized Cap](../market/caprealusd.md) (CapRealUSD) is defined as the sum USD value based on the USD closing price on the day that a native unit last moved (i.e., last transacted) for all native units.

| Name                             | IMetricD | Category  | Subcategory | Type  | Unit          | Interval |
| -------------------------------- | -------- | --------- | ----------- | ----- | ------------- | -------- |
| Miner Cap to Realized Cap (MCRC) | MCRC     | Economics | Mining      | Ratio | Dimensionless | 1 day    |

## Details

* This metric shows the ratio between the assets that miners hold in custody relative to the "cost basis" of the entire network.
* Like [MVRV](../market/capmvrvcur.md), it can be used to better understand the market cycle as it identifies moments where the value of the supply held by miners is higher than the cost basis of the entire network.
* Similarly, it may showcase when miners are capitulating and potentially selling at a loss.
* Miners are speculators as they are naturally exposed to the price of the currency they are mining. As such, they collectively make buy or sell decisions that ultimately impact the market.

## Chart

![](../../.gitbook/assets/MCRC\(1\).png)

## Interpretation

* When comparing the USD value of what miners have in custody relative to the cost basis of the network as a whole, a natural threshold of 1 is relevant.
* When this threshold is breached, it might indicate that miners are more willing to sell their assets, as their profit margins have widened.&#x20;
* Conversely, as this ratio nears zero, it might indicate miners are selling at a loss.

## Asset-Specific Details

Only applicable to assets for which we have SplyMiner0HopAllUSD (supply held by mining pools), SplyMiner1HopAllUSD (supply held by miners) and Realized Cap (CapRealUSD).

## Release History

* Release Version: NDP 5.0 (August, 2021)

## See Also:

* [MCTC (Miner Cap / Thermo Cap)](mctc.md)
* [MVRV (Market Cap / Realized Market Cap)](../market/capmvrvcur.md)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/MCTC" %}
