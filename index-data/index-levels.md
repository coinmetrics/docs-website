---
description: /timeseries/index-levels
---

# Index Levels

## **Definition**

Index levels represent the level of an index.&#x20;

## **Details**

For more information on the various indexes and what the various index levels represent, please consult the [CMBI Single Asset Series Methodology](https://coinmetrics.io/cmbi-single-asset-methodology/), the [CMBI Multi Asset Series Methodology](https://coinmetrics.io/cmbi-multi-asset-series-methodology/), the [CMBI Momentum Series Methodology](https://coinmetrics.io/cmbi-momentum-series-methodology/) and the [CMBI Mining Series Methodology](https://coinmetrics.io/cmbi-multi-asset-series-methodology/).&#x20;

Coin Metrics produces index values at the following frequencies:&#x20;

* `1d`: Daily closing levels at 00:00 UTC. \

* `1d-ny-close`: Daily closing levels at 16:00 New York time. \

* `1d-sg-close`: Daily closing levels at 17:00 Singapore time.\

* `1h`: Hourly closing levels every hour. \

* `15s`: Intraday levels every 15 seconds.&#x20;

## **Example**

A sample of the daily levels for the CMBI10 from our [`/timeseries/index-levels`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesIndexLevels) API endpoint is  shown below.&#x20;

```
{
  "data": [
    {
      "time": "2020-09-20T00:00:00.000000000Z",
      "index": "CMBI10",
      "level": "1118.132"
    },
    {
      "time": "2020-09-21T00:00:00.000000000Z",
      "index": "CMBI10",
      "level": "1096.141"
    }
  ]
}
```

* **`index`**: The ID of the index.   \

* **`time`**: The index time in ISO 8601 date-time format.\

* **`level`**: The index value.

## **Release History**

### CMBI Single Asset Series&#x20;

* **Version 1.0 on January 2020**: Methodology launch and release of CMBIBTC, CMBIBTCT, CMBIETH and CMBIETHT.\

* **Version 1.1 on March 2021**: Added CMBILTC.\

* **Version 1.2 on September 2021**: Added CMBISOL.

### CMBI Multi Asset Series&#x20;

* **Version 1.0 on September 2020**: Methodology launch and release of CMBI10, CMBI10E, CMBI10EX, and CMBIBE.&#x20;

### CMBI Mining Series

* **Version 1.0 on May 2020**: Methodology launch and release of CMBIWORK and CMBIHASH.

### CMBI Momentum Series

* **Version 1.0 on June 2020**: Methodology launch and release of CMBI10M.&#x20;

## **Availability**

The previous 24 hours of sub-daily frequencies and the full history of daily frequencies is available through our community API.  Community data is available via HTTP API only and is limited to 1,000 API requests per 10 minutes per IP address. All of our index levels is available through our professional API with higher rate limits.&#x20;

Index levels are available for the indexes listed below.&#x20;

### **Single Asset Series**

| **Index Ticker**                                         | **Index Name**             | Start Date |
| -------------------------------------------------------- | -------------------------- | ---------- |
| [CMBIBTC](https://cmbi-indexes.coinmetrics.io/cmbibtc)   | CMBI Bitcoin               | 2010-07-18 |
| [CMBIBTCT](https://cmbi-indexes.coinmetrics.io/cmbibtct) | CMBI Bitcoin Total Return  | 2010-07-18 |
| [CMBIETH](https://cmbi-indexes.coinmetrics.io/cmbieth)   | CMBI Ethereum              | 2015-08-08 |
| [CMBIETHT](https://cmbi-indexes.coinmetrics.io/cmbietht) | CMBI Ethereum Total Return | 2015-08-08 |
| [CMBILTC](https://cmbi-indexes.coinmetrics.io/cmbiltc)   | CMBI Litecoin              | 2013-04-01 |
| [CMBISOL](https://cmbi-indexes.coinmetrics.io/cmbisol)   | CMBI Solana                | 2020-04-11 |

### **Multi Asset Series**

| **Index Ticker**                                         | **Index Name**            | Start Date |
| -------------------------------------------------------- | ------------------------- | ---------- |
| [CMBI10](https://cmbi-indexes.coinmetrics.io/cmbi10)     | CMBI 10                   | 2017-01-03 |
| [CMBI10E](https://cmbi-indexes.coinmetrics.io/cmbi10e)   | CMBI Even                 | 2017-01-03 |
| [CMBI10EX](https://cmbi-indexes.coinmetrics.io/cmbi10ex) | CMBI 10 Excluding Bitcoin | 2017-01-03 |
| [CMBIBE](https://cmbi-indexes.coinmetrics.io/cmbibe)     | CMBI Bitcoin and Ethereum | 2015-08-08 |
| [CMBI10M](https://cmbi-indexes.coinmetrics.io/cmbi10m)   | CMBI Momentum             | 2017-01-09 |

### **Mining Series**

| **Index Ticker**                                         | **Index Name**             | **Start Date** |
| -------------------------------------------------------- | -------------------------- | -------------- |
| [CMBIHASH](https://cmbi-indexes.coinmetrics.io/cmbihash) | CMBI Bitcoin Hash Rate     | 2015-01-01     |
| [CMBIWORK](https://cmbi-indexes.coinmetrics.io/cmbiwork) | CMBI Bitcoin Observed Work | 2015-01-02     |
