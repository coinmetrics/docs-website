# Reported Future Open Interest

## Definition

The sum of all reported future open interest from all futures markets containing the specified pair in units of U.S. dollars.

| Name                          | Metric                                | Category      | Subcategory | Type | Unit | Frequency |
| ----------------------------- | ------------------------------------- | ------------- | ----------- | ---- | ---- | --------- |
| Reported Future Open Interest | open\_interest\_reported\_future\_usd | Open Interest | Future      | Sum  | USD  | 1h, 1d    |

## Details

Our reported future open interest metric is an aggregation of the reported future open interest for all futures markets containing the specified pair in CM's coverage universe. Covered exchanges can be found [here](../../exchanges/all-exchanges.md).

We use the open interest we collect for markets as input into the calculation of this metric. For more information on our market-level open interest data, please see the page below.

{% content-ref url="../../market-data/market-open-interest.md" %}
[market-open-interest.md](../../market-data/market-open-interest.md)
{% endcontent-ref %}

## Release History

* [**CM MDF v2.4 on September 1, 2021**](https://coinmetrics.io/cm-market-data-feed-v2-4-release-notes/): Added open interest for futures markets on Bybit. Added open interest for options markets on Deribit. Extended open interest for Ethereum markets on CME. Created several open interest metrics. Added enhanced open interest deduplication logic.

## Availability for Pairs

{% embed url="https://coverage.coinmetrics.io/pair-metrics/open_interest_reported_future_usd" %}

## See Also

* [Market Metadata](../../market-data-timeseries/market-metadata.md)\

* [Market Open Interest](../../market-data/market-open-interest.md)

