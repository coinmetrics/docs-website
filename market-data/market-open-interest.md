---
description: /timeseries/market-openinterest
---

# Market Open Interest

## **Definition**

Open interest represents the number of contracts that are currently outstanding and not settled for a specific derivatives market.&#x20;

## Details

Each contract has a specified contract value that can be described by the size asset and contract size. For example, the contract value for `bitmex-XBTUSD-future` is `1 usd` and the contract value for `cme-BTCF1-future` is `5 btc`. For more information, please take a look at our page about [derivatives contract specifications](https://docs.coinmetrics.io/market-data/derivatives-contract-specifications). &#x20;

Coin Metrics collects open interest in units of number of contracts and in units of U.S. dollars at one minute snapshot frequency. We collect open interest snapshots from **future** and **option** markets from exchanges that are listed on our exchange coverage universe.&#x20;

## **Example**

A sample of the futures open interest data from the `binance-BTCUSDT-future` market from our  [`/timeseries/market-openinterest`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketOpenIntereset) API endpoint is provided below.&#x20;

```
{
  "data": [
    {
      "market": "binance-BTCUSDT-future",
      "time": "2020-08-05T23:05:00.000000000Z",
      "contract_count": "35074.075",
      "value_usd": "408810440.79225",
      "database_time": "2020-08-05T23:05:00.000000000Z",
      "exchange_time": "2020-08-05T23:05:00.000000000Z"
    },
    {
      "market": "binance-BTCUSDT-future",
      "time": "2020-08-05T23:06:00.000000000Z",
      "contract_count": "35061.142",
      "value_usd": "409113039.09552",
      "database_time": "2020-08-05T23:06:00.000000000Z",
      "exchange_time": "2020-08-05T23:06:00.000000000Z"
    }
  ]
}
```

* **`market`**:  The id of the market. Market ids use the following naming convention: `exchangeName-baseAsset-quoteAsset-spot` for spot markets, `exchangeName-futuresSymbol-future` for futures markets, and `exchangeName-optionsSymbol-option` for options markets. \

* **`time`**: The time at which Coin Metrics queried the open interest data from an exchange in ISO 8601 date-time format. Always with nanoseconds precision.\

* **`contract_count`**:  The open interest denominated in number of contracts.\

* **`value_usd`**:  The open interest denominated in U.S. dollars.\

* **`database_time`**:  The timestamp when the data was saved in the database in ISO 8601 date-time format with nanoseconds precision. Always with nanoseconds precision.\

* **`exchange_time`**:  The timestamp reported by the exchange.  Can be null if the exchange does not report a timestamp.

## Frequently Asked Questions

### **Why do some markets have snapshot frequency of one minute but other markets have a different snapshot frequency?**&#x20;

Most exchanges report their open interest in real-time and for these exchanges we collect open interest at one minute snapshot frequency. Binance only updates their open interest once every 15 minutes and CME only updates their open interest once a day, so for these two exchanges our snapshot frequency matches their update frequency.&#x20;

### **Is your open interest snapshot taken exactly on the minute?**&#x20;

For exchanges that report an actual timestamp that is not the time of the request (such as Binance and CME), our `time`  field is the exchange-reported time. For all other exchanges, we truncate the `time` field to the minute. We try to cycle our scrapers as close to the minute as possible, but most exchanges do not allow us to query the open interest at a specific timestamp. Therefore, if you require a more precise timestamp for exactly when open interest was measured, we recommend using the `database_time` field which represents the time that we saved it in the database.&#x20;

### **Do you have open interest metrics for assets, exchanges, asset pairs, or exchange-asset pairs?**&#x20;

Yes! We calculate various types of total open interest for assets like `btc`, exchanges like `binance`, asset pairs like `btc-usd`, and exchange-asset pairs like `binance-btc`. For more information, please take a look at our [open interest metrics](https://docs.coinmetrics.io/asset-metrics/open-interest).&#x20;

## Release History

* [**CM MDF v2.2 on December 2, 2020**](https://coinmetrics.io/cm-market-data-feed-futures-data-expansion/)**:** Added open interest for futures markets on Binance, Bitfinex,  BitMEX, Deribit, FTX, Huobi, Kraken, and OKEx.\

* &#x20;[**CM MDF v2.3 on April 25, 2021**](https://coinmetrics.io/cm-market-data-feed-v2-3-release-notes/): Added open interest for futures markets on CME. \

* &#x20;[**CM MDF v2.4 on September 1, 2021**](https://coinmetrics.io/cm-market-data-feed-v2-4-release-notes/): Added open interest for futures markets on Bybit. Added open interest for options markets on Deribit. Extended open interest for Ethereum markets on CME. Created several open interest metrics. Added enhanced open interest deduplication logic.&#x20;

## See Also

Coin Metrics also calculates several open interest metrics at the asset, exchange, and exchange-asset level. For instance, you could see the total open interest for a specific asset like `btc`, for a specific exchange like `binance` , or for a specific asset that trades on a specific exchange like `binance-btc`.

Please see the following pages on open interest below to learn more.

{% content-ref url="../asset-metrics/open-interest/" %}
[open-interest](../asset-metrics/open-interest/)
{% endcontent-ref %}

{% content-ref url="../exchange-metrics/open-interest/" %}
[open-interest](../exchange-metrics/open-interest/)
{% endcontent-ref %}

{% content-ref url="../exchange-asset-metrics/open-interest.md" %}
[open-interest.md](../exchange-asset-metrics/open-interest.md)
{% endcontent-ref %}

## **Availability**

The previous 24 hours of open interest data is available through our community API.  Community data is available via HTTP API only and is limited to 10 API requests per 6 seconds per IP address. All of our open interest data is available through our professional API with higher rate limits. The professional API supports trades data through both our HTTP API and websocket API.&#x20;

### Availability by Market Type

| Type    | Number of Markets |
| ------- | :---------------: |
| Futures |        4720       |
| Option  |        7163       |

### Availability by Exchange

| Exchange | Future Market Count | Option Market Count | Start Date |
| -------- | :-----------------: | :-----------------: | :--------: |
| Binance  |         207         |                     | 2020-07-27 |
| Bitfinex |          25         |                     | 2020-07-27 |
| BitMEX   |          86         |                     | 2020-07-27 |
| Bybit    |          24         |                     | 2021-05-01 |
| CME      |          61         |                     | 2017-12-19 |
| Deribit  |          67         |         7163        | 2020-07-27 |
| FTX      |         1027        |                     | 2020-07-27 |
| Huobi    |         1673        |                     | 2020-07-27 |
| Kraken   |          67         |                     | 2020-10-09 |
| OKEx     |         1483        |                     | 2020-07-27 |
