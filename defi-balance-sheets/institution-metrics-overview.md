---
description: /timeseries/defi-balance-sheets
---

# DeFi Balance Sheets Overview

{% hint style="warning" %}
The DeFi balance sheets endpoint has been released as a [CM Labs](https://docs.coinmetrics.io/cm-labs) project. Breaking changes may be introduced with minimal notice. Please exercise caution given the endpoint's experimental nature.
{% endhint %}

Coin Metrics collects various data from DeFi protocols and we serve this data in the form of DeFi balance sheets from our  [`/timeseries/defi-balance-sheets`](https://docs.coinmetrics.io/api/v4#operation/getDefiBalanceSheets) API endpoint.&#x20;

## Institution Coverage

The protocols covered in our DeFi balance sheets endpoint are listed below:

| Protocol |     Ticker    | Start Date |
| -------- | :-----------: | :--------: |
| Aave V2  | `aave_v2_eth` | 2020-12-01 |

## Endpoint Response

The [`/timeseries/defi-balance-sheets`](https://docs.coinmetrics.io/api/v4#operation/getDefiBalanceSheetshttps://docs.coinmetrics.io/api/v4#operation/getDefiBalanceSheets) endpoint returns time series data for each DeFi protocol requested.  The response is formatted as follows:

| Field                        | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `defi_protocol`              | DeFi protocol name.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `block_height`               | Height of the underlying blockchain's block (number of confirmed blocks since Genesis block).                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| `time`                       | The time in ISO 8601 date-time format. Always with nanoseconds precision.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| `assets_total_usd`           | The valuation of total assets, in USD value, that have been allocated to the protocol.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `assets_total_count`         | The count of unique assets allocated to the protocol.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `assets`                     | An array of summary info associated with each asset allocated to the protocol, including _asset_, which represents the ticker of the constituent asset; _total\_units_, which represents the total units of the constituent asset in this protocol; _total\_usd_, which represents the total USD value that asset represents; and _total\_share_, which represents the ratio of total USD valuation of that asset relative to the total USD valuation of the assets allocated to the protocol.                                                                           |
| `loans_lent_total_usd`       | <p>The amount, in USD, that the protocol has lent out to users of the platform. Protocols</p><p>like AAVE loan user deposits to borrowers. As a reminder, our balance sheet takes the</p><p>perspective of the protocol itself. Since these loans are expected to be repaid to the</p><p>protocol, they fall into the assets column as a type receivable.</p>                                                                                                                                                                                                            |
| `tvl_total_usd`              | <p>The Total Value Locked (TVL) of the protocol. TVL differs from Total Assets, as it</p><p>represents the assets that are within the protocol and have not been lent out. In other</p><p>words, the difference between TVL and Total Assets represents the aggregate value of</p><p>loans made by the protocol.</p>                                                                                                                                                                                                                                                     |
| `liabilities_total_usd`      | <p>The total value, in USD, of liability tokens issued by the protocol. Liability tokens are</p><p>issued to users that have deposited cryptoassets into the protocol, similar to capital deposited by customers at a bank. These are tokens exclusively minted by DeFi</p><p>protocols and usually follow specific nomenclature standards. For example, AAVE</p><p>issues a-tokens like aUSDC, whereas compound issues c-tokens like cUSDC.</p>                                                                                                                         |
| `liabilities_total_count`    | <p>The total count of different types of liabilities issued by the protocol. For example, if</p><p>AAVE were to exclusively issue aUSDC and aUSDT, this field would return a value of 2.</p>                                                                                                                                                                                                                                                                                                                                                                             |
| `liabilities`                | <p>An array showcasing summary information associated with each liability issued by the</p><p>protocol, including <em>asset</em>, which represents the ticker of the constituent liability;</p><p><em>total_units</em>, which represents the total units of the constituent asset in this protocol;</p><p><em>total_usd</em>, which represents the total USD value that asset represents; and <em>share</em>,</p><p>which represents the ratio of total USD valuation of that liability relative to the total USD valuation of the assets allocated to the protocol.</p> |
| `net_working_capital_usd`    | <p>Net Working Capital represents the difference between TVL (<em>tvl_total_usd</em>) and</p><p>Total Liabilities (<em>liabilities_total_usd</em>). This ratio can be interpreted as a</p><p>measure of the protocol’s ability to meet its short-term obligations, such as the</p><p>repayment of its liabilities (e.g. a-tokens).</p>                                                                                                                                                                                                                                   |
| `protocol_utilization_ratio` | <p>The Protocol Utilization Ratio represents the ratio of loans made by the protocol</p><p>(<em>loans_lent_total_usd</em>) divided by its liabilities (<em>liabilities_total_usd</em>). As such, it is intended to represent how much the protocol is being used. In lending protocols, for example, this metric would reflect how efficiently the protocol is generating loans with its deposited capital.</p>                                                                                                                                                          |
| `liquid_supply_ratio`        | <p>The Liquid Supply Ratio represents the ratio between TVL (<em>tvl_total_usd</em>) and Total</p><p>Liabilities (<em>liabilities_total_usd</em>). In lending protocols, for example, this can be</p><p>interpreted as the percentage of the supply allocated to the protocol that is liquid and</p><p>can be used for loans.</p>                                                                                                                                                                                                                                        |
| `current_ratio`              | <p>If users make the assumption that a DeFi lender's liabilities (deposited capital from</p><p>Aave users) can mostly be considered short-term liabilities, then the current ratio can be</p><p>conservatively approximated by TVL (<em>tvl_total_usd</em>) / Total Liabilities</p><p>(<em>liabilities_total_usd</em>), which is the same as the Liquid Supply Ratio above.</p>                                                                                                                                                                                          |
| `debt_to_assets_ratio`       | <p>The Debt to Assets Ratio represents the ratio between Total Liabilities</p><p>(<em>liabilities_total_usd</em>) and Total Assets (<em>assets_total_usd</em>). For many</p><p>protocols, especially lending platforms, this ratio is expected to always be close to 1</p><p>given the dynamics of DeFi loans.</p>                                                                                                                                                                                                                                                       |

&#x20;A sample of DeFi balance sheet data in json format is provided below.

```
{
  "data" : [ {
    "defi_protocol" : "protocol1",
    "block_height" : "15821368",
    "time" : "2022-10-25T00:00:00.000000000Z",
    "assets_total_usd" : "5206858775.8887",
    "assets_total_count" : "5",
    "liabilities_total_usd" : "5207569174.7343",
    "liabilities_total_count" : "4",
    "loans_lent_total_usd" : "1643900213.0442",
    "tvl_total_usd" : "3562958562.8445",
    "net_working_capital_usd" : "-1644610611.8898",
    "assets" : [ {
      "asset" : "asset1",
      "total_units" : "16642572.299665700155624691",
      "loans_lent_units" : "3034432.558303788296351088",
      "tvl_units" : "13608139.741361911859273603",
      "total_usd" : "9421036.866",
      "loans_lent_usd" : "1717733.3218",
      "tvl_usd" : "7703303.5442",
      "total_share" : "0.001809",
      "loans_lent_share" : "0.001045",
      "tvl_share" : "0.002162"
    }, {
      "asset" : "asset2",
      "total_units" : "3.451110208332495257",
      "tvl_units" : "3.451110208332495257"
    }, {
      "asset" : "asset3",
      "total_units" : "1745617.903650065714276",
      "tvl_units" : "1745617.903650065714276",
      "total_usd" : "148378761.035",
      "tvl_usd" : "148378761.035",
      "total_share" : "0.028497",
      "tvl_share" : "0.091645"
    }, {
      "asset" : "asset4",
      "total_units" : "82725.553558289864058706",
      "loans_lent_units" : "31738.572718926909253698",
      "tvl_units" : "50986.980839362954805008"
    }, {
      "asset" : "asset5",
      "total_units" : "924683.504980413732672045",
      "loans_lent_units" : "482347.607737316633044131",
      "tvl_units" : "442335.897243097099627914",
      "total_usd" : "1243286021.2045",
      "loans_lent_usd" : "648541944.1693",
      "tvl_usd" : "594744077.0352",
      "total_share" : "0.238779",
      "loans_lent_share" : "0.394514",
      "tvl_share" : "0.166924"
    } ],
    "liabilities" : [ {
      "asset" : "liability1",
      "total_units" : "16642568.377251250315561367",
      "total_usd" : "9421034.6455",
      "total_share" : "0.001809"
    }, {
      "asset" : "liability2",
      "total_units" : "3.451110208332495257"
    }, {
      "asset" : "liability3",
      "total_units" : "930352212.629909",
      "total_usd" : "930289317.7994",
      "total_share" : "0.298642"
    }, {
      "asset" : "liability4",
      "total_units" : "925062.111387555686554298",
      "total_usd" : "1243795077.6017",
      "total_share" : "0.238844"
    } ],
    "protocol_utilization_ratio" : "0.315676",
    "liquid_supply_ratio" : "0.684189",
    "current_ratio" : "0.684189",
    "debt_to_assets_ratio" : "1.000137"
  } ]
}
```
