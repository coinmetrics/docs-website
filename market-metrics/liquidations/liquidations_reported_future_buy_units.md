# Liquidation Buy Orders (Units)

## Definition

The sum of all reported volume in native units of buy orders that were used to close short positions under liquidation for a specific market in our coverage universe.

| Name                                            | MetricID                                       | Category     | Subcategory | Type | Unit         | Interval |
| ----------------------------------------------- | ---------------------------------------------- | ------------ | ----------- | ---- | ------------ | -------- |
| Reported Liquidation Buy Orders (Units), 5 Min  | liquidations\_reported\_future\_buy\_units\_5m | Liquidations | Futures     | Sum  | Native Units | 5m       |
| Reported Liquidation Buy Orders (Units), 1 Hour | liquidations\_reported\_future\_buy\_units\_1h | Liquidations | Futures     | Sum  | Native Units | 1h       |
| Reported Liquidation Buy Orders (Units), 1 Day  | liquidations\_reported\_future\_buy\_units\_1d | Liquidations | Futures     | Sum  | Native Units | 1d       |

## Details

Our reported liquidations metric is an aggregation of the reported liquidations from an exchange.

## Examples

A sample of the daily reported liquidation buy orders for the Binance BTCUSDT futures market is shown below:

| market                 | time                | liquidations\_reported\_future\_buy\_units\_1d |
| ---------------------- | ------------------- | ---------------------------------------------- |
| binance-BTCUSDT-future | 2022-01-01 00:00:00 | 84.918                                         |
| binance-BTCUSDT-future | 2022-01-02 00:00:00 | 80.595                                         |
| binance-BTCUSDT-future | 2022-01-03 00:00:00 | 74.007                                         |
| binance-BTCUSDT-future | 2022-01-04 00:00:00 | 109.399                                        |

* market. The IDs of the markets.
* time. The time in ISO 8601 date-time format.
* liquidations\_reported\_future\_buy\_units\_1d. The reported volume of liquidation buy orders in native units.

## Release History

* Release Version. Market Data Feed 2.6 (July 2022)&#x20;
