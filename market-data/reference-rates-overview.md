# CM Prices Overview

Coin Metrics publishes a collection of prices for a set of cryptocurrencies and fiat currencies consisting of the Coin Metrics Reference Rates ("CM Reference Rates") and the Coin Metrics Principal Market Prices ("CM Principal Market Prices"), which are collectively referred to as the Coin Metrics Prices ("CM Prices").

Our coverage universe consists of over 640 assets and utilize a transparent and rules-based [methodology](methodologies/coin-metrics-prices-methodology.md). Our prices are robust to manipulation and are derived from high quality constituent markets and are governed by our [policies](methodologies/coin-metrics-prices-policies.md).

## Data Available for CM Reference Rates

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



## CM Prices Methodology

The CM Prices are collectively governed by rules-based methodologies described in [Coin Metrics Prices Methodology](https://docs.coinmetrics.io/market-data/methodologies/coin-metrics-prices-methodology) which describes our Market Selection Framework, a systematic method of producing a unique set of constituent markets for each asset, our data sources, calculation algorithm, and contingency rules.

{% content-ref url="methodologies/coin-metrics-prices-methodology.md" %}
[coin-metrics-prices-methodology.md](methodologies/coin-metrics-prices-methodology.md)
{% endcontent-ref %}
