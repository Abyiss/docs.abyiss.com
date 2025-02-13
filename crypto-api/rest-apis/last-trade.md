---
description: Get last trade returns the most recent trade for a crypto pair.
---

# Last Trade

## Get Last Trade

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/cex/{exchange}/{market}/lasttrade`

Returns an object containing the latest trade for a crypto pair on an exchange.

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
    "exchange": "coinbasepro",
    "market": "BTC/USD",
    "id": "279363545",
    "timestamp": "1644525461042",
    "price": 43990.48,
    "size": 0.00608355,
    "cost": 267.618284604,
    "side": "buy"
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
curl -H "apiKey: API KEY" https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/lasttrade
```
{% endtab %}

{% tab title="Python" %}
```python
import urllib.request
url = "https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/lasttrade?apiKey=*"
print(urllib.request.urlopen(url).read())
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/lasttrade?apiKey=*")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/lasttrade?apiKey=*")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/lasttrade?apiKey=*")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### Response Object

Example URL: [https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/lasttrade?apiKey=](https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/lasttrade?apiKey=)

```json
{
    "exchange": "coinbasepro",
    "market": "BTC/USD",
    "id": "279363545",
    "timestamp": "1644525461042",
    "price": 43990.48,
    "size": 0.00608355,
    "cost": 267.618284604,
    "side": "buy"
}
```

### Response Attributes

| Attribute Name | Data Type | Description                                   |
| -------------- | --------- | --------------------------------------------- |
| exchange       | string    | The exchange id the trade occurred on.        |
| market         | string    | The crypto pair that was traded.              |
| id             | string    | The exchange specific unique id of the trade. |
| timestamp      | string    | The Unix timestamp that trade was executed.   |
| price          | float     | The quote currency price of the market.       |
| size           | float     | The quantity traded.                          |
| cost           | float     | The quote cost: (size \* price).              |
| side           | string    | Whether the trade was a buy or sell.          |
