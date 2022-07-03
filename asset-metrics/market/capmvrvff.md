# Free Float MVRV (Free Float Market Cap / Realized Market Cap)

## Definition

The ratio of the free float market capitalization (CapMrktFFUSD) to the sum "realized" USD value of the current supply (CapRealUSD).

| Name                                                          | IMetricD  | Category | Subcategory           | Type  | Unit          | Interval |
| ------------------------------------------------------------- | --------- | -------- | --------------------- | ----- | ------------- | -------- |
| Free Float MVRV (Free Float Market Cap / Realized Market Cap) | CapMVRVFF | Market   | Market Capitalization | Ratio | Dimensionless | 1 day    |

## Details

* This metric provides an important adjustment to the how [MVRV](capmvrvcur.md) is calculated.
* It improves upon the Market Value numerator of the MVRV formula (Market Cap/Realized Cap) by proving a more accurate representation of liquidity via CapMrktFFUSD.
* For more details on the significance of this improvement, please refer to the following blog post [Introducing Free Float Supply](https://coinmetrics.io/introducing-free-float-supply/)

## Chart

![](<../../.gitbook/assets/Screen Shot 2021-05-24 at 2.57.27 PM.png>)

## Asset-Specific Details

Only applicable to assets for which we have Free Float Supply (SplyFF) data available.

## Release History

* Release Version: NDP-EOD 4.8 (Nov, 2020)

## Interpretation

Market value to realized value (MVRV) has historically been one of the most reliable on-chain indicators of bitcoin market tops and bottoms. MVRV is calculated by dividing bitcoin’s market capitalization by its [realized capitalization](https://coinmetrics.io/realized-capitalization/). Realized capitalization can also be thought of as a gross approximation of bitcoin’s aggregate cost basis. In our variant of the MVRV calculation, we use free float market capitalization which is calculated using [liquid supply as opposed to total supply](https://coinmetrics.substack.com/p/coin-metrics-state-of-the-network-7d0).

Historically, a high ratio of market capitalization to realized capitalization has signaled that bitcoin price was near a local maximum, while a low ratio has indicated that price is near a local minimum. The few times that MVRV has dropped below one have historically been some of the best times to buy bitcoin. An increasing MVRV indicates that current sentiment is increasing fast relative to estimated aggregate cost basis, while decreasing MVRV signals the opposite.

## See Also

* [MVRV (Market Cap / Realized Market Cap)](capmvrvcur.md)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/CapMVRVFF" %}
