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

*   **Version 1.2 on September 2021**: Added CMBISOL.&#x20;


* **Version 1.3 on February 2022**: Added CMBIEOS and CMBIXTZ.\

* **Version 1.4 on March 2022**: Added CMBISAND and CMBIMANA.\

* **Version 1.5 on May 2022**: Added CMBIAAVE, CMBIALGO, CMBIAPE, CMBIAVAX, CMBIATOM, CMBILINK, CMBIDOT, and CMBIUNI.\

* **Version 1.6 on June 2022**: Added CMBIADA and CMBIBAT.\


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
| [CMBIEOS](https://indexes.coinmetrics.io/cmbieos)        | CMBI EOS                   | 2017-06-29 |
| [CMBIXTZ](https://indexes.coinmetrics.io/cmbixtz)        | CMBI Tezos                 | 2017-06-24 |
| [CMBIMANA](https://indexes.coinmetrics.io/cmbimana)      | CMBI Decentraland          | 2017-08-25 |
| [CMBISAND](https://indexes.coinmetrics.io/cmbisand)      | CMBI The Sandbox           | 2020-08-15 |
| [CMBIUNI](https://indexes.coinmetrics.io/cmbiuni)        | CMBI Uniswap               | 2021-09-18 |
| [CMBILINK](https://indexes.coinmetrics.io/cmbilink)      | CMBI Chainlink             | 2017-09-29 |
| [CMBIAAVE](https://indexes.coinmetrics.io/cmbiaave)      | CMBI Aave                  | 2020-10-10 |
| [CMBIAPE](https://indexes.coinmetrics.io/cmbiape)        | CMBI Apecoin               | 2022-04-01 |
| [CMBIATOM](https://indexes.coinmetrics.io/cmbiatom)      | CMBI Cosmos                | 2019-04-23 |
| [CMBIAVAX](https://indexes.coinmetrics.io/cmbiavax)      | CMBI Avalanche             | 2020-09-23 |
| [CMBIALGO](https://indexes.coinmetrics.io/cmbialgo)      | CMBI Algorand              | 2019-06-22 |
| [CMBIDOT](https://indexes.coinmetrics.io/cmbidot)        | CMBI Polkadot              | 2021-03-12 |
| [CMBIBAT](https://indexes.coinmetrics.io/cmbibat)        | CMBI Basic Attention Token | 2017-10-06 |
| [CMBIADA](https://indexes.coinmetrics.io/cmbimana)       | CMBI Cardano               | 2017-12-01 |

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
