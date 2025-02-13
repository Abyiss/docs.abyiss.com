---
description: Get exchange markets returns all crypto pairs on a crypto exchange.
---

# Exchange Markets

## Get Exchange Markets

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/cex/{exchange}/markets`

Returns an array of all crypto pair ids on the exchange.

#### Path Parameters

| Name                                       | Type   | Description                                |
| ------------------------------------------ | ------ | ------------------------------------------ |
| exchange<mark style="color:red;">\*</mark> | string | Unique exchange identifier used by Abyiss. |

#### Query Parameters

| Name                                     | Type   | Description         |
| ---------------------------------------- | ------ | ------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key |

{% tabs %}
{% tab title="200: OK Success" %}
```javascript
[
    "OGN/BTC",
    "REQ/BTC",
    "KEEP/USD",
    "AAVE/USD",
    "SKL/GBP",
    "MIR/EUR",
    "FORTH/EUR",
    "DOT/USDT"
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

### Copy & Paste Code

{% tabs %}
{% tab title="Curl" %}
```shell
curl -H "apiKey: API KEY" https://api.abyiss.com/v2/cex/coinbasepro/markets
```
{% endtab %}

{% tab title="Python" %}
```python
from Abyiss import Abyiss

apiKey = "YOUR API KEY" 
client = Abyiss.Client(apiKey) 

exchangeMarkets = client.getExchangeMarkets("coinbasepro")

print(exchangeMarkets)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v2/cex/coinbasepro/markets?apiKey=*")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v2/cex/coinbasepro/markets?apiKey=*")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v2/cex/coinbasepro/markets?apiKey=*")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### Response Object

Example URL: [https://api.abyiss.com/v2/cex/coinbasepro/markets?apiKey=](https://api.abyiss.com/v2/cex/coinbasepro/markets?apiKey=)

```json
[
    "BTC/USD",
    "ETH/USD",
    "DOGE/USD",
    "DOT/USDT"
]
```

### Response Attribute

| Attribute Name | Data Type | Description                                         |
| -------------- | --------- | --------------------------------------------------- |
| pair id        | string    | Unique Crypto Pair identifier used by the exchange. |
