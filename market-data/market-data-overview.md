# Market Data Overview

The [CM Market Data Feed](https://coinmetrics.io/market-data-feed/) (MDF) provides access to historical and real-time data from the world’s leading centralized and decentralized (Labs) spot and derivatives crypto exchanges. We offer a wide range of harmonized datasets such as trades, candles, order book snapshots, futures-specific data types, and options-specific data types. We also offer metrics at the asset, exchange, exchange-asset, pair, and institution level.&#x20;

Our data is available at several different levels: asset, exchange, market, asset pair, exchange-asset pair, and institution. Our coverage universe consists of 3k+ assets, 39 exchanges, 21k+ spot markets, 10k+ futures markets, 14k+ options markets, 4k+ asset pairs, and one institution.&#x20;

## Data Available at Market Level&#x20;

Many of our data types are available at the market level. We define a market as a specific listed pair or derivatives contract that trades on a specific exchange, like `coinbase-btc-usd-spot` or `binance-BTCUSDT-future` or `deribit-BTC-16MAY21-58000-C-option`. The market coverage can be found by querying our [`/catalog/markets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogMarkets) or [`/catalog-all/markets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllMarkets) API endpoints.

Data available at the market level is served through the API endpoints below, which are described in the pages linked in this section:&#x20;

* [`/catalog/markets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogMarkets) and [`/catalog-all/markets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllMarkets)
* [`/timeseries/market-trades`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketTrades)
* [`/timeseries/market-openinterest`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketOpenIntereset)
* [`/timeseries/market-liquidations`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketLiquidations)
* [`/timeseries/market-funding-rates`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketFundingRates)
* [`/timeseries/market-orderbooks`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketOrderbooks)
* [`/timeseries/market-quotes`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketQuotes)
* [`/timeseries/market-candles`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketCandles)
* [`/timeseries/market-contract-prices`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketContractPrices)
* [`/timeseries/market-implied-volatility`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketImpliedVolatility)
* [`/timeseries/market-greeks`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketGreeks)

{% content-ref url="../market-data-timeseries/market-metadata.md" %}
[market-metadata.md](../market-data-timeseries/market-metadata.md)
{% endcontent-ref %}

{% content-ref url="market-trades.md" %}
[market-trades.md](market-trades.md)
{% endcontent-ref %}

{% content-ref url="market-open-interest.md" %}
[market-open-interest.md](market-open-interest.md)
{% endcontent-ref %}

{% content-ref url="futures-liquidations.md" %}
[futures-liquidations.md](futures-liquidations.md)
{% endcontent-ref %}

{% content-ref url="futures-funding-rates.md" %}
[futures-funding-rates.md](futures-funding-rates.md)
{% endcontent-ref %}

{% content-ref url="market-order-book.md" %}
[market-order-book.md](market-order-book.md)
{% endcontent-ref %}

{% content-ref url="market-quotes.md" %}
[market-quotes.md](market-quotes.md)
{% endcontent-ref %}

{% content-ref url="market-candles.md" %}
[market-candles.md](market-candles.md)
{% endcontent-ref %}

{% content-ref url="../market-data-timeseries/market-contract-prices.md" %}
[market-contract-prices.md](../market-data-timeseries/market-contract-prices.md)
{% endcontent-ref %}

{% content-ref url="market-implied-volatility.md" %}
[market-implied-volatility.md](market-implied-volatility.md)
{% endcontent-ref %}

{% content-ref url="market-greeks.md" %}
[market-greeks.md](market-greeks.md)
{% endcontent-ref %}

{% content-ref url="market-data-faqs.md" %}
[market-data-faqs.md](market-data-faqs.md)
{% endcontent-ref %}

## Metrics Available at Market Level

Coin Metrics calculates several metrics for markets such as `coinbase-btc-usd-spot` and `binance-BTCUSDT-future`. The asset coverage can be found by querying our [`/catalog/market-metrics`](https://docs.coinmetrics.io/api/v4#operation/getCatalogMarketMetrics) or [`/catalog-all/market-metrics`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllMarketMetrics) API endpoints.

Metrics available at the market level are available through the [`/timeseries/market-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketMetrics) API endpoint and specific metrics are described in the pages linked in this section:&#x20;

{% content-ref url="../market-metrics/liquidations/" %}
[liquidations](../market-metrics/liquidations/)
{% endcontent-ref %}

{% content-ref url="../market-metrics/liquidity/" %}
[liquidity](../market-metrics/liquidity/)
{% endcontent-ref %}

## Metrics Available at Asset Level&#x20;

Coin Metrics calculates several metrics for assets such as `btc` and `eth`. The asset coverage can be found by querying our [`/catalog/assets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAssets) or [`/catalog-all/assets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllAssets) API endpoints.

Metrics available at the asset level are available through the [`/timeseries/asset-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesAssetMetrics) API endpoint and specific metrics are described in the pages linked in this section:&#x20;

{% content-ref url="../asset-metrics/market/referencerateusd.md" %}
[referencerateusd.md](../asset-metrics/market/referencerateusd.md)
{% endcontent-ref %}

{% content-ref url="../asset-metrics/market/referencerateeur.md" %}
[referencerateeur.md](../asset-metrics/market/referencerateeur.md)
{% endcontent-ref %}

{% content-ref url="../asset-metrics/open-interest/" %}
[open-interest](../asset-metrics/open-interest/)
{% endcontent-ref %}

{% content-ref url="../asset-metrics/volume/" %}
[volume](../asset-metrics/volume/)
{% endcontent-ref %}

## Metrics Available at Exchange Level&#x20;

Coin Metrics calculates several metrics for exchanges such as `coinbase`, `binance`, and `deribit`. The exchange coverage can be found by querying our [`/catalog/exchanges`](https://docs.coinmetrics.io/api/v4#operation/getCatalogExchanges) or [`/catalog-all/exchanges`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllExchanges) API endpoints.

Metrics available at the exchange level are available through the [`/timeseries/exchange-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesExchangeMetrics) API endpoint and specific metrics are described in the pages linked in this section:&#x20;

{% content-ref url="../exchange-metrics/open-interest/" %}
[open-interest](../exchange-metrics/open-interest/)
{% endcontent-ref %}

{% content-ref url="../exchange-metrics/volume/" %}
[volume](../exchange-metrics/volume/)
{% endcontent-ref %}

## Metrics Available at Exchange-Asset Pair Level&#x20;

Coin Metrics calculates several metrics for exchange-asset pairs such as `coinbase-btc`, `binance-eth`, and `deribit-usdt`. The exchange coverage can be found by querying our [`/catalog/exchange-assets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogExchangeAssets) or [`/catalog-all/exchange-assets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllExchangeAssets) API endpoints.

Metrics available at the exchange-asset level are available through the [`/timeseries/exchange-asset-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesExchangeAssetMetrics) API endpoint and specific metrics are described in the pages linked in this section:&#x20;

{% content-ref url="../exchange-asset-metrics/basis/" %}
[basis](../exchange-asset-metrics/basis/)
{% endcontent-ref %}

{% content-ref url="../exchange-asset-metrics/liquidations.md" %}
[liquidations.md](../exchange-asset-metrics/liquidations.md)
{% endcontent-ref %}

{% content-ref url="../exchange-asset-metrics/open-interest.md" %}
[open-interest.md](../exchange-asset-metrics/open-interest.md)
{% endcontent-ref %}

{% content-ref url="../exchange-asset-metrics/volume.md" %}
[volume.md](../exchange-asset-metrics/volume.md)
{% endcontent-ref %}

## Metrics Available at Asset Pair Level&#x20;

Coin Metrics calculates several metrics for asset pairs such as `btc-usd` and `eth-usd`. The institution coverage can be found by querying our [`/catalog/pairs`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAssetPairs) or [`/catalog-all/pairs`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllAssetPairs) API endpoints.

Metrics available at the asset pair level are

&#x20;available through the [`/timeseries/pair-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesPairMetrics) API endpoint and specific metrics are described in the pages linked in this section:&#x20;

{% content-ref url="../pair-metrics/pair-open-interest/" %}
[pair-open-interest](../pair-metrics/pair-open-interest/)
{% endcontent-ref %}

{% content-ref url="../pair-metrics/pair-volume/" %}
[pair-volume](../pair-metrics/pair-volume/)
{% endcontent-ref %}

## Metrics Available at Institution Level&#x20;

Coin Metrics calculates several metrics for institutions such as `grayscale`. The institution coverage can be found by querying our [`/catalog/institutions`](https://docs.coinmetrics.io/api/v4#operation/getCatalogInstitutions) or [`/catalog-all/institutions`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllInstitutions) API endpoints.

Metrics available at the institution level is available through the [`/timeseries/institution-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesInstitutionMetrics) API endpoint and specific metrics are described in the pages linked in this section:&#x20;

{% content-ref url="../institution-metrics/grayscale/" %}
[grayscale](../institution-metrics/grayscale/)
{% endcontent-ref %}
