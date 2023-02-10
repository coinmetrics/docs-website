# Reference Rates Overview

CM Reference Rates provide prices calculated for over 550 assets quoted in U.S. dollars, Euro, Bitcoin, and Ethereum using a transparent and independent methodology. Our rates are robust to manipulation and are derived from high quality constituent markets per our[ Market Selection Framework](../methodologies/reference-rates/market-selection-framework.md).&#x20;

## Data Available at the Asset Level

Please note note that this metric is served through both the [`/timeseries/asset-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesAssetMetrics) HTTP API endpoint and the [`/timeseries-stream/asset-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesStreamAssetMetrics) websocket endpoint. The HTTP endpoint supports the frequencies 1d, 1h, 1m, and 1s. The websocket endpoint supports the frequencies 1s and 200ms.

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

## Methodologies

We have two reference rates methodologies. The Hourly Reference Rates Methodology is used to calculate the 1h and 1d frequencies. The Real-Time Reference Rates Methodology is used to calculate the 1m, 1s, and 200ms frequencies.

{% content-ref url="../methodologies/reference-rates/real-time-reference-rates-methodology.md" %}
[real-time-reference-rates-methodology.md](../methodologies/reference-rates/real-time-reference-rates-methodology.md)
{% endcontent-ref %}

{% content-ref url="../methodologies/reference-rates/hourly-reference-rates-methodology.md" %}
[hourly-reference-rates-methodology.md](../methodologies/reference-rates/hourly-reference-rates-methodology.md)
{% endcontent-ref %}
