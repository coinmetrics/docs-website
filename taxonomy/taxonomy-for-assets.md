---
description: /taxonomy/assets
---

# Taxonomy for Assets

## **Definition**

The asset taxonomy classifies assets by primary use.&#x20;

## Details

For more information on the asset taxonomy see the [datonomy overview](../reference-data/datonomy-overview.md) and [methodology](../reference-data/methodologies/) documents.

## Endpoint Response

The **Taxonomy Assets** endpoint returns taxonomy data for each asset, version, class, sector or subsector requested.  The response is formatted as follows:

| Field                 | Description                                                                             |
| --------------------- | --------------------------------------------------------------------------------------- |
| `asset`               | Asset symbol                                                                            |
| `full name`           | Asset name                                                                              |
| `taxonomy_version`    | Version of the taxonomy                                                                 |
| `taxonomy_start_time` | Start time of the taxonomy version in ISO 8601 date-time format                         |
| `class_id`            | Two digit code for the class                                                            |
| `class`               | First level of taxonomy describing the asset's fundamental purpose                      |
| `sector_id`           | Four digit code for the sector with the first two digits representing the class\_id     |
| `sector`              | Second level of taxonomy describing the asset's focus area within a class               |
| `subsector_id`        | Six digit code for the subsector with the first four digits representing the sector\_id |
| `subsector`           | Third level of taxonomy describing the asset's specific product, service or function    |
| `taxonomy_end_time`   | End time of the taxonomy version in ISO 8601 date-time format                           |

## Example

A sample of the taxonomy response for  `axs` is  shown below.&#x20;

<pre><code>"data": [
{
<strong>    "asset": "axs",
</strong>    "full_name": "Axie Infinity",
    "taxonomy_version": "1.0",
    "taxonomy_start_time": "2010-07-19T00:00:00.000000000Z",
    "class_id": "20",
    "class": "Application",
    "sector_id": "2030",
    "sector": "Metaverse",
    "subsector_id": "203020",
    "subsector": "Gaming",
    "taxonomy_end_time": "2021-06-12T23:59:59.999999999Z"
},
</code></pre>

## Release History

* **Version 1.0 on November 4, 2022**: Methodology launch and release of initial version of the taxonomy\
