---
description: Get exchange data returns information about a crypto exchange.
---

# Exchange Data

## Get Exchange Data

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v1/{exchange}`

Returns an object with properties about the exchange.

#### Path Parameters

| Name                                       | Type   | Description                                 |
| ------------------------------------------ | ------ | ------------------------------------------- |
| exchange<mark style="color:red;">\*</mark> | string | Unique exchange identifier used by Abyiss.  |

#### Query Parameters

| Name                                     | Type   | Description         |
| ---------------------------------------- | ------ | ------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key |

{% tabs %}
{% tab title="200: OK Success" %}
```javascript
{
    "name": "Coinbase Pro",
    "id": "coinbasepro",
    "countries": [
        "US"
    ],
    "hasTrades": true,
    "hasAggregates": true,
    "aggregateTimeframes": {
        "1m": 60,
        "5m": 300,
        "15m": 900,
        "1h": 3600,
        "6h": 21600,
        "1d": 86400
    },
    "url": "https://pro.coinbase.com/",
    "fees": [
        "https://docs.pro.coinbase.com/#fees",
        "https://support.pro.coinbase.com/customer/en/portal/articles/2945310-fees"
    ],
    "docs": "https://docs.pro.coinbase.com",
    "logo": "https://user-images.githubusercontent.com/1294454/41764625-63b7ffde-760a-11e8-996d-a6328fa9347a.jpg"
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

### Copy & Paste Code

{% tabs %}
{% tab title="Curl" %}
```shell
curl -H "apiKey: API KEY" https://api.abyiss.com/v1/coinbasepro
```
{% endtab %}

{% tab title="Python" %}
```python
from Abyiss import Abyiss

apiKey = "YOUR API KEY" 
client = Abyiss.Client(apiKey)

exchangeDetails = client.getExchangeDetails("coinbasepro")

print(exchangeDetails)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v1/coinbasepro?apiKey=*")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v1/coinbasepro?apiKey=*")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v1/coinbasepro?apiKey=*")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### Response Object

Example URL: [https://api.abyiss.com/v1/coinbasepro?apiKey=](https://api.abyiss.com/v1/coinbasepro?apiKey=)

```json
{
    "name": "Coinbase Pro",
    "id": "coinbasepro",
    "countries": [
        "US"
    ],
    "hasTrades": true,
    "hasAggregates": true,
    "aggregateTimeframes": {
        "1m": 60,
        "5m": 300,
        "15m": 900,
        "1h": 3600,
        "6h": 21600,
        "1d": 86400
    },
    "url": "https://pro.coinbase.com/",
    "fees": [
        "https://docs.pro.coinbase.com/#fees",
        "https://support.pro.coinbase.com/customer/en/portal/articles/2945310-fees"
    ],
    "docs": "https://docs.pro.coinbase.com",
    "logo": "https://user-images.githubusercontent.com/1294454/41764625-63b7ffde-760a-11e8-996d-a6328fa9347a.jpg"
}
```

### Response Attribute

| Attribute Name      | Data Type          | Description                                                                 |
| ------------------- | ------------------ | --------------------------------------------------------------------------- |
| name                | string             | The official name of the exchange.                                          |
| id                  | string             | Unique identifier used by Abyiss for the exchange.                          |
| countries           | object             | The countries abbreviations the exchange is located in.                     |
| hasTrades           | boolean            | Can query market trades.                                                    |
| hasAggregates       | boolean            | Can query market candle aggregates. (1m, 5m, 15m, 1h, 6h, 1d)               |
| aggregateTimeframes | object             | Timeframes supported for market candle aggregates. (Spot, Derivatives, Dex) |
| url                 | string             | Exchange's official website URL.                                            |
| fees                | object \|\| string | The URL to for Exchange Fee Structure.                                      |
| docs                | string             | The URL for the Exchange Documentation.                                     |
| logo                | string             | The URL to the Exchange Logos.                                              |
