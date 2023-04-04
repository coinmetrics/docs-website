# Reported Tether-Margined Future Open Interest

## Definition

The sum of all reported future open interest from all tether-margined futures markets containing the specified pair in units of U.S. dollars. Tether-margined futures markets are futures markets where the margin currency is Tether.

| Name                                          | Metric                                                  | Category      | Subcategory | Type | Unit | Frequency |
| --------------------------------------------- | ------------------------------------------------------- | ------------- | ----------- | ---- | ---- | --------- |
| Reported Tether-Margined Future Open Interest | open\_interest\_reported\_future\_tether\_margined\_usd | Open Interest | Future      | Sum  | USD  | 1h, 1d    |

## Details

Our reported tether-margined future open interest metric is an aggregation of the reported future open interest for all tether-margined futures markets containing the specified pair in CM's coverage universe. Covered exchanges can be found [here](../../exchanges/all-exchanges.md).

We use the open interest we collect for markets as input into the calculation of this metric. For more information on our market-level open interest data, please see the page below.

{% content-ref url="../../market-data/market-open-interest.md" %}
[market-open-interest.md](../../market-data/market-open-interest.md)
{% endcontent-ref %}

## Release History

* [**CM MDF v2.4 on September 1, 2021**](https://coinmetrics.io/cm-market-data-feed-v2-4-release-notes/): Added open interest for futures markets on Bybit. Added open interest for options markets on Deribit. Extended open interest for Ethereum markets on CME. Created several open interest metrics. Added enhanced open interest deduplication logic.

## See Also

* [Futures Contract Specifications](../../market-data-timeseries/market-metadata.md)\

* [Market Open Interest](../../market-data/market-open-interest.md)

## Availability for Pairs

{% embed url="https://coverage.coinmetrics.io/pair-metrics/open_interest_reported_future_tether_margined_usd" %}

## See Also

* [Market Metadata](../../market-data-timeseries/market-metadata.md)
* [Market Open Interest](../../market-data/market-open-interest.md)
