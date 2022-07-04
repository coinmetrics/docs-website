# 10 Year Expected Supply (native units)

## Definition

The sum of all native units counting current supply and including all those expected to be issued over the next 10 years from that day if the current known continuous issuance schedule is followed. Future expected hard-forks that will change the continuous issuance are not considered until the day they are activated/enforced.

| Name                                   | MetricID       | Category | Subcategory      | Type | Unit         | Interval |
| -------------------------------------- | -------------- | -------- | ---------------- | ---- | ------------ | -------- |
| 10 Year Expected Supply (native units) | SplyExpFut10yr | Supply   | Future Expected  | Sum  | Native units | 10 years |

## Details

* Expected future supply is computed by extrapolating the behavior of the currently active monetary policy.
* Even if future changes in monetary policy are announced, they are only taken into account once they are enforced by the protocol.
* For some assets, estimating this number relies on too many assumptions (staking ratio, etc.), in which case it is not computed.

## Release History

* Released in the 1.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/SplyExpFut10yr" %}
