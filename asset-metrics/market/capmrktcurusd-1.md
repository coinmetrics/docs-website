# Estimate Market Cap (USD)

## Definition

The sum USD value of the circulating supply. Also referred to as network value or market capitalization. Circulating supply is reported by the projects or other derived sources.&#x20;

| Name                      | MetricID      | Category | Subcategory           | Type    | Unit | Interval |
| ------------------------- | ------------- | -------- | --------------------- | ------- | ---- | -------- |
| Estimate Market Cap (USD) | CapMrktEstUSD | Market   | Market Capitalization | Product | USD  | 1 day    |

## Details

* Computed as Circulating Supply \* PriceUSD
* The price used is the daily close price
* The circulating supply used is sourced through third party APIs

## Asset-Specific Details

* For ERC-20 assets, the circulating supply is sourced from EtherScan via CoinGecko
* Where available circulating supply was sourced from the projects circulating supply API end point via CoinGecko

## Interpretation

Informally called ‘market cap,’ our Estimate Market Cap aligns with the industry convention for market cap. We called this market cap, estimate because this is a reported amount and not sourced directly from what is seen on-chain.&#x20;

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/CapMrktEstUSD" %}
