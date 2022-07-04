# 10 Year Expected Supply, Adj (native units)

## Definition

This metric is an improved version of the legacy SplyExpFut10yr metric as it is better suited for use-cases that require a high degree of standardization, such as multi-asset indexes. As part of the v4.7 release, Coin Metrics has taken additional steps to harmonize the treatment of expected future supply across different token models. We have implemented these improvements in a this new metric; SplyExpFut10yrCMBI.

| Name                                        | MetricID           | Category | Subcategory     | Type | Unit         | Interval |
| ------------------------------------------- | ------------------ | -------- | --------------- | ---- | ------------ | -------- |
| 10 Year Expected Supply, Adj (native units) | SplyExpFut10yrCMBI | Supply   | Future Expected | Sum  | Native units | 10 years |

## Details

* Expected future supply is computed by extrapolating the behavior of the currently active monetary policy.
* The CMBI version of this metric takes extra steps to guarantee heuristics are uniformly applied to various cryptoassets.
* Only implemented and programmatically defined supply inflation levels are considered. Any proposed or speculative inflation changes are not included until they are implemented in the source code as historically delays and governance processes have hindered such changes in a protocol’s monetary policy. Even if future changes in monetary policy are announced, they are only taken into account once they are enforced by the protocol.
* Unless lost, burned, or vested on-chain beyond 10 years, all current on-chain supply will be deemed liquid supply in 10 years time. Coin Metrics has taken this approach to account for the unpredictability associated with determining what holders of restricted supply will do over the next 10 years. e assets, estimating this number relies on too many assumptions (staking ratio, etc..), in which case it is not computed.

## Release History

* Released in the 4.7 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/SplyCur" %}
