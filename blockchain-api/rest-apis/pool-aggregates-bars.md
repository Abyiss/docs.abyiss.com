---
description: >-
  Get pool aggregates returns real-time or historical candlestick bars for a
  liquidity pool.
---

# Pool Aggregates (Bars)

## Get Liquidity Pool Aggregates (Bars)

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/dex/{exchange}/{blockchain}/pool/{pool}/aggregate?timeframe={interval}`

Returns an object of real-time or historical candlestick bars for a liquidity pool on a decentralized exchange.&#x20;

#### Path Parameters

| Name                                         | Type   | Description                                          |
| -------------------------------------------- | ------ | ---------------------------------------------------- |
| exchange<mark style="color:red;">\*</mark>   | string | Decentralized exchange Id                            |
| blockchain<mark style="color:red;">\*</mark> | string | Blockchain that supports the decentralized exchange. |
| pool<mark style="color:red;">\*</mark>       | string | Liquidity Pool contract address.                     |

#### Query Parameters

| Name                                       | Type   | Description                                                                                                    |
| ------------------------------------------ | ------ | -------------------------------------------------------------------------------------------------------------- |
| apiKey<mark style="color:red;">\*</mark>   | string | Your Abyiss API Key                                                                                            |
| limit                                      | int    | Number of results per request. Maximum 1,0000 (default 100)                                                    |
| orderBy                                    | string | Sort the returned data by any field in the API response, such as `id`, `name`, `symbol`, `volumeUSD` and more. |
| orderDirection                             | string | `asc` or `desc` return the results sorted by that field in either ascending or descending order                |
| skip                                       | int    | Number of results to skip per request.                                                                         |
| interval<mark style="color:red;">\*</mark> | string | Aggregate bar size. `hour` or `day`                                                                            |
| to                                         | int    | The end of the aggregate time window for historical data. Unix timestamp in milliseconds.                      |
| from                                       | int    | The start of the aggregate time window for historical data. Unix timestamp in milliseconds.                    |

{% tabs %}
{% tab title="200: OK Success" %}
```json
{
    "timeframe": "day",
    "token0": {
        "name": "USD Coin",
        "id": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
        "symbol": "USDC"
    },
    "token1": {
        "name": "Wrapped Ether",
        "id": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
        "symbol": "WETH"
    },
    "poolAggregates": [
        {
            "id": "0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640-19457",
            "timestamp": 1681084800,
            "feeGrowthGlobal0X128": "2339213968916729531223096419274296",
            "feeGrowthGlobal1X128": "1124565708862364413358919226291694974818769",
            "feesUSD": "24570.19489506981696256671263525303",
            "o": "1861.229249917124425671059978055896",
            "h": "1866.129826859531905327345582770674",
            "l": "1849.588545028402903627911445772043",
            "c": "1861.229249917124425671059978055896",
            "volumeUSD": "49140389.79013963392513342527050604",
            "volumeToken0": "49134098.465595",
            "volumeToken1": "26424.102167136654514951",
            "token0Price": "1860.821468497617504272633341910774",
            "token1Price": "0.0005373970673325130686586439093719616",
            "liquidity": "28359865230079992268",
            "txCount": "1946",
            "tvlUSD": "445832755.5937852890879586310030789",
            "sqrtPrice": "1836653495884466183644038654704998",
            "tick": "201032"
        },
        {
            "id": "0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640-19456",
            "timestamp": 1680998400,
            "feeGrowthGlobal0X128": "2339079716985510919254387473263998",
            "feeGrowthGlobal1X128": "1124493096642505157141501076316955741370453",
            "feesUSD": "97638.63554132466059685342601960951",
            "o": "1850.396710419790204337751969898761",
            "h": "1873.596532314986342851627620643428",
            "l": "1828.321888992128176916756588291294",
            "c": "1850.396710419790204337751969898761",
            "volumeUSD": "195277271.0826493211937068520392203",
            "volumeToken0": "195303846.783318",
            "volumeToken1": "105673.156917704060998814",
            "token0Price": "1861.217048228268273911189536461615",
            "token1Price": "0.0005372828499244196538466630433087226",
            "liquidity": "28271708994189162991",
            "txCount": "4708",
            "tvlUSD": "446136840.2157276077963775647371453",
            "sqrtPrice": "1836458305993924899300320848785481",
            "tick": "201030"
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
curl -H "apiKey: API KEY" https://api.abyiss.com/v2/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640/aggregate?timeframe=day
```
{% endtab %}

{% tab title="Python" %}
```python
import urllib.request
url = "https://api.abyiss.com/v2/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640/aggregate?timeframe=day&apiKey="
print(urllib.request.urlopen(url).read())
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v2/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640/aggregate?timeframe=day&apiKey=")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v2/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640/aggregate?timeframe=day&apiKey=")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v2/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640/aggregate?timeframe=day&apiKey=")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### **Response Object**

Example URL: [https://api.abyiss.com/v2/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640/aggregate?timeframe=day\&apiKey=](https://api.abyiss.com/v2/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640/aggregate?timeframe=day\&apiKey=)

```json
{
    "timeframe": "day",
    "token0": {
        "name": "USD Coin",
        "id": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
        "symbol": "USDC"
    },
    "token1": {
        "name": "Wrapped Ether",
        "id": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
        "symbol": "WETH"
    },
    "poolAggregates": [
        {
            "id": "0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640-19457",
            "timestamp": 1681084800,
            "feeGrowthGlobal0X128": "2339213968916729531223096419274296",
            "feeGrowthGlobal1X128": "1124565708862364413358919226291694974818769",
            "feesUSD": "24570.19489506981696256671263525303",
            "o": "1861.229249917124425671059978055896",
            "h": "1866.129826859531905327345582770674",
            "l": "1849.588545028402903627911445772043",
            "c": "1861.229249917124425671059978055896",
            "volumeUSD": "49140389.79013963392513342527050604",
            "volumeToken0": "49134098.465595",
            "volumeToken1": "26424.102167136654514951",
            "token0Price": "1860.821468497617504272633341910774",
            "token1Price": "0.0005373970673325130686586439093719616",
            "liquidity": "28359865230079992268",
            "txCount": "1946",
            "tvlUSD": "445832755.5937852890879586310030789",
            "sqrtPrice": "1836653495884466183644038654704998",
            "tick": "201032"
        },
        {
            "id": "0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640-19456",
            "timestamp": 1680998400,
            "feeGrowthGlobal0X128": "2339079716985510919254387473263998",
            "feeGrowthGlobal1X128": "1124493096642505157141501076316955741370453",
            "feesUSD": "97638.63554132466059685342601960951",
            "o": "1850.396710419790204337751969898761",
            "h": "1873.596532314986342851627620643428",
            "l": "1828.321888992128176916756588291294",
            "c": "1850.396710419790204337751969898761",
            "volumeUSD": "195277271.0826493211937068520392203",
            "volumeToken0": "195303846.783318",
            "volumeToken1": "105673.156917704060998814",
            "token0Price": "1861.217048228268273911189536461615",
            "token1Price": "0.0005372828499244196538466630433087226",
            "liquidity": "28271708994189162991",
            "txCount": "4708",
            "tvlUSD": "446136840.2157276077963775647371453",
            "sqrtPrice": "1836458305993924899300320848785481",
            "tick": "201030"
        }
    ]
}
```

### Response Attributes

<table><thead><tr><th width="265.3333333333333">Attribute Name</th><th>Data Type</th><th>Description </th></tr></thead><tbody><tr><td>timeframe</td><td>string</td><td>The Timeframe of the Aggregate bar (<code>Hour</code> or <code>Day</code>)</td></tr><tr><td>token0</td><td>string</td><td>Token 0 in the pool</td></tr><tr><td>token1</td><td>string</td><td>Token 1 in the pool</td></tr><tr><td>name</td><td>string</td><td>Token name</td></tr><tr><td>id</td><td>string</td><td>Token contract address id</td></tr><tr><td>symbol</td><td>string</td><td>Token symbol</td></tr><tr><td>id</td><td>string</td><td>Id of the candlestick.</td></tr><tr><td>timestamp</td><td>string</td><td>Timestamp rounded to current day by dividing by 86400</td></tr><tr><td>feeGrowthGlobal0X128</td><td>string</td><td>Tracker for global fee growth</td></tr><tr><td>feeGrowthGlobal1X128</td><td>string</td><td>Tracker for global fee growth</td></tr><tr><td>feesUSD</td><td>string</td><td>Fees in USD</td></tr><tr><td>o</td><td>string</td><td>Opening price of token0</td></tr><tr><td>h</td><td>string</td><td>High price of token0</td></tr><tr><td>l</td><td>string</td><td>Low price of token0</td></tr><tr><td>c</td><td>string</td><td>Close price of token0</td></tr><tr><td>volumeUSD</td><td>string</td><td>Volume in USD</td></tr><tr><td>volumeToken0</td><td>string</td><td>Volume in token0</td></tr><tr><td>volumeToken1</td><td>string</td><td>Volume in token1</td></tr><tr><td>token0Price</td><td>string</td><td>Price of token0 - derived from sqrtPrice</td></tr><tr><td>token1Price</td><td>string</td><td>Price of token1 - derived from sqrtPrice</td></tr><tr><td>liquidity</td><td>string</td><td>In-range liquidity at end of period</td></tr><tr><td>txCount</td><td>string</td><td>Number of transactions during period</td></tr><tr><td>tvlUSD</td><td>string</td><td>The total value locked in USD at the end of the period.</td></tr><tr><td>sqrtPrice</td><td>string</td><td>Current price tracker at end of period</td></tr><tr><td>tick</td><td>string</td><td>Current tick at end of period</td></tr></tbody></table>



