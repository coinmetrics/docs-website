---
description: /timeseries/index-levels
---

# Index Levels

## **Definition**

Index levels represent the level of an index. 

**Dictionary**

| **Name** | **Category** | **Subcategory** | **Type** | **Unit** | **Interval** |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Index levels | Index | Level | Index data | n/a | 1d, 1d-ny-close, 1d-sg-close, 1h, 15s |

## **Details**

* For more information on the various indexes and what the various index levels represent, please consult the CMBI Single Asset Series Methodology, the CMBI Market Cap Series Methodology, and the CMBI Mining Series Methodology. 
* Note: 1d-sg-close is 5pm Singapore

## **Example**

A sample of the daily levels for the CMBI10 is shown below:

![Source: CM CMBI](../.gitbook/assets/0%20%287%29.png)

* index:  The ID of the index.   
* time: The reference rate time in ISO 8601 date-time format.
* level:  The index value.

## **Release History**

CMBI Single Asset Series 

* Release Version:  v1.0 \(January 2020\) - Methodology launch and release of CMBIBTC, CMBIBTCT, CMBIETH and CMBIETHT

CMBI Multi Asset Series 

* Release Version: v1.0 \(Sep 2020\)  - Methodology launch and release of CMBI10, CMBI10E, CMBI10EX, and CMBIBE 

CMBI Mining Series

* Release Version: v1.0 \(May 2020\) - Methodology launch and release of CMBIWORK and CMBIHASH

## **Availability**

Community and pro index availability does not differ.  Community is available via HTTP API only, is limited to 1,000 API requests per 10 minutes per IP address and only showcases the last 24 hours of history for the 1 hour, 1 min and 15 second rates. 

