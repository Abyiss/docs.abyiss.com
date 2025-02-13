---
description: Get current price returns the real-time price of a crypto pair.
---

# Current Price

## Get Current Price

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/cex/{exchange}/{market}/currentprice`

Returns an object with the real-time price of a crypto pair.&#x20;

#### Path Parameters

| Name                                       | Type   | Description                                         |
| ------------------------------------------ | ------ | --------------------------------------------------- |
| exchange<mark style="color:red;">\*</mark> | sring  | Unique exchange identifier used by Abyiss.          |
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
    "timestamp": "1644510051396",
    "price": 45202.18
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
curl -H "apiKey: API KEY" https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/currentprice
```
{% endtab %}

{% tab title="Python" %}
```python
import urllib.request
url = "https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/currentprice?apiKey=*"
print(urllib.request.urlopen(url).read())
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/currentprice?apiKey=*")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/currentprice?apiKey=*")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/currentprice?apiKey=*")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### **Response Object**

Example URL: https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/currentprice?apiKey=

```json
{
    "exchange": "coinbasepro",
    "market": "BTC/USD",
    "timestamp": "1644510051396",
    "price": 45202.18
}
```

### Response Attributes

| Attribute Name | Data Type | Description                                        |
| -------------- | --------- | -------------------------------------------------- |
| exchange       | string    | Unique identifier used by Abyiss for the exchange. |
| market         | string    | Unique identifier used by the exchange for ticker. |
| timestamp      | string    | Unix timestamp of the current price.               |
| price          | float     | The latest price of the crypto asset.              |
