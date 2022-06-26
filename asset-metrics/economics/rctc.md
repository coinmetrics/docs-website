# Realized Cap to Thermo Cap (RCTC)

## Definition

The ratio of the Realized Cap over Thermo Cap at the end of that interval.  [Realized Cap](../market/caprealusd.md) (CapRealUSD) is defined as the sum USD value based on the USD closing price on the day that a native unit last moved (i.e., last transacted) for all native units. Thermo Cap is calculated as RevAllTimeUSD and it represents the USD value of all funds disbursed to miners at the time of issuance.

| Name                              | IMetricD | Category  | Subcategory | Type  | Unit          | Interval |
| --------------------------------- | -------- | --------- | ----------- | ----- | ------------- | -------- |
| Realized Cap to Thermo Cap (RCTC) | RCTC     | Economics | Valuation   | Ratio | Dimensionless | 1 day    |

## Details

* Like [MVRV](../market/capmvrvcur.md), RCTC can be used to better understand the market cycle as it identifies the ralationship between the network's overall cost basis (CapRealUSD) relative to the USD amount issued to miners by the protocol (RevAllTimeUSD). &#x20;
* When evaluating market tops, RCTC provides a view on the realization of profits relative to the liquidity that is being issued to miners.
* Miners are speculators as they are naturally exposed to the price of the currency they are mining. As such, they collectively make buy or sell decisions that ultimately impact the market.

## Chart

![](../../.gitbook/assets/coin\_metrics\_network\_chart\(2\).png)

## Interpretation

* This metric fundamentally showcases the impact of miner liquity in the overall market. When the USD value of miner income is low relative to what is being realized on-chain, this could be interpreted as a sign of market tops.
* This metric could also be interpreted as the profit margin that might be realized by miners as it showcases the gap between profit taking.
* Historically, a threshold of 10 has been indicative of market tops as a wide profit margins are being realized relative to the USD value being issued to miners.

## Asset-Specific Details

Only applicable to assets for which we have RevAllTimeUSD and CapRealUSD.

## Release History

* Release Version: NDP 5.0 (August, 2021)

## See Also:

* [MCRC (Market Cap / Realized Cap)](mcrc.md)
* [MVRV (Market Cap / Realized Market Cap)](../market/capmvrvcur.md)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/CapMVRVFF" %}
