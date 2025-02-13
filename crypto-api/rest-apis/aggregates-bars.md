---
description: Get aggregates returns candlestick bars for a crypto pair.
---

# Aggregates (Bars)

## Get Aggregates (Bars)

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/cex/{exchange}/{market}/aggregates/{aggregate size}`

Returns an object with the latest aggregates or candlesticks of a crypto pair.

#### Path Parameters

| Name                                             | Type   | Description                                                        |
| ------------------------------------------------ | ------ | ------------------------------------------------------------------ |
| exchange<mark style="color:red;">\*</mark>       | string | Unique exchange identifier used by Abyiss.                         |
| market<mark style="color:red;">\*</mark>         | string | Unique Crypto Pair identifier used by the exchange.                |
| aggregate size<mark style="color:red;">\*</mark> | string | Aggregate bar or candlestick time frame. (1m, 5m, 15m, 1h, 6h, 1d) |

#### Query Parameters

| Name                                     | Type   | Description                                                             |
| ---------------------------------------- | ------ | ----------------------------------------------------------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key                                                     |
| limit                                    | string | Number of results per request. Maximum 50,000. (default 200)            |
| since                                    | number | Unix Timestamp from where you want the data to start. (Historical Data) |

{% tabs %}
{% tab title="200: OK Success" %}
```javascript
{
    "exchange": "coinbasepro",
    "market": "BTC/USD",
    "aggregates": [
        {
        "t": 1644496320000,
        "o": 44714.52,
        "h": 44770.05,
        "l": 44714.52,
        "c": 44751.17,
        "v": 2.88395739
        },
        {
        "t": 1644496380000,
        "o": 44752,
        "h": 44753.14,
        "l": 44713.07,
        "c": 44747.05,
        "v": 10.80901469
        },
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
curl -H "apiKey: API KEY" https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/aggregates/1m
```
{% endtab %}

{% tab title="Python" %}
```python
from Abyiss import Abyiss

apiKey = "YOUR API KEY" 
client = Abyiss.Client(apiKey)

aggregates = client.aggregates("coinbasepro", "BTC-USD", "1m", "250")

print(aggregates)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/aggregates/1m?apiKey=*")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/aggregates/1m?apiKey=*")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```javascript
require 'net/http'
uri = URI("https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/aggregates/1m?apiKey=*")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### Response Object

Example URL: [https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/aggregates/1m?apiKey=](https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/aggregates/1m?apiKey=)

```json
{
    "exchange": "coinbasepro",
    "market": "BTC/USD",
    "aggregates": [
        {
        "t": 1644496320000,
        "o": 44714.52,
        "h": 44770.05,
        "l": 44714.52,
        "c": 44751.17,
        "v": 2.88395739
        },
}
```

### Response Attributes <a href="#response-attributes" id="response-attributes"></a>

| Attribute Name | Data Type | Description                                         |
| -------------- | --------- | --------------------------------------------------- |
| exchange       | string    | Unique identifier used by Abyiss for the exchange.  |
| market         | string    | Unique identifier used by the exchange for ticker.  |
| aggregates     | array     | Array of Aggregates                                 |
| t              | integer   | Unix timestamp at the start of the aggregate.       |
| o              | float     | The open or first price of the aggregate.           |
| h              | float     | The highest price of the aggregate.                 |
| l              | float     | The lowest price of the aggregate.                  |
| c              | float     | The close or last price of the aggregate.           |
| v              | float     | The volume or quantity traded within the aggregate. |
