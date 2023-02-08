# Liquidation Sell Orders (Units)

## Definition

The sum of all reported volume in native units of sell orders that were used to close long positions under liquidation for a specific market in our coverage universe.

| Name                                             | MetricID                                        | Category     | Subcategory | Type | Unit         | Interval |
| ------------------------------------------------ | ----------------------------------------------- | ------------ | ----------- | ---- | ------------ | -------- |
| Reported Liquidation Sell Orders (Units), 5 Min  | liquidations\_reported\_future\_sell\_units\_5m | Liquidations | Futures     | Sum  | Native Units | 5m       |
| Reported Liquidation Sell Orders (Units), 1 Hour | liquidations\_reported\_future\_sell\_units\_1h | Liquidations | Futures     | Sum  | Native Units | 1h       |
| Reported Liquidation Sell Orders (Units), 1 Day  | liquidations\_reported\_future\_sell\_units\_1d | Liquidations | Futures     | Sum  | Native Units | 1d       |

## Details

Our reported liquidations metric is an aggregation of the reported liquidations from an exchange.

## Examples

A sample of the daily reported liquidation sell orders for the Binance BTCUSDT futures market is shown below:

| market                 | time                | liquidations\_reported\_future\_sell\_units\_1d |
| ---------------------- | ------------------- | ----------------------------------------------- |
| binance-BTCUSDT-future | 2022-01-01 00:00:00 | 60.012                                          |
| binance-BTCUSDT-future | 2022-01-02 00:00:00 | 114.786                                         |
| binance-BTCUSDT-future | 2022-01-03 00:00:00 | 177.809                                         |
| binance-BTCUSDT-future | 2022-01-04 00:00:00 | 386.542                                         |

* market. The IDs of the markets.
* time. The time in ISO 8601 date-time format.
* liquidations\_reported\_future\_sell\_units\_1d. The reported volume of liquidation sell orders in native units.

## Release History

* Release Version. Market Data Feed 2.6 (July 2022)&#x20;
