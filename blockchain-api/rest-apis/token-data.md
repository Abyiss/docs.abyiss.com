---
description: Get token data returns real-time or historical token information.
---

# Token Data

## Get Token Data

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/dex/{exchange}/{blockchain}/token/{token}`

Returns an object of real-time or historical token data on the decentralized exchange.

#### Path Parameters

| Name                                         | Type   | Description                           |
| -------------------------------------------- | ------ | ------------------------------------- |
| exchange<mark style="color:red;">\*</mark>   | string | Decentralized exchange Id             |
| blockchain<mark style="color:red;">\*</mark> | string | Blockchain for Decentralized exchange |
| token<mark style="color:red;">\*</mark>      | string | Token contract address.               |

#### Query Parameters

| Name                                     | Type   | Description                                       |
| ---------------------------------------- | ------ | ------------------------------------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key                               |
| block                                    | int    | The blockchain block number for historical data.  |

{% tabs %}
{% tab title="200: OK Success" %}
```javascript
{
    "id": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
    "name": "Wrapped Ether",
    "symbol": "WETH",
    "decimals": "18",
    "supply": "19848",
    "totalValueLocked": "631142.087037589087808909",
    "totalValueLockedUSD": "1175058789.34375407186171784308728",
    "volume": "344086745.20009839797422871",
    "volumeUSD": "753749160247.6554862800162826515373",
    "untrackedVolumeUSD": "418002367585531.1947936090378553175",
    "txCount": "24827115",
    "derivedETH": "1",
    "feesUSD": "1205919785.200171873113778800523199",
    "totalValueLockedUSDUntracked": "0",
    "poolCount": "0"
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
curl -H "apiKey: API KEY" https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2
```
{% endtab %}

{% tab title="Python" %}
```python
import urllib.request
url = "https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2?apiKey=*")"
print(urllib.request.urlopen(url).read())
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2?apiKey=*")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2?apiKey=*")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2?apiKey=*")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### **Response Object**

Example URL: [https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2?apiKey=](https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2?apiKey=)

```json
{
    "id": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
    "name": "Wrapped Ether",
    "symbol": "WETH",
    "decimals": "18",
    "supply": "19848",
    "totalValueLocked": "631142.087037589087808909",
    "totalValueLockedUSD": "1175058789.34375407186171784308728",
    "volume": "344086745.20009839797422871",
    "volumeUSD": "753749160247.6554862800162826515373",
    "untrackedVolumeUSD": "418002367585531.1947936090378553175",
    "txCount": "24827115",
    "derivedETH": "1",
    "feesUSD": "1205919785.200171873113778800523199",
    "totalValueLockedUSDUntracked": "0",
    "poolCount": "0"
}
```

### Response Attributes

<table><thead><tr><th width="268.3333333333333">Attribute Name</th><th>Data Type</th><th>Description </th></tr></thead><tbody><tr><td>id</td><td>string</td><td>Token contract address</td></tr><tr><td>name</td><td>string</td><td>Token name</td></tr><tr><td>symbol</td><td>string</td><td>Token symbol</td></tr><tr><td>tokenDecmials</td><td>string</td><td>Token decimals</td></tr><tr><td>totalSupply</td><td>string</td><td>Token total supply</td></tr><tr><td>tokenTotalValueLocked</td><td>string</td><td>Liquidity across all pools in token units</td></tr><tr><td>tokenTotalValueLockedUSD</td><td>string</td><td>Liquidity across all pools in derived USD</td></tr><tr><td>tokenVolume</td><td>string</td><td>Volume in token units</td></tr><tr><td>tokenVolumeUSD</td><td>string</td><td>Volume in derived USD</td></tr><tr><td>tokenUntrackedVolumeUSD</td><td>string</td><td>Volume in USD even on pools with less reliable USD values</td></tr><tr><td>tokenTxCount</td><td>string</td><td>Transactions across all pools that include this token</td></tr><tr><td>tokenDerivedETH</td><td>string</td><td>Derived price in ETH</td></tr><tr><td>tokenFeesUSD</td><td>string</td><td>Fees in USD</td></tr><tr><td>totalValueLockedUSDUntracked</td><td>string</td><td>TVL derived in USD untracked</td></tr><tr><td>poolCount</td><td>string</td><td>Number of pools containing this token</td></tr></tbody></table>

