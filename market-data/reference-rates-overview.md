# CM Prices Overview

Coin Metrics publishes a collection of prices for a set of cryptocurrencies and fiat currencies consisting of the Coin Metrics Reference Rates ("CM Reference Rates") and the Coin Metrics Principal Market Prices ("CM Principal Market Prices"), which are collectively referred to as the Coin Metrics Prices ("CM Prices").

Our coverage universe consists of over 640 assets and utilize a transparent and rules-based [methodology](methodologies/coin-metrics-prices-methodology.md). Our prices are robust to manipulation and are derived from high quality constituent markets and are governed by our [policies](methodologies/coin-metrics-prices-policies.md).

## Data Available for CM Reference Rates

The CM Reference Rates represent the reference rate of one unit of the asset quoted in U.S. dollars or other currency.

The CM Reference Rates supports multiple frequencies. The daily and hourly frequencies utilize one calculation methodology and the minute, second, and 200 millisecond frequencies ("real-time frequencies") utilize a separate calculation methodology.

Please note that this metric is served through both the [/timeseries/asset-metrics](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesAssetMetrics) HTTP endpoint and the [/timeseries-stream/asset-metrics](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesStreamAssetMetrics) websocket endpoint. The HTTP endpoint supports the frequencies 1d, 1h, 1m, and 1s. The websocket endpoint supports the frequencies 1s and 200ms.

{% content-ref url="../asset-metrics/market/referencerateusd.md" %}
[referencerateusd.md](../asset-metrics/market/referencerateusd.md)
{% endcontent-ref %}

{% content-ref url="../asset-metrics/market/referencerateeur.md" %}
[referencerateeur.md](../asset-metrics/market/referencerateeur.md)
{% endcontent-ref %}

{% content-ref url="../asset-metrics/market/referencerateeth.md" %}
[referencerateeth.md](../asset-metrics/market/referencerateeth.md)
{% endcontent-ref %}

{% content-ref url="../asset-metrics/market/referencerateeth-1.md" %}
[referencerateeth-1.md](../asset-metrics/market/referencerateeth-1.md)
{% endcontent-ref %}

## Data Available for Principal Market Prices



## CM Prices Methodology

The CM Prices are collectively governed by rules-based methodologies described in [Coin Metrics Prices Methodology](https://docs.coinmetrics.io/market-data/methodologies/coin-metrics-prices-methodology) which describes our Market Selection Framework, a systematic method of producing a unique set of constituent markets for each asset, our data sources, calculation algorithm, and contingency rules.

{% content-ref url="methodologies/coin-metrics-prices-methodology.md" %}
[coin-metrics-prices-methodology.md](methodologies/coin-metrics-prices-methodology.md)
{% endcontent-ref %}
