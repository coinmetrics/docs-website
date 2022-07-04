# Bitfinex Withdrawals (USD)

## Definition

The sum USD value withdrawn from Bitfinex that day.

| Name                       | MetricID      | Category | Subcategory | Type | Unit | Interval       |
| -------------------------- | ------------- | -------- | ----------- | ---- | ---- | -------------- |
| Bitfinex Withdrawals (USD) | FlowOutBFXUSD | Exchange | Withdrawals | Sum  | USD  | 1 block, 1 day |

## Details

* Computed as FlowOutBFXNtv \* PriceUSD
* Native units are considered as withdrawn if they leave the control of an address we identify as being owned by an exchange.

## Asset-Specific Details

* This metric might not be available for all assets. Either that exchange doesn’t support this asset (BitMEX only trades in BTC for example), or we deemed that our coverage of the exchange was not complete enough to release the metric for it.
* For Bitcoin, this metric excludes the effect of change outputs:
*
  * If a transaction spends 100 BTC from exchange A but 90 BTC are sent back to it as change, the flow is -10 BTC, not -100 BTC.

## Release History

* Released in the 4.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/FlowOutBFXUSD" %}
