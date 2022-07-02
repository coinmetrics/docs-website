# Bitfinex Deposits (USD)

## Definition

The sum USD value sent to Bitfinex that interval.

| Name                    | MetricID     | Category | Subcategory | Type | Unit | Interval       |
| ----------------------- | ------------ | -------- | ----------- | ---- | ---- | -------------- |
| Bitfinex Deposits (USD) | FlowInBFXUSD | Exchange | Deposits    | Sum  | USD  | 1 block, 1 day |

## Details

* Computed as FlowInBFXNtv \* PriceUSD
* Native units are considered as sent to an exchange if they are sent to an address we identify as being owned by an exchange.

## Asset-Specific Details

* This metric might not be available for all assets. Either that exchange doesn’t support this asset, or we deemed that our coverage of the exchange was not complete enough to release the metric for it.
* For Bitcoin, this metric excludes the effect of change outputs:
*
  * If a transaction sends 90 BTC to exchange A but also withdraws 50 BTC from it, the flow is +40 BTC, not +90 BTC and -50 BTC.

## Release History

* Released in the 4.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/FlowInBFXUSD" %}
