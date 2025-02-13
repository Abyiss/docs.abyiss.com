---
description: Get tokens returns real-time or historical token information.
---

# Tokens

## Get Tokens

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/dex/{exchange}/{blockchain}/tokens`

Returns an array of real-time or historical token data on a decentralized exchange.&#x20;

#### Path Parameters

| Name                                         | Type   | Description                           |
| -------------------------------------------- | ------ | ------------------------------------- |
| exchange<mark style="color:red;">\*</mark>   | string | Decentralized exchange Id             |
| blockchain<mark style="color:red;">\*</mark> | string | Blockchain for decentralized exchange |

#### Query Parameters

| Name                                     | Type    | Description                                                                                                                 |
| ---------------------------------------- | ------- | --------------------------------------------------------------------------------------------------------------------------- |
| apiKey<mark style="color:red;">\*</mark> | string  | Your Abyiss API Key                                                                                                         |
| limit                                    | int     | Number of results per request. Maximum 1,0000 (defualt 100)                                                                 |
| orderBy                                  | string  | Sort the returned data by any field in the API response, such as `id`, `name`, `symbol`, `volumeUSD` and more.              |
| orderDirection                           | string  | `asc` or `desc` return the results sorted by that field in either ascending or descending order.                            |
| skip                                     | int     | Number of results to skip per request.                                                                                      |
| tokenSymbol                              | string  | Filters the results to show only records with the specified token symbol. Example: `WETH`                                   |
| tokenId                                  | string  | Filters the results to show only records with the specified token ID. Example: `0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2` |
| tokeName                                 | string  | Filters the results to show only records with the specified token name. Example: `Wrapped Ethereum`                         |
| logo                                     | boolean | Determines whether or not to include the logo in the response. Example: `true` or `false`                                   |

{% tabs %}
{% tab title="200: OK Success" %}
```json
[
    {
        "id": "0x00000000000045166c45af0fc6e4cf31d9e14b9a",
        "name": "TopBidder",
        "symbol": "BID",
        "decimals": "18",
        "supply": "28240",
        "totalValueLocked": "45.690660599764812617",
        "totalValueLockedUSD": "0",
        "volume": "8347.641875381858852443",
        "volumeUSD": "8114.480070327402387046118602321907",
        "untrackedVolumeUSD": "4057.240035163701193523059301160956",
        "txCount": "15",
        "derivedETH": "0",
        "feesUSD": "81.14480070327402387046118602321907",
        "totalValueLockedUSDUntracked": "0",
        "poolCount": "0"
    }
]
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
curl -H "apiKey: API KEY" https://api.abyiss.com/v2/dex/uniswap/ethereum/tokens
```
{% endtab %}

{% tab title="Python" %}
```python
import urllib.request
url = "https://api.abyiss.com/v2/dex/uniswap/ethereum/tokens?apiKey=*"
print(urllib.request.urlopen(url).read())
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v2/dex/uniswap/ethereum/tokens?apiKey=*")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v2/dex/uniswap/ethereum/tokens?apiKey=*")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v2/dex/uniswap/ethereum/tokens?apiKey=*")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### **Response Object**

Example URL: [https://api.abyiss.com/v2/dex/uniswap/ethereum/tokens?apiKey=](https://api.abyiss.com/v2/dex/uniswap/ethereum/tokens?apiKey=)

```json
[
    {
        "id": "0x00000000000045166c45af0fc6e4cf31d9e14b9a",
        "name": "TopBidder",
        "symbol": "BID",
        "decimals": "18",
        "supply": "28240",
        "totalValueLocked": "45.690660599764812617",
        "totalValueLockedUSD": "0",
        "volume": "8347.641875381858852443",
        "volumeUSD": "8114.480070327402387046118602321907",
        "untrackedVolumeUSD": "4057.240035163701193523059301160956",
        "txCount": "15",
        "derivedETH": "0",
        "feesUSD": "81.14480070327402387046118602321907",
        "totalValueLockedUSDUntracked": "0",
        "poolCount": "0"
    }
]
```

### Response Attributes

<table><thead><tr><th width="265.3333333333333">Attribute Name</th><th>Data Type</th><th>Description </th></tr></thead><tbody><tr><td>id</td><td>string</td><td>Token contact address</td></tr><tr><td>name</td><td>string</td><td>Token name</td></tr><tr><td>symbol</td><td>string</td><td>Token symbol</td></tr><tr><td>tokenDecimals</td><td>string</td><td>Token decimals</td></tr><tr><td>totalSupply</td><td>string</td><td>Token total supply</td></tr><tr><td>tokenTotalValueLocked</td><td>string</td><td>Liquidity across all pools in token units</td></tr><tr><td>tokenTotalValueLockedUSD</td><td>string</td><td>Liquidity across all pools in derived USD</td></tr><tr><td>tokenVolume</td><td>string</td><td>Volume in token units</td></tr><tr><td>tokenVolumeUSD</td><td>string</td><td>Volume in derived USD</td></tr><tr><td>tokenUntrackedVolumeUSD</td><td>string</td><td>Volume in USD even on pools with less reliable USD values</td></tr><tr><td>tokenTxCount</td><td>string</td><td>Transactions across all pools that include this token</td></tr><tr><td>tokenDerivedETH</td><td>string</td><td>Derived price in ETH</td></tr><tr><td>tokenFeesUSD</td><td>string</td><td>Fees in USD</td></tr><tr><td>totalValueLockedUSDUntracked</td><td>string</td><td>TVL derived in USD untracked</td></tr><tr><td>poolCount</td><td>string</td><td>Number of pools containing this token</td></tr></tbody></table>

