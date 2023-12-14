# USD Denominated Closing Price

## Definition

The price of the asset denominated in U.S. Dollars.&#x20;

| Name                          | MetricID | Category | Subcategory | Type | Unit | Interval              |
| ----------------------------- | -------- | -------- | ----------- | ---- | ---- | --------------------- |
| USD Denominated Closing Price | PriceUSD | Market   | Price       | NA   | USD  | 1 day, 1block, 1 hour |

## Details

* This metric is available in both daily and block frequencies. The daily frequency represents the price as of the end of the day in UTC time. The block frequency represents the price at the time the block was added to the blockchain.\

* This metric is identical to `ReferenceRate` and `ReferenceRateUSD` but with different timestamp conventions. Please see the frequently asked questions below for more information on this topic.\

* This price is computed using our CM Reference Rates. Please see our [CM Prices Overview](../../market-data/reference-rates-overview.md) for more information on methodology and policies.

## Example

A sample of the `PriceUSD` metric for Bitcoin with daily frequency is shown below:

```
{
  "data" : [ {
    "asset" : "btc",
    "time" : "2023-03-18T00:00:00.000000000Z",
    "PriceUSD" : "26985.7359915254"
  }, {
    "asset" : "btc",
    "time" : "2023-03-19T00:00:00.000000000Z",
    "PriceUSD" : "28185.2043319696"
  }, {
    "asset" : "btc",
    "time" : "2023-03-20T00:00:00.000000000Z",
    "PriceUSD" : "27834.3361090006"
  }, {
    "asset" : "btc",
    "time" : "2023-03-21T00:00:00.000000000Z",
    "PriceUSD" : "28172.7950558153"
  }, {
    "asset" : "btc",
    "time" : "2023-03-22T00:00:00.000000000Z",
    "PriceUSD" : "27341.5571297487"
  }
}
```

A sample of the `PriceUSD` metric for Bitcoin with block frequency is shown below:

```
{
  "data" : [ {
    "block_hash" : "000000000000000000061ade334ac0403c9473001639a16d4ff93bb822d30e92",
    "parent_block_hash" : "00000000000000000003c4583ecf8f90eefc404e8fb42e035649b7ed3010936d",
    "height" : "782143",
    "asset" : "btc",
    "time" : "2023-03-23T13:33:46.000000000Z",
    "PriceUSD" : "27520.25"
  }, {
    "block_hash" : "000000000000000000063ca1e45712d631ae9daa0bca98fd2d42229471d5abd6",
    "parent_block_hash" : "000000000000000000061ade334ac0403c9473001639a16d4ff93bb822d30e92",
    "height" : "782144",
    "asset" : "btc",
    "time" : "2023-03-23T13:36:23.000000000Z",
    "PriceUSD" : "27493.35"
  }, {
    "block_hash" : "000000000000000000040f8e246619bea33b4e22a4f797daa78ef721c727885f",
    "parent_block_hash" : "000000000000000000063ca1e45712d631ae9daa0bca98fd2d42229471d5abd6",
    "height" : "782145",
    "asset" : "btc",
    "time" : "2023-03-23T13:48:09.000000000Z",
    "PriceUSD" : "27404.86"
  }, {
    "block_hash" : "0000000000000000000391940aa48790413a38ec3834d299a05eaaa797f2336b",
    "parent_block_hash" : "000000000000000000040f8e246619bea33b4e22a4f797daa78ef721c727885f",
    "height" : "782146",
    "asset" : "btc",
    "time" : "2023-03-23T13:49:45.000000000Z",
    "PriceUSD" : "27384.94"
  }, {
    "block_hash" : "000000000000000000006b582725ac8e609305e3b5643afe0a92205220cf7fa6",
    "parent_block_hash" : "0000000000000000000391940aa48790413a38ec3834d299a05eaaa797f2336b",
    "height" : "782147",
    "asset" : "btc",
    "time" : "2023-03-23T14:20:06.000000000Z",
    "PriceUSD" : "27463"
  }
}
```

* **`asset`**: The ID of the asset.\

* **`time`**: The reference rate time in ISO 8601 date-time format.\

* **`PriceUSD`**: The published reference rate value in U.S. Dollars.\

* **`block_hash`**: The hash of the block.\

* **`parent_block_hash`**: The hash of the parent block.\

* **`height`**: The block height.

## Release History

* Released in the version 1.0 release of NDP

## Availability for Assets

Please see our Coin Metrics Coverage below for our asset coverage universe.

{% embed url="https://coverage.coinmetrics.io/asset-metrics/PriceUSD" %}
