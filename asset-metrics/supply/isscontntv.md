# Coinbase Issuance (native units)

## Definition

The sum of native units issued that day. Only those native units that are issued by a protocol-mandated continuous emission schedule are included.

| Name                             | MetricID   | Category | Subcategory | Type | Unit         | Interval |
| -------------------------------- | ---------- | -------- | ----------- | ---- | ------------ | -------- |
| Coinbase Issuance (native units) | IssContNtv | Supply   | Issuance    | Sum  | Native units | 1 day    |

## Details

* Most protocols have a fixed monetary policy that describes how many native units must be issued per block. This metric tracks those policies.
* It includes founders and community rewards if their amounts are predictable.

## Asset-Specific Details

* For XLM, the inflation process is considered continuous issuance as it is protocol mandated and predictable.

## Release Details

* Released in the 1.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/IssContNtv" %}
