# CM Prices Overview

Coin Metrics publishes a collection of prices for a set of cryptocurrencies and fiat currencies consisting of the Coin Metrics Reference Rates ("CM Reference Rates") and the Coin Metrics Principal Market Prices ("CM Principal Market Prices"), which are collectively referred to as the Coin Metrics Prices ("CM Prices").

Our coverage universe consists of over [800 assets](https://coverage.coinmetrics.io/asset-metrics/ReferenceRate) and utilizes a transparent and rules-based [methodology](methodologies/coin-metrics-prices-methodology.md). Our prices are robust to manipulation and are derived from high quality constituent markets and are governed by our [policies](methodologies/coin-metrics-prices-policies.md).

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

{% content-ref url="../asset-metrics/market/referenceratebtc.md" %}
[referenceratebtc.md](../asset-metrics/market/referenceratebtc.md)
{% endcontent-ref %}

{% content-ref url="../asset-metrics/market/referencerateeth-1.md" %}
[referencerateeth-1.md](../asset-metrics/market/referencerateeth-1.md)
{% endcontent-ref %}

## Data Available for CM Principal Market Prices

The CM Principal Market Price is the price of an asset quoted in U.S. dollars derived from the asset's principal market, the market with the most trading volume or activity.

We offer both the principal market price and the identity of the principal market in separate metrics below.

{% content-ref url="../asset-metrics/market/principal_market_price_usd.md" %}
[principal\_market\_price\_usd.md](../asset-metrics/market/principal\_market\_price\_usd.md)
{% endcontent-ref %}

{% content-ref url="../asset-metrics/market/principal_market_usd.md" %}
[principal\_market\_usd.md](../asset-metrics/market/principal\_market\_usd.md)
{% endcontent-ref %}

## Data Available on On-Chain Oracles

We also publish the CM Reference Rates to Pyth Network, an on-chain oracle that publishes financial market data to multiple blockchains. Now decentralized applications or off-chain applications needing a reliable pricing source via an on-chain oracle can consume our CM Reference Rates. For more information, please contact Coin Metrics through [our website](https://coinmetrics.io/contact/) or at [info@coinmetrics.io](mailto:info@coinmetrics.io).

## CM Prices Documents

The CM Prices are collectively governed by policies described in [Coin Metrics Prices Policies](https://docs.coinmetrics.io/market-data/methodologies/coin-metrics-prices-policies) which describes the administration, oversight, conflicts of interest, material changes and terminations, recalculations, internal controls, complaints, record retention, and compliance policies.

{% content-ref url="methodologies/coin-metrics-prices-policies.md" %}
[coin-metrics-prices-policies.md](methodologies/coin-metrics-prices-policies.md)
{% endcontent-ref %}

The CM Prices are collectively governed by rules-based methodologies described in [Coin Metrics Prices Methodology](https://docs.coinmetrics.io/market-data/methodologies/coin-metrics-prices-methodology) which describes our Market Selection Framework, a systematic method of producing a unique set of constituent markets for each asset, our data sources, calculation algorithm, and contingency rules.

{% content-ref url="methodologies/coin-metrics-prices-methodology.md" %}
[coin-metrics-prices-methodology.md](methodologies/coin-metrics-prices-methodology.md)
{% endcontent-ref %}
