---
description: /timeseries/index-levels
---

# Index Levels

## **Definition**

Index levels represent the level of an index.&#x20;

## **Details**

For more information on the various indexes and what the various index levels represent, please consult the [CMBI Single Asset Series Methodology](https://coinmetrics.io/cmbi-single-asset-methodology/), the [CMBI Multi Asset Series Methodology](https://coinmetrics.io/cmbi-multi-asset-series-methodology/), the [CMBI Momentum Series Methodology](https://coinmetrics.io/cmbi-momentum-series-methodology/), the [CMBI Mining Series Methodology](https://coinmetrics.io/cmbi-multi-asset-series-methodology/), and the [CMBI Total Market Series Methodology](https://coinmetrics.io/wp-content/uploads/2022/12/CMBI-Total-Market-Series-Methodology.pdf).&#x20;

Coin Metrics produces index values at the following frequencies:&#x20;

* `1d`: Daily closing levels at 00:00 UTC. \

* `1d-ny-close`: Daily closing levels at 16:00 New York time. \

* `1d-sg-close`: Daily closing levels at 17:00 Singapore time.\

* `1h`: Hourly closing levels every hour. \

*   `15s`: Intraday levels every 15 seconds.

    &#x20;
* `1s`: Intraday levels every 1 second.&#x20;

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

### CMBI Total Market Series

* **Version 1.0 on November 2022**: Methodology launch and release of CMBITM, CMBIAUE, CMBIBUE, CMBIBSE, CMBIDFIE, CMBIIFE, CMBIITE, CMBIMSE, CMBIMTAE, CMBISCPE. CMBISCE, CMBIVTCE, CMBIDEXE, CMBINSE, and CMBINFTE.&#x20;

## **Availability**

The previous 24 hours of sub-daily frequencies and the prior 30 days of daily frequencies are available through our community API.  Community data is available via HTTP API only and is limited to 10 API requests per 6 seconds per IP address. All of our index levels is available through our professional API with higher rate limits.&#x20;

Index levels are available for the indexes listed in our coverage tool:&#x20;

{% embed url="https://coverage.coinmetrics.io/indexes" %}
