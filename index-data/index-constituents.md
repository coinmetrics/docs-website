---
description: /timeseries/index-constituents
---

# Index Constituents

## **Definition**

An index constituent is a member of an index.  For multi-asset crypto indexes, a constituent is a cryptoasset. &#x20;

## Details

Certain indexes consist of multiple index constituents. Such indexes weight constituents by one or more factors to determine the composition of the index. For instance, market capitalization-weighted indexes weight index constituents by their adjusted free float market capitalization. For each index that utilizes this approach, the index constituent data contains the constituents and their weights.&#x20;

Index constituents and weights are calculated once an hour, every hour, including on weekends and holidays. Single asset indexes only have a single constituent, so no data will be returned for this endpoint. There are also no constituents for our CMBI Mining Series indexes.&#x20;

## **Example**

A sample of the constituents for the CMBI10 from our [`/timeseries/index-constituents`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesIndexConstituents) API endpoint is  shown below.&#x20;

```
{
  "data": [
    {
      "time": "2020-05-01T22:00:00.000000000Z",
      "index": "CMBI10",
      "constituents": [
        {
          "asset": "bch",
          "weight": "0.01887429752681492"
        },
        {
          "asset": "bsv",
          "weight": "0.01343767932475944"
        },
        {
          "asset": "btc",
          "weight": "0.747355794635124"
        },
        {
          "asset": "etc",
          "weight": "0.004565578678797349"
        },
        {
          "asset": "eth",
          "weight": "0.1351998514006912"
        },
        {
          "asset": "ltc",
          "weight": "0.01756776057810796"
        },
        {
          "asset": "xlm",
          "weight": "0.008757017272583251"
        },
        {
          "asset": "xmr",
          "weight": "0.006442672327610681"
        },
        {
          "asset": "xrp",
          "weight": "0.03769069726575187"
        },
        {
          "asset": "xtz",
          "weight": "0.01010865098975933"
        }
      ]
    }
  ]
}
```

* **`index`**:  The ID of the index. \

* **`time`**: The reference rate time in ISO 8601 date-time format. \

* **`asset`**:  The asset id of the index constituent.\

* **`weight`**: The index constituent weight.

## **Release History**

### Adjusted Free Float Methodology

* **Version 1.0 on July 2020**: Methodology launch.

### CMBI Multi Asset Series&#x20;

* **Version 1.0 on September 2020**: Methodology launch and release of CMBI10, CMBI10E, CMBI10EX, and CMBIBE.&#x20;

### CMBI Momentum Series

* **Version 1.0 on June 2020**: Methodology launch and release of CMBI10M.&#x20;

## **Availability**

The last 60 days of history is available through our community API.  Community data is available via HTTP API only and is limited to 10 API requests per 6 seconds per IP address. All of our index constituenst data is available through our professional API with higher rate limits.&#x20;

Index constituents are available for the indexes listed below.&#x20;

### **Multi Asset Series**

| **Index Ticker**                                         | **Index Name**            | Start Date |
| -------------------------------------------------------- | ------------------------- | ---------- |
| [CMBI10](https://cmbi-indexes.coinmetrics.io/cmbi10)     | CMBI 10                   | 2017-01-03 |
| [CMBI10E](https://cmbi-indexes.coinmetrics.io/cmbi10e)   | CMBI Even                 | 2017-01-03 |
| [CMBI10EX](https://cmbi-indexes.coinmetrics.io/cmbi10ex) | CMBI 10 Excluding Bitcoin | 2017-01-03 |
| [CMBIBE](https://cmbi-indexes.coinmetrics.io/cmbibe)     | CMBI Bitcoin and Ethereum | 2015-08-08 |
| [CMBI10M](https://cmbi-indexes.coinmetrics.io/cmbi10m)   | CMBI Momentum             | 2017-01-09 |
