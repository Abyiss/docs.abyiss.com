---
description: Get last aggregate returns the latest aggregate bar for a crypto pair.
---

# Last Aggregate

## Get Last Aggregate

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v1/{exchange}/{market}/lastaggregate/{aggregate size}`

Returns an object with the latest aggregate or candlestick of a crypto pair.

#### Path Parameters

| Name                                             | Type   | Description                                                        |
| ------------------------------------------------ | ------ | ------------------------------------------------------------------ |
| exchange<mark style="color:red;">\*</mark>       | string | Unique exchange identifier used by Abyiss.                         |
| market<mark style="color:red;">\*</mark>         | string | Unique Crypto Pair identifier used by the exchange.                |
| aggregate size<mark style="color:red;">\*</mark> | string | Aggregate bar or candlestick time frame. (1m, 5m, 15m, 1h, 6h, 1d) |

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
    "timeframe": "1m",
    "t": 1644515400000,
    "o": 45203.6,
    "h": 45216.72,
    "l": 45183.93,
    "c": 45200.37,
    "v": 5.43995508
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
curl -H "apiKey: API KEY" https://api.abyiss.com/v1/coinbasepro/BTC-USD/lastaggregate/1m?apiKey=*
```
{% endtab %}

{% tab title="Python" %}
```python
import urllib.request
url = "https://api.abyiss.com/v1/coinbasepro/BTC-USD/lastaggregate/1m?apiKey=*"
print(urllib.request.urlopen(url).read())
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v1/coinbasepro/BTC-USD/lastaggregate/1m?apiKey=*")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v1/coinbasepro/BTC-USD/lastaggregate/1m?apiKey=*")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v1/coinbasepro/BTC-USD/lastaggregate/1m?apiKey=*")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### Response Object

Example URL: [https://api.abyiss.com/v1/coinbasepro/BTC-USD/lastaggregate/1m?apiKey=](https://api.abyiss.com/v1/coinbasepro/BTC-USD/lastaggregate/1m?apiKey=)

```json
{
    "exchange": "coinbasepro",
    "market": "BTC/USD",
    "timeframe": "1m",
    "t": 1644515400000,
    "o": 45203.6,
    "h": 45216.72,
    "l": 45183.93,
    "c": 45200.37,
    "v": 5.43995508
}
```

### Response Attributes&#x20;

| Attribute Name | Data Type | Description                                                        |
| -------------- | --------- | ------------------------------------------------------------------ |
| exchange       | string    | Unique identifier used by Abyiss for the exchange.                 |
| market         | string    | Unique identifier used by the exchange for ticker.                 |
| timeframe      | string    | Aggregate bar or candlestick time frame. (1m, 5m, 15m, 1h, 6h, 1d) |
| t              | integer   | Unix timestamp at the start of the aggregate.                      |
| o              | float     | The open or first price of the aggregate.                          |
| h              | float     | The highest price of the aggregate.                                |
| l              | float     | The lowest price of the aggregate.                                 |
| c              | float     | The close or last price of the aggregate.                          |
| v              | float     | The volume or quantity traded within the aggregate.                |
