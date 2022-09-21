# Mean Tx Fee per Block Weight (native units)

## Definition

The mean transaction fee per weight unit in that interval in native units. Weight is a dimensionless measure of a block’s “size”. It is only applicable for chains that use SegWit (segregated witness).

| Name                                        | MetricID       | Category         | Subcategory | Type | Unit         | Interval |
| ------------------------------------------- | -------------- | ---------------- | ----------- | ---- | ------------ | -------- |
| Mean Tx Fee per Block Weight (native units) | FeeWghtMeanNtv | Fees and Revenue | Fees        | Mean | Native units | 1 day    |

## Details

* For more details on SegWit, check the [Bitcoin Wiki Entry](https://en.bitcoin.it/wiki/Segregated\_Witness)

## Chart

<figure><img src="../../.gitbook/assets/BTC_Block_Time___Avg_Tx_Fees_ (2).png" alt=""><figcaption></figcaption></figure>

## Asset-Specific Details

* Only relevant to cryptoassets that have implemented Segregated Witness (SegWit)

## Examples

* During the BTC mining ban in China in 2021, we saw an influx of miners turn off their operations so the block interval time increased significantly due to less hash power on the network. In effect, because less miners were online, we saw a spike in the mean transaction fee per byte since less miners were available to include transactions in the blocks, therefore transactions costs were more competitive.

## Release History

* Release Version: NDP-EOD 4.8 (Nov, 2020)

## Interpretation

* The Segwit upgrade replaced the concept of block size with block weight . While Bitcoins block weight is 4 MB, the mean block time is still slower than other chains such as Litecoin resulting

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/FeeWghtMeanNtv" %}
