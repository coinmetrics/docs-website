# Liquidation Buy Orders (USD)

## Definition

The sum of all reported volume in U.S. dollars of buy orders that were used to close short positions under liquidation for a specific market in our coverage universe.

| Name                                          | MetricID                                     | Category     | Subcategory | Type | Unit | Interval |
| --------------------------------------------- | -------------------------------------------- | ------------ | ----------- | ---- | ---- | -------- |
| Reported Liquidation Buy Orders (USD), 5 Min  | liquidations\_reported\_future\_buy\_usd\_5m | Liquidations | Futures     | Sum  | USD  | 5m       |
| Reported Liquidation Buy Orders (USD), 1 Hour | liquidations\_reported\_future\_buy\_usd\_1h | Liquidations | Futures     | Sum  | USD  | 1h       |
| Reported Liquidation Buy Orders (USD), 1 Day  | liquidations\_reported\_future\_buy\_usd\_1d | Liquidations | Futures     | Sum  | USD  | 1d       |

## Details

Our reported liquidations metric is an aggregation of the reported liquidations from an exchange.

## Examples

A sample of the daily reported liquidation buy orders for the Binance BTCUSDT futures market is shown below:

| market                 | time                | liquidations\_reported\_future\_buy\_usd\_1d |
| ---------------------- | ------------------- | -------------------------------------------- |
| binance-BTCUSDT-future | 2022-01-01 00:00:00 | 3998040.835345                               |
| binance-BTCUSDT-future | 2022-01-02 00:00:00 | 3813877.390613                               |
| binance-BTCUSDT-future | 2022-01-03 00:00:00 | 3458893.546343                               |
| binance-BTCUSDT-future | 2022-01-04 00:00:00 | 5097647.77909                                |

* market. The IDs of the markets.
* time. The time in ISO 8601 date-time format.
* liquidations\_reported\_future\_buy\_usd\_1d. The reported volume of liquidation buy orders in units of U.S. dollars.

## Release History

* Release Version. Market Data Feed 2.6 (July 2022)&#x20;
