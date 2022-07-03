# Market Cap (USD)

## Definition

The sum USD value of the current supply. Also referred to as network value or market capitalization.

| Name             | MetricID      | Category | Subcategory           | Type    | Unit | Interval |
| ---------------- | ------------- | -------- | --------------------- | ------- | ---- | -------- |
| Market Cap (USD) | CapMrktCurUSD | Market   | Market Capitalization | Product | USD  | 1 day    |

## Details

* Computed as SplyCur \* PriceUSD
* The price used is the daily close price

## Asset-Specific Details

* For XRP, amounts under escrow are included in current supply

## Release History

* Released in the 1.0 release of NDP

## Interpretation

Informally called ‘market cap,’ our formulation differs in that we do consider all historically issued supply and does not exclude illiquid supply held in escrow or foundation accounts. In this respect, our formulation of this metric diverges from other sources who discount coins held in escrow or treasuries.

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/CapMrktCurUSD" %}
