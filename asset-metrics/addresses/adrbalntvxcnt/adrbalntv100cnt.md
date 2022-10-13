# Addr Cnt of Bal ≥ 100 (native units)

The sum count of unique addresses holding at least 100 native units as of the end of that day. Only native units are considered (e.g., an address with less than 100 ETH but with more than 100 in ERC-20 tokens would not be considered).

| Name                                 | MetricID        | Category  | Subcategory | Type | Unit      | Interval |
| ------------------------------------ | --------------- | --------- | ----------- | ---- | --------- | -------- |
| Addr Cnt of Bal ≥ 100 (native units) | AdrBalNtv100Cnt | Addresses | Balance     | Sum  | Addresses | 1 day    |

## Chart

<figure><img src="../../../.gitbook/assets/Bitcoin_Supply_Distribution_by_Adr_Balance (6).png" alt=""><figcaption></figcaption></figure>

## Examples

* As the price of BTC increase, the number of Addresses holding 100 BTC will be lower, as 100 units of BTC will be worth significantly more than . When the price of BTC is 20k, 100 units is worth about $2 million. One could look at this metric to better understand whales and their accumulation patterns.

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/AdrBalNtv100Cnt" %}
