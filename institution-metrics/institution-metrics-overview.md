---
description: /timeseries/institution-metrics
---

# Institution Metrics Overview

Coin Metrics collects various data from institutions and we serve this data in the form of institution metrics from our  [`/timeseries/institution-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesInstitutionMetrics) API endpoint. 

## Institution Coverage

The institution coverage can be found by querying our [`/catalog/institutions`](https://docs.coinmetrics.io/api/v4#operation/getCatalogInstitutions) or [`/catalog-all/institutions`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllInstitutions) API endpoints. The institutions are also listed below. Grayscale Investments is currently the only institution in our coverage universe. 

{% page-ref page="grayscale/" %}

## Endpoint Response

The [`/timeseries/institution-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesInstitutionMetrics) endpoint returns time series data for each institution and metric requested.  The response is formatted as follows:

| Field | Description |
| :--- | :--- |
| `institution` | Institution name. |
| `time` | The time in ISO 8601 date-time format. Always with nanoseconds precision. |
| `{metric}` | Metric value for the specific institution and timestamp. |

 A sample of the institution metrics data in json format is also provided below.

```text
{
  "data": [
    {
      "institution": "institution1",
      "time": "2020-09-28T00:00:00.000000000Z",
      "total_assets": "317000178.776577"
    },
    {
      "institution": "institution1",
      "time": "2020-09-29T00:00:00.000000000Z",
      "total_assets": "246153685.485477"
    },
    {
      "institution": "institution1",
      "time": "2020-09-30T00:00:00.000000000Z",
      "total_assets": "217972373.240482"
    },
    {
      "institution": "institution1",
      "time": "2020-10-01T00:00:00.000000000Z",
      "total_assets": "492203699.871197"
    }
  ]
}
```



