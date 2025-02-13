---
description: Get whales returns large crypto trades for a crypto pair from an exchange.
---

# Whales

{% hint style="danger" %}
**The `whales` endpoint is in beta. We do not recommend use in production.**&#x20;
{% endhint %}

## Get Whales

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/whales/{exchange}/{market}`

Returns an object containing large crypto trades for a crypto pair on an exchange.

#### Path Parameters

| Name                                       | Type   | Description                                         |
| ------------------------------------------ | ------ | --------------------------------------------------- |
| exchange<mark style="color:red;">\*</mark> | string | Unique exchange identifier used by Abyiss.          |
| market<mark style="color:red;">\*</mark>   | string | Unique Crypto Pair identifier used by the exchange. |

#### Query Parameters

| Name                                     | Type   | Description         |
| ---------------------------------------- | ------ | ------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key |

{% tabs %}
{% tab title="200: OK Success" %}
```json
{
    "name": "BTC-USD",
    "exchangeId": "coinbasepro",
    "base": "BTC",
    "quote": "USD",
    "whales": {
        "nodes": [
            {
                "cost": 220116.966516,
                "id": 18332,
                "idOnExchange": "456861288",
                "insertedAt": "2022-11-17T15:49:18.878",
                "price": 16560,
                "side": "buy",
                "size": 13.29208735
            },
        ]
    }
}
```
{% endtab %}

{% tab title="401: Unauthorized Unauthorized -- Invalid API Key" %}
```json
{
    "Unauthorized": "Invaild API Key"
}
```
{% endtab %}
{% endtabs %}

## Get Whales Today

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/whales/today`

Returns an object containing the most recent or newest top 50 large crypto trades within the day.

#### Query Parameters

| Name                                     | Type   | Description         |
| ---------------------------------------- | ------ | ------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key |

{% tabs %}
{% tab title="200: OK Success" %}
```json
{
    "cost": 313438.248,
    "id": 18336,
    "idOnExchange": "1025921603",
    "insertedAt": "2022-11-18T05:21:40.879",
    "market": {
        "name": "ETH-USDT",
        "exchangeId": "binance",
        "base": "ETH",
        "quote": "USDT"
    },
    "price": 1224,
    "side": "sell",
    "size": 256.077
},
```
{% endtab %}

{% tab title="401: Unauthorized Unauthorized -- Invalid API Key" %}
```json
{
    "Unauthorized": "Invaild API Key"
}
```
{% endtab %}
{% endtabs %}

### Copy & Paste Code

{% tabs %}
{% tab title="Curl" %}
```shell
curl -H "apiKey: API KEY" https://api.abyiss.com/v2/whales/coinbasepro/btc-usd
```
{% endtab %}

{% tab title="Python" %}
```python
import urllib.request
url = "https://api.abyiss.com/v2/whales/coinbasepro/btc-usd?apiKey=*"
print(urllib.request.urlopen(url).read())
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v2/whales/coinbasepro/btc-usd?apiKey=*")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v2/whales/coinbasepro/btc-usd?apiKey=*")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v2/whales/coinbasepro/btc-usd?apiKey=*")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### Response Object

{% tabs %}
{% tab title="Whales" %}
Example URL: [https://api.abyiss.com/v2/whales/coinbasepro/btc-usd?apiKey=](https://api.abyiss.com/v2/whales/coinbasepro/btc-usd?apiKey=)

```json
{
    "name": "BTC-USD",
    "exchangeId": "coinbasepro",
    "base": "BTC",
    "quote": "USD",
    "whales": {
        "nodes": [
            {
                "cost": 220116.966516,
                "id": 18332,
                "idOnExchange": "456861288",
                "insertedAt": "2022-11-17T15:49:18.878",
                "price": 16560,
                "side": "buy",
                "size": 13.29208735
            },
        ]
    }
}
```
{% endtab %}

{% tab title="Whales Today" %}
Example URL: [https://api.abyiss.com/v2/whales/today?apiKey=](https://api.abyiss.com/v2/whales/today?apiKey=)

```json
{
    "cost": 313438.248,
    "id": 18336,
    "idOnExchange": "1025921603",
    "insertedAt": "2022-11-18T05:21:40.879",
    "market": {
        "name": "ETH-USDT",
        "exchangeId": "binance",
        "base": "ETH",
        "quote": "USDT"
    },
    "price": 1224,
    "side": "sell",
    "size": 256.077
},
```
{% endtab %}
{% endtabs %}

### Response Attributes

| Attribute Name | Data Type | Description                                               |
| -------------- | --------- | --------------------------------------------------------- |
| name           | string    | Unique identifier used by the exchange for ticker.        |
| exchangeId     | string    | The exchange id.                                          |
| base           | string    | The base of the market. eg: The quantity that is bought.  |
| quote          | string    | The quote of the market. eg: The currency being compared. |
| cost           | integer   | The quote cost: (size \* price).                          |
| id             | integer   | The exchange specific unique id of the trade.             |
| idOnExchange   | string    | Unique identifier used by the exchange for trade.         |
| insertedAt     | string    | Unix timestamp of the trade.                              |
| price          | integer   | The price the trade was executed at.                      |
| side           | string    | Whether the trade was a buy or sell.                      |
| size           | integer   | The quantity traded.                                      |

