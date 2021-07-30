# Trusted Volume, 1 Hour

## Definition

The sum of all volume from the spot markets of a set of trusted exchanges in units of U.S. dollars.[  
](https://docs.coinmetrics.io/info/metrics/volume_trusted_spot_usd_1d)

| Name | MetricID | Category | Subcategory | Type | Unit | Interval |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Trusted Volume, 1 Hour | volume\_trusted\_spot\_usd\_1hr | Market | Volume | NA | USD | 1d |

## Release History

* Release Version. Reference Rates v1.0 \(Jan 27, 2021\) - initial version

## Interpretation

Fake trading volume is a persistent problem on crypto exchanges. With little regulatory oversight, it can be difficult to determine whether reported volume numbers are accurate or exaggerated. At Coin Metrics, we’ve taken a data driven approach to the problem and offer a trusted volume metric to help identify legitimate trading volume. Our trusted volume metric is an aggregation of the reported volume from exchanges that we consider the most accurate and trustworthy. This is based on a combination of both quantitative and qualitative features. Our framework for measuring the reporting quality of an exchange is broken down into three broad categories: volume correlation, web traffic analytics and qualitative features. Each of these three categories culminates in a pass/fail test. Exchanges that pass all three measures are included in our trusted volume set of metrics. The current set of trusted volume metrics consider spot markets only and do not include futures or options markets.

## See Also

* [Trusted Volume](volume_trusted_spot_usd_1d.md)

## Availability for Assets

{% embed url="https://docs.coinmetrics.io/info/metrics/volume\_trusted\_spot\_usd\_1h" %}

