# API Basics

## API Versions

* \*\*\*\*[**API v4**](https://docs.coinmetrics.io/api/v4) **(stable)**

## API Access

### Free Tier (Community API)

Our community data can be accessed without an API key. Simply run queries against the`community-api.coinmetrics.io` endpoint. This data is available for free for non-commercial use under a [Creative Commons](https://creativecommons.org/licenses/by-nc/4.0/) license. See our [Terms of Use](https://coinmetrics.io/terms-of-use/) for more details.

### Paid Tier (Pro API)

Our professional data is available to institutions via an API key. Please [contact us](https://share.hsforms.com/15lLsB4n2Tl-Jj9MS7P2utA34tym) if you wish to purchase our institutional data.

## Coin Metrics API Standards

### Timestamps

Coin Metrics formats time in accordance with the ISO 8601 standard. As such, the following formats for time parameters in the query string are supported:

* 2020-03-13
* 20060120
* 2020-03-13T15:25:15Z
* 2020-03-13T15:25:15.12345789Z
* 2020-03-13T525.999Z

Note the **Z** suffix in requests is optional. All dates in the query parameters are in the UTC timezone by default. All responses are always in the UTC timezone and with nanoseconds precision.

### Number Format

All numbers in API responses are surrounded by quotes, which allows JavaScript clients to work with numbers that have more than 53 bits. The decimal separator is always a "dot". The number of decimal places is defined by blockchain/exchange and not modified by the API.

### Monetary Amount Formats

Monetary amounts are provided as strings and with the same order of magnitude as the one used for pricing. For Bitcoin, the primary format is the native BTC unit (e.g., 1 BTC, 0.29938 BTC) as opposed to any subformat, such as satoshis, which represent one hundred millionth of a Bitcoin.

## Pagination

Large lists may be split into pages. In accordance with Coin Metrics' API v4, page size has a default value of **100** and can be changed using a `page_size` parameter. The **maximum** page size supported is **10,000**.

If a response contains the `next_page_url` field at the top level of the JSON response, it means the client can request the next page of results by fetching the provided URL without any modifications.

## HTTP/REST API

Coin Metrics' API v4 API uses the HTTP/2 protocol.

## Rate limits

To ensure the quality of Coin Metrics services, our API is subject to rate limiting. If you reach the limit, the API will begin to return `429 Too Many Requests` HTTP response status. The API also provides `X-RateLimit-*` response headers formatted according to [https://tools.ietf.org/html/draft-polli-ratelimit-headers-03](https://tools.ietf.org/html/draft-polli-ratelimit-headers-03).

### Community API

The community version of API has a limit of 10 requests per 6 seconds sliding window for an **IP address**. It corresponds to 1.6 RPS.

### Paid Tier (Pro API)

The paid version of API has a limit of 6,000 requests per 20 seconds sliding window for an **API key**. It corresponds to 300 RPS.

## WebSocket

We use the default WS protocol ping/pong mechanism. There are some restarts occasionally because it goes through Cloudflare, so you should have some logic in place to automatically reconnect.&#x20;

## Backward Compatibility

Our API is versioned using [Semantic Versioning](https://semver.org/). The API version number convention is `major.minor.patch`. The notation rules are:

* Backward incompatible changes increase the major number.
* Backward compatible changes increase the minor number.
* Backward compatible bug fixes increase the patch number.

### Versioning

Major versions of the API are run in parallel. The choice of what major API version to use is up to the client, although clients are advised to use the highest stable version.

Major versions can be marked as either stable or unstable. As backward-incompatible changes can be introduced only in unstable or development major versions, no breakage is expected when using fixed, stable major API versions (and adhering to safety guidelines below).

New major API releases are to be added alongside old major API versions, so clients of old (stable) versions are not affected. Old major API versions may be gradually deprecated and removed, following a (generally long-term) deprecation schedule. This should give clients time to adapt their implementations to the new major version.

Minor and patch releases replace old minor/patch API versions, under the same major version. Old minor/patch API versions become inaccessible following these releases.

#### Unstable Major Versions

Recently introduced versions of the API may be explicitly labeled "unstable". Unstable API versions are fully tested, usable by clients, and have complete documentation. However, an unstable API version is not covered by the backward compatibility rules below and can receive arbitrary changes at any time without any warning. Unstable API versions should be used only for evaluation of new features. It is not advised to use unstable versions in production systems.

New major versions of the API are expected to be marked unstable, and after a period of stabilization and testing become permanently stable.

#### Development Major Versions

The newest version of the API may be explicitly labeled "development". Development API versions may receive arbitrary changes at any time and may also have wrong/incomplete implementation, documentation, or other critical issues. Generally, development API versions should be completely avoided, as there are no guarantees about how well it works, or whether it works at all.

### Backward Compatible Changes

A change is considered backward compatible when an API client built for an old version of the API still works with the new version. Hence, it is important that clients use correct assumptions about what details of the API they can rely on.

#### Changes considered backward-compatible (can be introduced in a minor or patch API version)

{% hint style="danger" %}
These changes can be introduced in minor or patch API versions. Follow the below recommendations to avoid broken integrations:

* Addition of a new API method. Do not rely on the absence of a specific URL path or API method.
* Addition of new constant-named fields to response structures of the existing API method. Do not rely on the absence of unknown fields in API response structures.
* Addition of a new optional request parameter to a method, given that its absence has the same meaning as it was before the change. Do not add unsupported request parameters to API calls - they are ignored while unsupported, but may suddenly become "supported".
* Making previously mandatory request parameters optional.
* Addition of new possible values for enum-typed request parameters of the API method.
* Changes in human-friendly strings (i.e. asset/metric names/definitions, error descriptions). Do not make decisions in your code based on human-friendly strings. These strings can be changed for reasons like fixing misspelling or style. Use fields designed to be "stable", e.g. error codes, etc.
* Adding/removing/changing available resources: assets, metrics, etc. Availability of specific assets/metrics/etc is not part of the API interface and not covered by this policy. You should use the discovery API methods to get an accurate list of available resources.
* Fixes which technically should be considered backward-incompatible, when the affected part of the API was virtually unusable before the fix.
{% endhint %}

#### Changes considered backward-incompatible

{% hint style="success" %}
These changes can only be introduced in a new major API version or unstable major API version. It is safe to assume that this will not happen to fixed, stable major API versions.

* Renaming or removing an API method.
* Removing mandatory request parameters of an API method.
* Making previously optional request parameters mandatory.
* Removing constant-named fields from API response structures.
* Renaming, removing, or changing the meaning of a request parameter.
* Renaming, removing, or changing the meaning of the possible value of enum-typed request parameters.
* Changing the response structure of an API method.
{% endhint %}

### Emergency Changes <a href="#apibackwardcompatibilitypolicy-emergencychanges" id="apibackwardcompatibilitypolicy-emergencychanges"></a>

Generally, changes to the API interface and functionality will follow this policy as outlined above. However, breaking changes may still be made without introducing a new major version, if it is needed for continuous operation of Coin Metrics' services, for security reasons, or for other reasons, if following this policy is deemed to be infeasible. That may include, but is not limited to, the following: introducing or changing request rate limits, applying specific limits per specific API key, immediate disabling of specific methods or features, etc. Changes also can be made to this policy.

Such emergency changes are expected to be rare exceptions and would be conducted only after careful assessment of the impact to clients. In the event of such a change, Coin Metrics would provide as much advance notice as possible.
