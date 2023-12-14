# BTC Denominated Closing Price

## Definition

The price of the asset denominated in Bitcoin units.&#x20;

| Name                  | MetricID | Category | Subcategory | Type | Unit | Interval      |
| --------------------- | -------- | -------- | ----------- | ---- | ---- | ------------- |
| BTC Denominated Price | PriceBTC | Market   | Price       | NA   | BTC  | 1 day, 1 hour |

## Details

* This metric is available in both daily and block frequencies. The daily frequency represents the price as of the end of the day in UTC time. The block frequency represents the price at the time the block was added to the blockchain.\

* This metric is identical to `ReferenceRateBTC` but with different timestamp conventions. Please see the frequently asked questions below for more information on this topic.\

* This price is computed using our CM Reference Rates. Please see our [CM Prices Overview](../../market-data/reference-rates-overview.md) for more information on methodology and policies.

## Example

A sample of the `PriceBTC` metric for Ethereum with daily frequency is shown below:

```
{
  "data" : [ {
    "asset" : "eth",
    "time" : "2023-03-18T00:00:00.000000000Z",
    "PriceBTC" : "0.06538140200862749"
  }, {
    "asset" : "eth",
    "time" : "2023-03-19T00:00:00.000000000Z",
    "PriceBTC" : "0.06392540140433825"
  }, {
    "asset" : "eth",
    "time" : "2023-03-20T00:00:00.000000000Z",
    "PriceBTC" : "0.062418493975669356"
  }, {
    "asset" : "eth",
    "time" : "2023-03-21T00:00:00.000000000Z",
    "PriceBTC" : "0.06407211604389325"
  }, {
    "asset" : "eth",
    "time" : "2023-03-22T00:00:00.000000000Z",
    "PriceBTC" : "0.06357608845321447"
  }
}
```

A sample of the `PriceBTC` metric for Ethereum with block frequency is shown below:

```
{
  "data" : [ {
    "block_hash" : "cf604b220ea0f3fba67244573f33a36919b6cf2ff7ea210a86377d229bb9b0d8",
    "parent_block_hash" : "152ca610b2f68643c43dd82dcdb79519ee26f490cf29c14456ac23f9489eaa1b",
    "height" : "16890992",
    "asset" : "eth",
    "time" : "2023-03-23T15:01:35.000000000Z",
    "PriceBTC" : "0.06447664"
  }, {
    "block_hash" : "7f279840f5f4cf23a7a6c880531f1dd2858b2a6ad220dc7123600c064c700db9",
    "parent_block_hash" : "cf604b220ea0f3fba67244573f33a36919b6cf2ff7ea210a86377d229bb9b0d8",
    "height" : "16890993",
    "asset" : "eth",
    "time" : "2023-03-23T15:01:47.000000000Z",
    "PriceBTC" : "0.0644538"
  }, {
    "block_hash" : "2051a0dba9018764e8469f4f5de4845c5c7333e34b84e258f088f6b7ceb5369e",
    "parent_block_hash" : "7f279840f5f4cf23a7a6c880531f1dd2858b2a6ad220dc7123600c064c700db9",
    "height" : "16890994",
    "asset" : "eth",
    "time" : "2023-03-23T15:01:59.000000000Z",
    "PriceBTC" : "0.0644743"
  }, {
    "block_hash" : "fb45b96b4527c535a957754ef81b603e878da31d05f20010497914177cd0c2b0",
    "parent_block_hash" : "2051a0dba9018764e8469f4f5de4845c5c7333e34b84e258f088f6b7ceb5369e",
    "height" : "16890995",
    "asset" : "eth",
    "time" : "2023-03-23T15:02:11.000000000Z",
    "PriceBTC" : "0.06449479"
  }, {
    "block_hash" : "e5f672e9accdcedc0c319de63037a25102b47efdfd794bf4e3e5124bcc20b8c4",
    "parent_block_hash" : "fb45b96b4527c535a957754ef81b603e878da31d05f20010497914177cd0c2b0",
    "height" : "16890996",
    "asset" : "eth",
    "time" : "2023-03-23T15:02:23.000000000Z",
    "PriceBTC" : "0.06443347"
  }
}
```

* **`asset`**: The ID of the asset.\

* **`time`**: The reference rate time in ISO 8601 date-time format.\

* **`PriceBTC`**: The published reference rate value in Bitcoin units.\

* **`block_hash`**: The hash of the block.\

* **`parent_block_hash`**: The hash of the parent block.\

* **`height`**: The block height.

## Release History

* Released in the version 1.0 release of NDP

## Availability for Assets

Please see our Coin Metrics Coverage below for our asset coverage universe.

{% embed url="https://coverage.coinmetrics.io/asset-metrics/PriceBTC" %}
