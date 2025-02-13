---
description: Get market details returns information about a crypto pair.
---

# Market Details

## Get Market Details

<mark style="color:blue;">`GET`</mark> `https://api.abyis.com/v2/cex/{exchange}/{market}`

Returns an object with properties about the crypto pair.

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
```javascript
{
    "exchange":"coinbasepro",
    "symbol":"BTC/USD",
    "id":"BTC-USD",
    "active":true,
    "base":"BTC",
    "quote":"USD",
    "percentage":true,
    "taker":0.005,
    "maker":0.005,
    "type":"spot"
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
```bash
curl -H "apiKey: API KEY" https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD
```
{% endtab %}

{% tab title="Python" %}
```python
from Abyiss import Abyiss

apiKey = "YOUR API KEY" 
client = Abyiss.Client(apiKey) 

exchangeMarketDetails = client.getMarketDetails("coinbasepro", "BTC-USD")

print(exchangeMarketDetails)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD?apiKey=*")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD?apiKey=*")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD?apiKey=*")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### Response Object

Example URL: [https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD?apiKey=](https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD?apiKey=)

```json
{
    "exchange":"coinbasepro",
    "symbol":"BTC/USD",
    "id":"BTC-USD",
    "active":true,
    "base":"BTC",
    "quote":"USD",
    "percentage":true,
    "taker":0.005,
    "maker":0.005,
    "type":"spot"
}
```

### Response Attributes

| Attribute Name | Data Type | Description                                                                  |
| -------------- | --------- | ---------------------------------------------------------------------------- |
| exchange       | string    | Unique identifier used by Abyiss for the exchange.                           |
| symbol         | string    | The symbol of the market.                                                    |
| id             | string    | Unique identifier used by Abyiss for the market.                             |
| active         | boolean   | Whether the market is active on the exchange.                                |
| base           | string    | The base of the market. eg: The quantity that is bought.                     |
| quote          | string    | The quote of the market. eg: The currency being compared.                    |
| percentage     | boolean   | Whether the taker and maker fee rate is a multiplier or a fixed flat amount. |
| taker          | float     | Taker fee rate, 0.002 = 0.2%.                                                |
| maker          | float     | Maker fee rate, 0.0016 = 0.16%.                                              |
| type           | string    | Exchange type that the market is listed on.                                  |
