---
description: /timeseries/index-constituents
---

# Index Constituents

## **Definition**

An index constituent is a member of an index.  For multi-asset crypto indexes, a constituent is a cryptoasset.  

| **Name** | **Category** | **Subcategory** | **Type** | **Unit** | **Interval** |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Index constituents | Index | Constituents | Index data | n/a | Hourly |

## Details

* Certain indexes consist of multiple index constituents. Such indexes weight constituents by one or more factors to determine the composition of the index. For instance, market capitalization weighted indexes weight index constituents by their adjusted free float market capitalization. For each index that utilizes this approach, the index constituent’s data concept lists the constituents and their weights at regular intervals. 
* Index constituents and weights are calculated once an hour, every hour, including on weekends and holidays. 
* Single asset indexes only have a single constituent, so no data will be returned for this endpoint.

## **Example**

A sample of the index constituents data for the CMBI10 is shown below:  

![](../.gitbook/assets/0%20%281%29.png)

* index:  The ID of the index.   
* time: The reference rate time in ISO 8601 date-time format.
* asset:  The ID of the index constituent.
* weight: The index constituent weight.

## Resource history

Adjusted Free Float Methodology

* Release Version: v1.0 \(Jul 2020\)  - Methodology launch.

CMBI Multi Asset Series 

* Release Version: v1.0 \(Sep 2020\)  - Methodology launch and release of CMBI10, CMBI10E, CMBI10EX, and CMBIBE 

## **Availability**

Community and pro index availability does not differ.  Community is available via HTTP API only, is limited to 1,000 API requests per 10 minutes per IP address and showcases the last 60 days of history. 

