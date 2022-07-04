# 1 Year Current Supply Velocity, Adj

## Definition

The ratio of the adjusted value transferred (i.e., the aggregate "size" of all transfers) in the trailing 1 year divided by the current supply on that day. It can be thought of as a rate of turnover -- the number of times that an average native unit has been transferred in the past 1 year.

| Name                                | MetricID     | Category     | Subcategory | Type  | Unit          | Interval |
| ----------------------------------- | ------------ | ------------ | ----------- | ----- | ------------- | -------- |
| 1 Year Current Supply Velocity, Adj | VelCurAdj1yr | Transactions | Velocity    | Ratio | Dimensionless | 1 year   |

## Details

* [Xfer'd Val, Adj (native units)](txtfrvaladjntv.md) for trailing 1 year / [Current Supply (native units)](../supply/splycur.md)

## Chart

![https://charts.coinmetrics.io/network-data/#576](../../.gitbook/assets/Velocity\_1\_Yr,\_Adjusted.png)

## Release History

* Released in the 1.0 release of NDP

## Interpretation

Velocity​ is a measurement of the rate at which an asset is exchanged. It can be thought of as a rate of turnover, or, in other words, the number of times that an average unit of an asset has been transferred within the last year. In the above chart, we calculate velocity by dividing BTC’s adjusted transfer value over the past year (which is the total amount of cryptoasset transferred) by BTC’s total supply. Historically BTC’s velocity has increased during a rising bull cycle as on-chain activity increases, and has dipped following both the 2013 and 2017 price peaks. If velocity starts to slow dramatically, it could be read as a sign that the bull phase is reaching its end.

## See Also

* [1 Year Current Supply Velocity](velcur1yr.md)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/VelCurAdj1yr" %}
