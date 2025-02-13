---
description: Get pool trades returns real-time or historical transactions for a pool.
---

# Pool Trades

## Get Pool Trades

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v1/dex/{exchange}/{blockchain}/pool/{pool}/trades`

Returns an object of real-time or historical transactions for a pool on a decentralized exchange.

#### Path Parameters

| Name                                         | Type   | Description                                          |
| -------------------------------------------- | ------ | ---------------------------------------------------- |
| exchange<mark style="color:red;">\*</mark>   | string | Decentralized exchange Id                            |
| blockchain<mark style="color:red;">\*</mark> | string | Blockchain that supports the decentralized exchange. |
| pool<mark style="color:red;">\*</mark>       | string | Pool contract address.                               |

#### Query Parameters

| Name                                     | Type    | Description                                                                                                    |
| ---------------------------------------- | ------- | -------------------------------------------------------------------------------------------------------------- |
| apiKey<mark style="color:red;">\*</mark> | string  | Your Abyiss API Key.                                                                                           |
| limit                                    | int     | Number of results per request. Maximum 1,0000 (default 100).                                                   |
| orderBy                                  | string  | Sort the returned data by any field in the API response, such as `id`, `name`, `symbol`, `volumeUSD` and more. |
| orderDirection                           | string  | `asc` or `desc` return the results sorted by that field in either ascending or descending order.               |
| skip                                     | int     | Number of results to skip per request.                                                                         |
| swap                                     | boolean | Set to false to not return swap array.                                                                         |
| mint                                     | boolean | Set to false to not return mint array.                                                                         |
| burn                                     | boolean | Set to false to not return burn array.                                                                         |
| to                                       | int     | The end of the aggregate time window for historical data. Unix timestamp in milliseconds.                      |
| from                                     | int     | The start of the aggregate time window for historical data. Unix timestamp in milliseconds.                    |
| block                                    | int     | The blockchain block number for historical data.                                                               |

{% tabs %}
{% tab title="200: OK Success" %}
```json
{
    "poolAddress": "0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640",
    "burns": [
        {
            "id": "0x7258050fbb90fa41f73505c552a973113ffc87c67ddd19b37dff7adb6bded18e#3",
            "amount0": "2588.187276",
            "amount1": "0.931484249884373906",
            "amountUSD": "5856.678575459276743008030298541704",
            "logIndex": "122",
            "origin": "0xb2ef52180d1e5f4835f4e343251286fa84743456",
            "timestamp": "1620253661",
            "amount": "310565794229424",
            "owner": "0xc36442b4a4522e871399cd717abdd847ab11fe88"
        }
    ],
    "mints": [
        {
            "id": "0x125e0b641d4a4b08806bf52c0c6757648c9963bcda8681e4f996f09e00d4c2cc#1",
            "amount0": "2995.507735",
            "amount1": "0.999999999871526563",
            "amountUSD": "6424.90529371289423696173129469554",
            "logIndex": "106",
            "origin": "0xb2ef52180d1e5f4835f4e343251286fa84743456",
            "timestamp": "1620250931",
            "amount": "345073104699360",
            "owner": "0xc36442b4a4522e871399cd717abdd847ab11fe88",
            "sender": "0xc36442b4a4522e871399cd717abdd847ab11fe88"
        }
    ],
    "swaps": [
        {
            "id": "0x0804ff007263a885191f23c808a9346e62d502a1fc23be82eb14052408d76ae2#2",
            "amount0": "-119.744094",
            "amount1": "0.035",
            "amountUSD": "119.2881007156144668372176276273185",
            "logIndex": "73",
            "origin": "0x4a12b86c7c0270443760fe85c7d1e6bc62f78e4e",
            "timestamp": "1620252901",
            "recipient": "0xe592427a0aece92de3edee1f18e0157c05861564",
            "sender": "0xe592427a0aece92de3edee1f18e0157c05861564",
            "sqrtPriceX96": "1358206768703179146794161129278934"
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
curl -H "apiKey: API KEY" https://api.abyiss.com/v1/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640/trades
```
{% endtab %}

{% tab title="Python" %}
```python
import urllib.request
url = "https://api.abyiss.com/v1/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640/trades?apiKey="
print(urllib.request.urlopen(url).read())
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v1/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640/trades?apiKey=")
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v1/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640/trades?apiKey=")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v1/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640/trades?apiKey=")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### **Response Object**

Example URL: [https://api.abyiss.com/v1/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640/trades?apiKey=](https://api.abyiss.com/v1/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640/trades?apiKey=)

```json
{
    "poolAddress": "0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640",
    "burns": [
        {
            "id": "0x7258050fbb90fa41f73505c552a973113ffc87c67ddd19b37dff7adb6bded18e#3",
            "amount0": "2588.187276",
            "amount1": "0.931484249884373906",
            "amountUSD": "5856.678575459276743008030298541704",
            "logIndex": "122",
            "origin": "0xb2ef52180d1e5f4835f4e343251286fa84743456",
            "timestamp": "1620253661",
            "amount": "310565794229424",
            "owner": "0xc36442b4a4522e871399cd717abdd847ab11fe88"
        }
    ],
    "mints": [
        {
            "id": "0x125e0b641d4a4b08806bf52c0c6757648c9963bcda8681e4f996f09e00d4c2cc#1",
            "amount0": "2995.507735",
            "amount1": "0.999999999871526563",
            "amountUSD": "6424.90529371289423696173129469554",
            "logIndex": "106",
            "origin": "0xb2ef52180d1e5f4835f4e343251286fa84743456",
            "timestamp": "1620250931",
            "amount": "345073104699360",
            "owner": "0xc36442b4a4522e871399cd717abdd847ab11fe88",
            "sender": "0xc36442b4a4522e871399cd717abdd847ab11fe88"
        }
    ],
    "swaps": [
        {
            "id": "0x0804ff007263a885191f23c808a9346e62d502a1fc23be82eb14052408d76ae2#2",
            "amount0": "-119.744094",
            "amount1": "0.035",
            "amountUSD": "119.2881007156144668372176276273185",
            "logIndex": "73",
            "origin": "0x4a12b86c7c0270443760fe85c7d1e6bc62f78e4e",
            "timestamp": "1620252901",
            "recipient": "0xe592427a0aece92de3edee1f18e0157c05861564",
            "sender": "0xe592427a0aece92de3edee1f18e0157c05861564",
            "sqrtPriceX96": "1358206768703179146794161129278934"
        }
    ]
}
```

### Response Attributes

<table><thead><tr><th width="265.3333333333333">Attribute Name</th><th width="241">Data Type</th><th>Description </th></tr></thead><tbody><tr><td>poolAddress</td><td>string</td><td>Contract address of the pool.</td></tr><tr><td>burns</td><td>object</td><td>Transaction type where tokens where burned or destroyed.</td></tr><tr><td>mints</td><td>object</td><td>Transaction type where tokens where minted or created.</td></tr><tr><td>swaps</td><td>object</td><td>Transaction type where tokens where swaped or traded.</td></tr><tr><td>id</td><td>string</td><td>Transaction hash + "#" + index in Transaction array</td></tr><tr><td>amount0</td><td>string</td><td>Amount of token 0</td></tr><tr><td>amount1</td><td>string</td><td>Amount of token 1</td></tr><tr><td>amountUSD</td><td>string</td><td>Derived amount based on available prices of tokens</td></tr><tr><td>logIndex</td><td>string</td><td>Position within the transactions</td></tr><tr><td>origin</td><td>string</td><td>Transaction origin</td></tr><tr><td>timestamp</td><td>string</td><td>Timestamp of the transaction.</td></tr><tr><td>amount</td><td>string</td><td>amount of liquidity</td></tr><tr><td>owner</td><td>string</td><td>owner of the position</td></tr><tr><td>sender</td><td>string</td><td>Sender of the transaction</td></tr><tr><td>recipient</td><td>string</td><td>Recipient of the transaction</td></tr><tr><td>sqrtPriceX96</td><td>string</td><td>The sqrt(price) of the pool after the swap, as a Q64.96</td></tr></tbody></table>



