---
description: >-
  Get token aggregates returns real-time or historical candlestick bars for a
  token.
---

# Token Aggregates (Bars)

## Get Token Aggregates (Bars)

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/dex/{exchange}/{blockchain}/token/{token}/aggregate?timeframe={interval}`

Returns an object of real-time or historical candlesticks (bars) for a token on a decentralized exchange.&#x20;

#### Path Parameters

| Name                                         | Type   | Description                                          |
| -------------------------------------------- | ------ | ---------------------------------------------------- |
| exchange<mark style="color:red;">\*</mark>   | string | Decentralized exchange Id.                           |
| blockchain<mark style="color:red;">\*</mark> | string | Blockchain that supports the decentralized exchange. |
| token                                        | string | Token contract address.                              |

#### Query Parameters

| Name                                       | Type   | Description                                                                                                    |
| ------------------------------------------ | ------ | -------------------------------------------------------------------------------------------------------------- |
| apiKey<mark style="color:red;">\*</mark>   | string | Your Abyiss API Key.                                                                                           |
| limit                                      | int    | Number of results per request. Maximum 1,0000 (default 100).                                                   |
| orderBy                                    | string | Sort the returned data by any field in the API response, such as `id`, `name`, `symbol`, `volumeUSD` and more. |
| orderDirection                             | string | `asc` or `desc` return the results sorted by that field in either ascending or descending order.               |
| skip                                       | int    | Number of results to skip per request.                                                                         |
| interval<mark style="color:red;">\*</mark> | string | Aggregate bar size. `hour` or `day.`                                                                           |
| from                                       | int    | The start of the aggregate time window for historical data. Unix timestamp in milliseconds.                    |
| to                                         | int    | The end of the aggregate time window for historical data. Unix timestamp in milliseconds.                      |

{% tabs %}
{% tab title="200: OK Success" %}
```json
{
    "timeframe": "day",
    "id": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
    "name": "Wrapped Ether",
    "symbol": "WETH",
    "TokenAggregates": [
        {
            "id": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2-19457",
            "timestamp": 1681084800,
            "priceUSD": "1861.812948948509109388355192853743",
            "o": "1863.160356657281537768066137359126",
            "h": "1863.160356657281537768066137359126",
            "l": "1854.198335514748181373337243056372",
            "c": "1861.812948948509109388355192853743",
            "volume": "45669.177692851802160815",
            "volumeUSD": "84911506.50161917605934414103318911",
            "untrackedVolumeUSD": "84911506.50161917605934414103318911",
            "totalValueLocked": "631521.957032934821587711",
            "totalValueLockedUSD": "1175775757.14922204229657038017616",
            "feesUSD": "136802.7673893035106587395801362141"
        },
        {
            "id": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2-19456",
            "timestamp": 1680998400,
            "priceUSD": "1863.160356657281537768066137359126",
            "o": "1853.838633116650036787389059651635",
            "h": "1869.100132810398674639493628800632",
            "l": "1832.845247207196123319380992497196",
            "c": "1863.160356657281537768066137359126",
            "volume": "183377.010533141634178776",
            "volumeUSD": "338844982.527842179017489089242307",
            "untrackedVolumeUSD": "338844982.527842179017489089242307",
            "totalValueLocked": "630787.710476643156442134",
            "totalValueLockedUSD": "1175258655.626692509388975773585923",
            "feesUSD": "462630.7204260430184761393488914015"
        }
    ]
}
```
{% endtab %}

{% tab title="401: Unauthorized Unauthorized -- Invalid API Key" %}
```javascript
{
    "Unauthorized": "Invaild API Key"
}
```
{% endtab %}
{% endtabs %}

### **Copy & Paste Code**

{% tabs %}
{% tab title="Curl" %}
```bash
curl -H "apiKey: API KEY" https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2/aggregate?timeframe=day
```
{% endtab %}

{% tab title="Python" %}
```python
import urllib.request
url = "https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2/aggregate?timeframe=day&apiKey="
print(urllib.request.urlopen(url).read())
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2/aggregate?timeframe=day&apiKey=")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2/aggregate?timeframe=day&apiKey=")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2/aggregate?timeframe=day&apiKey=")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### **Response Object**

Example URL: [https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2/aggregate?timeframe=day\&apiKey=](https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2/aggregate?timeframe=day\&apiKey=)

```json
{
    "timeframe": "day",
    "id": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
    "name": "Wrapped Ether",
    "symbol": "WETH",
    "TokenAggregates": [
        {
            "id": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2-19457",
            "timestamp": 1681084800,
            "priceUSD": "1861.812948948509109388355192853743",
            "o": "1863.160356657281537768066137359126",
            "h": "1863.160356657281537768066137359126",
            "l": "1854.198335514748181373337243056372",
            "c": "1861.812948948509109388355192853743",
            "volume": "45669.177692851802160815",
            "volumeUSD": "84911506.50161917605934414103318911",
            "untrackedVolumeUSD": "84911506.50161917605934414103318911",
            "totalValueLocked": "631521.957032934821587711",
            "totalValueLockedUSD": "1175775757.14922204229657038017616",
            "feesUSD": "136802.7673893035106587395801362141"
        },
        {
            "id": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2-19456",
            "timestamp": 1680998400,
            "priceUSD": "1863.160356657281537768066137359126",
            "o": "1853.838633116650036787389059651635",
            "h": "1869.100132810398674639493628800632",
            "l": "1832.845247207196123319380992497196",
            "c": "1863.160356657281537768066137359126",
            "volume": "183377.010533141634178776",
            "volumeUSD": "338844982.527842179017489089242307",
            "untrackedVolumeUSD": "338844982.527842179017489089242307",
            "totalValueLocked": "630787.710476643156442134",
            "totalValueLockedUSD": "1175258655.626692509388975773585923",
            "feesUSD": "462630.7204260430184761393488914015"
        }
    ]
}
```

### Response Attributes

<table><thead><tr><th width="265.3333333333333">Attribute Name</th><th>Data Type</th><th>Description </th></tr></thead><tbody><tr><td>timeframe</td><td>string</td><td>The Timeframe of the Aggregate bar (Hour or Day)</td></tr><tr><td>id</td><td>string</td><td>Token contact address</td></tr><tr><td>name</td><td>string</td><td>Token name</td></tr><tr><td>symbol</td><td>string</td><td>Token symbol</td></tr><tr><td>id</td><td>string</td><td>Id of the candlestick.</td></tr><tr><td>timestamp</td><td>int</td><td>Unix timestamp of the aggregate bar.</td></tr><tr><td>priceUSD</td><td>string</td><td>The price at the end of the period in USD</td></tr><tr><td>o</td><td>string</td><td>The opening price USD</td></tr><tr><td>h</td><td>string</td><td>The high price USD</td></tr><tr><td>l</td><td>string</td><td>The low price USD</td></tr><tr><td>c</td><td>string</td><td>The close price USD</td></tr><tr><td>volume</td><td>string</td><td>The volume in token units</td></tr><tr><td>volumeUSD</td><td>string</td><td>The volume in derived USD</td></tr><tr><td>untrackedVolumeUSD</td><td>string</td><td>The volume in USD even on pools with less reliable USD valuesThe liquidity across all pools in token units</td></tr><tr><td>totalValueLocked</td><td>string</td><td>The liquidity across all pools in token units</td></tr><tr><td>totalValueLockedUSD</td><td>string</td><td>The liquidity across all pools in derived USD</td></tr><tr><td>feesUSD</td><td>string</td><td>The fees in USD</td></tr></tbody></table>



