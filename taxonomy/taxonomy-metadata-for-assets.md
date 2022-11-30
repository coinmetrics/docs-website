---
description: /taxonomy-metadata/assets
---

# Taxonomy Metadata for Assets

## Definition

The asset taxonomy metadata provides the entire structure of the taxonomy via api. &#x20;

## Details

For more information on the asset taxonomy see the [datonomy product description](../reference-data/datonomy-overview.md) and [methodology](../reference-data/methodologies/) documents.

## Endpoint Response

The **Asset Taxonomy Metadata** endpoint returns a list of subsectors for the taxonomy version (or start/end time) requested.  Each subsector has the following fields:

| Field          | Description                                                                             |
| -------------- | --------------------------------------------------------------------------------------- |
| `class_id`     | Two digit code for the class                                                            |
| `class`        | First level of taxonomy describing the asset's fundamental purpose                      |
| `sector_id`    | Four digit code for the sector with the first two digits representing the class\_id     |
| `sector`       | Second level of taxonomy describing the asset's focus area within a class               |
| `subsector_id` | Six digit code for the subsector with the first four digits representing the sector\_id |
| `subsector`    | Third level of taxonomy describing the asset's specific product, service or function    |

A sample of the taxonomy metadata response for the is shown below.&#x20;

<pre><code>"data": [
<strong>{
</strong>    "taxonomy_version": "1.1",
    "taxonomy_start_time": "2021-06-13T00:00:00.000000000Z",
    "subsectors": [
        {
            "class_id": "10",
            "class": "Digital Currencies",
            "sector_id": "1010",
            "sector": "Specialized Coins",
<strong>            "subsector_id": "101010",
</strong>            "subsector": "Remittance Coins"
        },
        {
            "class_id": "10",
            "class": "Digital Currencies",
            "sector_id": "1010",
            "sector": "Specialized Cions",
            "subsector_id": "101020",
            "subsector": "Meme Coins"
        },
        {
            "class_id": "10",
<strong>            "class": "Digital Currencies",
</strong>            "sector_id": "1010",
            "sector": "Specialized Coins",
            "subsector_id": "101040",
            "subsector": "Privacy Coins"
        }
        ],
    "taxonomy_end_time": "2022-06-12T23:59:59.999999999Z"
}
</code></pre>
