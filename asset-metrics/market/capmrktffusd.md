# Free Float Market Cap (USD)

## Definition

The sum USD value of the free float supply. Also referred to as free float network value or free float market capitalization.

| Name                        | MetricID     | Category | Subcategory           | Type    | Unit | Interval |
| --------------------------- | ------------ | -------- | --------------------- | ------- | ---- | -------- |
| Free Float Market Cap (USD) | CapMrktFFUSD | Market   | Market Capitalization | Product | USD  | 1 day    |

## Details

* Free Float Market Capitalization is a measure of the market value of an asset’s supply that is issued and available to market participants. This excludes supply that is held by company insiders, controlling investors and long term strategic holders.
* This metric is calculated by multiplying SplyFF by PriceUSD.
* For more details on Free Float Supply, please refer to our blog post [Introducing Free Float Supply](https://coinmetrics.io/introducing-free-float-supply/)

## Asset-Specific Details

* Only applicable to assets for which we have Free Float Supply (SplyFF) data available.
* ETH Free Float Supply includes tokens on the Consensus Layer and Execution Layer

## Release History

* Release Version: NDP-EOD 4.8 (Nov, 2020)

## See Also

* [Free Float Supply](../supply/splyff.md)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/CapMrktFFUSD" %}
