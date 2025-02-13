---
description: Get token trades returns real-time or historical transactions for a token.
---

# Token Trades

## Get Token Trades

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/dex/{exchange}/{blockchain}/token/{token}/trades`

Returns an object of real-time or historical transactions for a token on a decentralized exchange.

#### Path Parameters

| Name                                         | Type   | Description                                          |
| -------------------------------------------- | ------ | ---------------------------------------------------- |
| exchange<mark style="color:red;">\*</mark>   | string | Decentralized exchange Id                            |
| blockchain<mark style="color:red;">\*</mark> | string | Blockchain that supports the decentralized exchange. |
| token<mark style="color:red;">\*</mark>      | string | Token contract address.                              |

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
| base                                     | boolean | Set to false to not return any arrays with key 'As0' appended.                                                 |
| quote                                    | boolean | Set to false to not return any arrays with key 'As1' appended.                                                 |

{% tabs %}
{% tab title="200: OK Success" %}
```json
{
    "token": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
    "burnsAs0": [
        {
            "id": "0x6dd54d05de948aeed4020a80d96cbe33141e08ca056e3bce9ff5f830a479a72f#12216",
            "amount0": "0.640763031979070073",
            "amount1": "9668376285.524915178789976791",
            "amountUSD": "1764.095549673846551960457267566354",
            "logIndex": "272",
            "origin": "0x525208dd0b56c27bd10703bd675fca0509a17154",
            "timestamp": "1677806459",
            "pool": {
                "token0": {
                    "name": "Wrapped Ether",
                    "id": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
                    "symbol": "WETH"
                },
                "token1": {
                    "name": "PAWSWAP",
                    "id": "0xdc63269ea166b70d4780b3a11f5c825c2b761b01",
                    "symbol": "PAW"
                }
            },
            "transactionId": "0x6dd54d05de948aeed4020a80d96cbe33141e08ca056e3bce9ff5f830a479a72f",
            "amount": "139566126878029687610035",
            "owner": "0xc36442b4a4522e871399cd717abdd847ab11fe88"
        }
    ],
    "burnsAs1": [
        {
            "id": "0xdc3fe821971ed33e296ab649a43a7804ccf2b5c20a1c5c0f06ecb38428f85e92#32385",
            "amount0": "0",
            "amount1": "0",
            "amountUSD": "0",
            "logIndex": "368",
            "origin": "0xd1818a80dac94fa1db124b9b1a1bb71dc20f228d",
            "timestamp": "1677806363",
            "pool": {
                "token0": {
                    "name": "Frax Share",
                    "id": "0x3432b6a60d23ca0dfca7761b7ab56459d9c964d0",
                    "symbol": "FXS"
                },
                "token1": {
                    "name": "Wrapped Ether",
                    "id": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
                    "symbol": "WETH"
                }
            },
            "transactionId": "0xdc3fe821971ed33e296ab649a43a7804ccf2b5c20a1c5c0f06ecb38428f85e92",
            "amount": "0",
            "owner": "0xc36442b4a4522e871399cd717abdd847ab11fe88"
        }
    ],
    "mintsAs0": [
        {
            "id": "0x2aefe4d786d4f8ae16f67383efd19d5a4ffc4cf0bb599f673348ccd477b7f566#12237",
            "amount0": "0.663375770535683083",
            "amount1": "23855798459.50671632017966465",
            "amountUSD": "2802.032003282354183726020735499312",
            "logIndex": "229",
            "origin": "0x525208dd0b56c27bd10703bd675fca0509a17154",
            "timestamp": "1677806831",
            "pool": {
                "token0": {
                    "name": "Wrapped Ether",
                    "id": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
                    "symbol": "WETH"
                },
                "token1": {
                    "name": "PAWSWAP",
                    "id": "0xdc63269ea166b70d4780b3a11f5c825c2b761b01",
                    "symbol": "PAW"
                }
            },
            "transactionId": "0x2aefe4d786d4f8ae16f67383efd19d5a4ffc4cf0bb599f673348ccd477b7f566",
            "amount": "204211770708667193113473",
            "owner": "0xc36442b4a4522e871399cd717abdd847ab11fe88",
            "sender": "0xc36442b4a4522e871399cd717abdd847ab11fe88"
        }
    ],
    "mintsAs1": [
        {
            "id": "0xa5e72d20faee5bd352f087c3a8d64de37124db3fe658abcb160216aaa0e474c6#32386",
            "amount0": "3.560916861043253688",
            "amount1": "0.013838517603100051",
            "amountUSD": "60.90661297105051853347306524867313",
            "logIndex": "250",
            "origin": "0xd1818a80dac94fa1db124b9b1a1bb71dc20f228d",
            "timestamp": "1677806423",
            "pool": {
                "token0": {
                    "name": "Frax Share",
                    "id": "0x3432b6a60d23ca0dfca7761b7ab56459d9c964d0",
                    "symbol": "FXS"
                },
                "token1": {
                    "name": "Wrapped Ether",
                    "id": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
                    "symbol": "WETH"
                }
            },
            "transactionId": "0xa5e72d20faee5bd352f087c3a8d64de37124db3fe658abcb160216aaa0e474c6",
            "amount": "675512064657779058",
            "owner": "0xc36442b4a4522e871399cd717abdd847ab11fe88",
            "sender": "0xc36442b4a4522e871399cd717abdd847ab11fe88"
        }
    ],
    "swapsAs0": [
        {
            "id": "0x9362916811086056d07314328c08354b36d06ff88e90d641ea08f3b33cc67762#2004702",
            "amount0": "-0.612354427081033309",
            "amount1": "1000",
            "amountUSD": "1001.008603810961858938601242554778",
            "logIndex": "12",
            "origin": "0x30c649958a034ac779212f71369441df416ee5e8",
            "timestamp": "1677806351",
            "pool": {
                "token0": {
                    "name": "Wrapped Ether",
                    "id": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
                    "symbol": "WETH"
                },
                "token1": {
                    "name": "Tether USD",
                    "id": "0xdac17f958d2ee523a2206206994597c13d831ec7",
                    "symbol": "USDT"
                }
            },
            "transactionId": "0x9362916811086056d07314328c08354b36d06ff88e90d641ea08f3b33cc67762",
            "recipient": "0xdbc1a433a5ca4ffa184a036a27d3d6322d4ea6f4",
            "sender": "0xef1c6e67703c7bd7107eed8303fbe6ec2554bf6b",
            "sqrtPriceX96": "3200892511195460953817623"
        }
    ],
    "swapsAs1": [
        {
            "id": "0x143a04e8c249c886e974446a169fe308146a6908291f8b8e3477f89b497bfc4b#62193",
            "amount0": "46228.346306409424",
            "amount1": "-12.286385713223357948",
            "amountUSD": "20104.64750424809236613816733545052",
            "logIndex": "26",
            "origin": "0x903c26a3d690bf010fd6441328983925852ffe4c",
            "timestamp": "1677806351",
            "pool": {
                "token0": {
                    "name": "Fantom Token",
                    "id": "0x4e15361fd6b4bb609fa63c81a2be19d873717870",
                    "symbol": "FTM"
                },
                "token1": {
                    "name": "Wrapped Ether",
                    "id": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
                    "symbol": "WETH"
                }
            },
            "transactionId": "0x143a04e8c249c886e974446a169fe308146a6908291f8b8e3477f89b497bfc4b",
            "recipient": "0x000000000dfde7deaf24138722987c9a6991e2d4",
            "sender": "0x000000000dfde7deaf24138722987c9a6991e2d4",
            "sqrtPriceX96": "1295321746504811986688003350"
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
curl -H "apiKey: API KEY" https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2/trades
```
{% endtab %}

{% tab title="Python" %}
```python
import urllib.request
url = "https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2/trades?apiKey="
print(urllib.request.urlopen(url).read())
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2/trades?apiKey=")
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2/trades?apiKey=")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2/trades?apiKey=")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### **Response Object**

Example URL: [https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2/trades?apiKey=](https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2/trades?apiKey=)

```json
{
    "token": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
    "burnsAs0": [
        {
            "id": "0x6dd54d05de948aeed4020a80d96cbe33141e08ca056e3bce9ff5f830a479a72f#12216",
            "amount0": "0.640763031979070073",
            "amount1": "9668376285.524915178789976791",
            "amountUSD": "1764.095549673846551960457267566354",
            "logIndex": "272",
            "origin": "0x525208dd0b56c27bd10703bd675fca0509a17154",
            "timestamp": "1677806459",
            "pool": {
                "token0": {
                    "name": "Wrapped Ether",
                    "id": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
                    "symbol": "WETH"
                },
                "token1": {
                    "name": "PAWSWAP",
                    "id": "0xdc63269ea166b70d4780b3a11f5c825c2b761b01",
                    "symbol": "PAW"
                }
            },
            "transactionId": "0x6dd54d05de948aeed4020a80d96cbe33141e08ca056e3bce9ff5f830a479a72f",
            "amount": "139566126878029687610035",
            "owner": "0xc36442b4a4522e871399cd717abdd847ab11fe88"
        }
    ],
    "burnsAs1": [
    ],
    "mintsAs0": [
    ],
    "mintsAs1": [
    ],
    "swapsAs0": [
    ],
    "swapsAs1": [
    ],
}
```

### Response Attributes

<table><thead><tr><th width="265.3333333333333">Attribute Name</th><th width="241">Data Type</th><th>Description </th></tr></thead><tbody><tr><td>token</td><td>string</td><td>Contract address of the token.</td></tr><tr><td>burnsAs0</td><td>object</td><td>Transaction where the token was burned as token 0.</td></tr><tr><td>burnsAs1</td><td>object</td><td>Transaction where the token was burned as token 1.</td></tr><tr><td>mintsAs0</td><td>object</td><td>Transaction where the token was minted as token 0.</td></tr><tr><td>mintsAs1</td><td>object</td><td>Transaction where the token was minted as token 1.</td></tr><tr><td>swapsAs0</td><td>object</td><td>Transaction where the token was swaped as token 0.</td></tr><tr><td>swapsAs1</td><td>object</td><td>Transaction where the token was swaped as token 1.</td></tr><tr><td>id</td><td>string</td><td>Transaction hash + "#" + index in Transaction array</td></tr><tr><td>amount0</td><td>string</td><td>Amount of token 0</td></tr><tr><td>amount1</td><td>string</td><td>Amount of token 1</td></tr><tr><td>amountUSD</td><td>string</td><td>Derived amount based on available prices of tokens</td></tr><tr><td>logIndex</td><td>string</td><td>Position within the transactions</td></tr><tr><td>origin</td><td>string</td><td>Transaction origin</td></tr><tr><td>timestamp</td><td>string</td><td>Timestamp of the transaction.</td></tr><tr><td>pool</td><td>string</td><td>Liquidity pool that the transaction occurred in.</td></tr><tr><td>token0</td><td>string</td><td>Token 0 in the pool.</td></tr><tr><td>token1</td><td>string</td><td>Token 1 in the pool.</td></tr><tr><td>name</td><td>string</td><td>Name of the token.</td></tr><tr><td>id</td><td>string</td><td>Contract address of the token.</td></tr><tr><td>symbol</td><td>string</td><td>Symbol of the token.</td></tr><tr><td>transactionId</td><td>string</td><td>The transaction id. </td></tr><tr><td>amount</td><td>string</td><td>Amount of liquidity. </td></tr><tr><td>owner</td><td>string</td><td>Owner of position.</td></tr></tbody></table>



