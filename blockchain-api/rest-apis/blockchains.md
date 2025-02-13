---
description: >-
  Get blockchains returns the supported blockchains for a decentralized
  exchange.
---

# Blockchains

## Get Exchange Blockchains

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/dex/{exchange}`

Returns an array of supported blockchains for a decentralized exchange.

#### Path Parameters

| Name                                       | Type   | Description                |
| ------------------------------------------ | ------ | -------------------------- |
| exchange<mark style="color:red;">\*</mark> | string | The decentralized exchange |

#### Query Parameters

| Name                                     | Type   | Description         |
| ---------------------------------------- | ------ | ------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key |

{% tabs %}
{% tab title="200: OK Success" %}
```javascript
[
    {
        "id": "ethereum",
        "name": "Ethereum"
    },
    {
        "id": "polygon",
        "name": "Polygon"
    },
    {
        "id": "optimism",
        "name": "Optimism"
    },
    {
        "id": "celo",
        "name": "Celo"
    },
    {
        "id": "arbitrum",
        "name": "Arbitrum"
    },
    {
        "id": "binance",
        "name": "Binance Smart Chain"
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
curl -H "apiKey: API KEY" https://api.abyiss.com/v2/dex/uniswap
```
{% endtab %}

{% tab title="Python" %}
```python
import urllib.request
url = "https://api.abyiss.com/v2/dex/uniswap?apiKey=*"
print(urllib.request.urlopen(url).read())
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v2/dex/uniswap?apiKey=*")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v2/dex/uniswap?apiKey=*")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v2/dex/uniswap?apiKey=*")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### **Response Object**

Example URL: [https://api.abyiss.com/v2/dex/uniswap?apiKey=](https://api.abyiss.com/v2/dex/uniswap?apiKey=)

```json
[
    {
        "id": "ethereum",
        "name": "Ethereum"
    },
    {
        "id": "polygon",
        "name": "Polygon"
    },
    {
        "id": "optimism",
        "name": "Optimism"
    },
    {
        "id": "celo",
        "name": "Celo"
    },
    {
        "id": "arbitrum",
        "name": "Arbitrum"
    },
    {
        "id": "binance",
        "name": "Binance Smart Chain"
    }
]
```

### Response Attributes

| Attribute Name | Data Type | Description                                      |
| -------------- | --------- | ------------------------------------------------ |
| id             | string    | Unique exchange identifier used by Abyiss.       |
| name           | string    | The official name of the decentralized exchange. |

