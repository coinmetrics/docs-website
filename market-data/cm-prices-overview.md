# CM Prices Overview

Coin Metrics publishes a collection of prices for a set of cryptocurrencies and fiat currencies consisting of the Coin Metrics Hourly Reference Rates, the Coin Metrics Real-Time Reference Rates, and the Coin Metrics Principal Market Prices, which are collectively referred to as the Coin Metrics Prices (“CM Prices”).

Our coverage universe consists of over 640 assets and utilize a transparent and rules-based [methodology](methodologies/coin-metrics-prices-methodology.md). Our prices are robust to manipulation and are derived from high quality constituent markets and are governed by our [policies](methodologies/coin-metrics-prices-policies.md).

## Data Available for Hourly Reference Rates and Real-Time Reference Rates

Please note that the following price metrics are served through both the [`/timeseries/asset-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesAssetMetrics) HTTP API endpoint and the [`/timeseries-stream/asset-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesStreamAssetMetrics) websocket endpoint.&#x20;

The HTTP endpoint supports the frequencies 1d, 1h, 1m, and 1s. The websocket endpoint supports the frequencies 1s and 200ms. Frequencies 1d and 1h use our Hourly Reference Rates. Frequencies 1m and 1s use our Real-Time Reference Rates.

{% content-ref url="../asset-metrics/market/referenceratesusd.md" %}
[referenceratesusd.md](../asset-metrics/market/referenceratesusd.md)
{% endcontent-ref %}

{% content-ref url="../asset-metrics/market/referencerateeur.md" %}
[referencerateeur.md](../asset-metrics/market/referencerateeur.md)
{% endcontent-ref %}

{% content-ref url="../asset-metrics/market/reference-rate-btc.md" %}
[reference-rate-btc.md](../asset-metrics/market/reference-rate-btc.md)
{% endcontent-ref %}

{% content-ref url="../asset-metrics/market/reference-rate-eth.md" %}
[reference-rate-eth.md](../asset-metrics/market/reference-rate-eth.md)
{% endcontent-ref %}

## Data Available for Principal Market Prices



## Methodologies

We have two reference rates methodologies. The Hourly Reference Rates Methodology is used to calculate the 1h and 1d frequencies. The Real-Time Reference Rates Methodology is used to calculate the 1m, 1s, and 200ms frequencies.

{% content-ref url="../methodologies/reference-rates/real-time-reference-rates-methodology.md" %}
[real-time-reference-rates-methodology.md](../methodologies/reference-rates/real-time-reference-rates-methodology.md)
{% endcontent-ref %}

{% content-ref url="../methodologies/reference-rates/hourly-reference-rates-methodology.md" %}
[hourly-reference-rates-methodology.md](../methodologies/reference-rates/hourly-reference-rates-methodology.md)
{% endcontent-ref %}
