---
description: Get snapshot returns the current price and aggregates of a crypto pair.
---

# Snapshot

## Get Snapshot

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v1/{exchange}/{market}/snapshot`

Returns an object with the current price and latest aggregates of a crypto pair.

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
    "currentPrice": {
    "timestamp": "1644514081304",
    "price": 45664.68
    },
    "lastAggregates": [
        {
        "timeframe": "1m",
        "t": 1644514020000,
        "o": 45611.24,
        "h": 45642.66,
        "l": 45603.99,
        "c": 45633.36,
        "v": 3.06919763
        },
        {
        "timeframe": "5m",
        "t": 1644513600000,
        "o": 45609.98,
        "h": 45618.75,
        "l": 45518.29,
        "c": 45556.56,
        "v": 68.72929794
        },
        {
        "timeframe": "15m",
        "t": 1644513300000,
        "o": 45700,
        "h": 45855,
        "l": 45518.29,
        "c": 45674.69,
        "v": 325.19832174
        },
        {
        "timeframe": "1h",
        "t": 1644512400000,
        "o": 45428.67,
        "h": 45855,
        "l": 45350,
        "c": 45553.23,
        "v": 539.73451388
        },
        {
        "timeframe": "6h",
        "t": 1644494400000,
        "o": 44871.79,
        "h": 45855,
        "l": 43210,
        "c": 45635.08,
        "v": 8832.20007482
        },
        {
        "timeframe": "1d",
        "t": 1644451200000,
        "o": 44416.39,
        "h": 45855,
        "l": 43210,
        "c": 45633.36,
        "v": 13322.95932161
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

### Copy & Paste Code

{% tabs %}
{% tab title="Curl" %}
```bash
curl -H "apiKey: API KEY" https://api.abyiss.com/v1/coinbasepro/BTC-USD/snapshot
```
{% endtab %}

{% tab title="Python" %}
```python
import urllib.request
url = "https://api.abyiss.com/v1/coinbasepro/BTC-USD/snapshot?apiKey=*"
print(urllib.request.urlopen(url).read())
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v1/coinbasepro/BTC-USD/snapshot?apiKey=*")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v1/coinbasepro/BTC-USD/snapshot?apiKey=*")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v1/coinbasepro/BTC-USD/snapshot?apiKey=*")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### Response Object

Example URL: [https://api.abyiss.com/v1/coinbasepro/BTC-USD/snapshot?apiKey=](https://api.abyiss.com/v1/coinbasepro/BTC-USD/snapshot?apiKey=)

```json
{
    "exchange": "coinbasepro",
    "market": "BTC/USD",
    "currentPrice": {
    "timestamp": "1644514081304",
    "price": 45664.68
    },
    "lastAggregates": [
        {
        "timeframe": "1m",
        "t": 1644514020000,
        "o": 45611.24,
        "h": 45642.66,
        "l": 45603.99,
        "c": 45633.36,
        "v": 3.06919763
        },
        {
        "timeframe": "5m",
        "t": 1644513600000,
        "o": 45609.98,
        "h": 45618.75,
        "l": 45518.29,
        "c": 45556.56,
        "v": 68.72929794
        },
        {
        "timeframe": "15m",
        "t": 1644513300000,
        "o": 45700,
        "h": 45855,
        "l": 45518.29,
        "c": 45674.69,
        "v": 325.19832174
        },
        {
        "timeframe": "1h",
        "t": 1644512400000,
        "o": 45428.67,
        "h": 45855,
        "l": 45350,
        "c": 45553.23,
        "v": 539.73451388
        },
        {
        "timeframe": "6h",
        "t": 1644494400000,
        "o": 44871.79,
        "h": 45855,
        "l": 43210,
        "c": 45635.08,
        "v": 8832.20007482
        },
        {
        "timeframe": "1d",
        "t": 1644451200000,
        "o": 44416.39,
        "h": 45855,
        "l": 43210,
        "c": 45633.36,
        "v": 13322.95932161
        }
    ]
}
```

### Response Attributes

| Attribute Name | Data Type | Description                                                        |
| -------------- | --------- | ------------------------------------------------------------------ |
| exchange       | string    | Unique identifier used by Abyiss for the exchange.                 |
| market         | string    | Unique identifier used by the exchange for ticker.                 |
| currentPrice   | object    | Object with the time and price                                     |
| timestamp      | string    | Unix timestamp of the current price.                               |
| price          | float     | The latest price of the crypto asset.                              |
| timeframe      | string    | Aggregate bar or candlestick time frame. (1m, 5m, 15m, 1h, 6h, 1d) |
| lastAggregates | array     | Array of aggregates                                                |
| t              | integer   | Unix timestamp at the start of the aggregate.                      |
| o              | float     | The open or first price of the aggregate.                          |
| h              | float     | The highest price of the aggregate.                                |
| l              | float     | The lowest price of the aggregate.                                 |
| c              | float     | The close or last price of the aggregate.                          |
| v              | float     | The volume or quantity traded within the aggregate.                |
