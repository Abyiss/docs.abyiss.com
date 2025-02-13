---
description: Get last aggregate returns the latest aggregate bar for a crypto pair.
---

# Trades

## Get Trades

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/cex/{exchange}/{market}/trades`

Returns an object with recent trades for a crypto pair on an exchange.

#### Path Parameters

| Name                                       | Type   | Description                                         |
| ------------------------------------------ | ------ | --------------------------------------------------- |
| exchange<mark style="color:red;">\*</mark> | string | Unique exchange identifier used by Abyiss.          |
| market<mark style="color:red;">\*</mark>   | string | Unique Crypto Pair identifier used by the exchange. |

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
    "trades": [
        {
            "id": "279352169",
            "timestamp": "1644524462830",
            "price": 44322.55,
            "size": 0.02209576,
            "cost": 979.340427388,
            "side": "buy"
        },
        {
            "id": "279352170",
            "timestamp": "1644524463216",
            "price": 44322.55,
            "size": 0.00030296,
            "cost": 13.427959748000001,
            "side": "buy"
        },
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
```shell
curl -H "apiKey: API KEY" https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/trades
```
{% endtab %}

{% tab title="Python" %}
```python
from Abyiss import Abyiss

apiKey = "YOUR API KEY"
client = Abyiss.Client(apiKey)

trades = client.trades("coinbasepro", "BTC-USD", "250")

print(trades)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/trades?apiKey=*")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/trades?apiKey=*")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/trades?apiKey=*")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### Response Object

Example URL: [https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/trades?apiKey=](https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/trades?apiKey=)

```json
{
    "exchange": "coinbasepro",
    "market": "BTC/USD",
    "trades": [
        {
            "id": "279352169",
            "timestamp": "1644524462830",
            "price": 44322.55,
            "size": 0.02209576,
            "cost": 979.340427388,
            "side": "buy"
        },
    ]
}
```

### Response Attributes

<table><thead><tr><th width="150">Attribute Name</th><th width="150">Data Type</th><th>Description</th></tr></thead><tbody><tr><td>exchange</td><td>string</td><td>The exchange id the trade occurred on.</td></tr><tr><td>market</td><td>string</td><td>The crypto pair that was traded.</td></tr><tr><td>trades</td><td>array</td><td>An array of trades</td></tr><tr><td>id</td><td>string</td><td>The exchange specific unique id of the trade.</td></tr><tr><td>timestamp</td><td>string</td><td>The Unix timestamp that trade was executed.</td></tr><tr><td>price</td><td>float</td><td>The quote currency price of the market.</td></tr><tr><td>size</td><td>float</td><td>The quantity traded.</td></tr><tr><td>cost</td><td>float</td><td>The quote cost: (size * price).</td></tr><tr><td>side</td><td>string</td><td>Whether the trade was a buy or sell.</td></tr></tbody></table>
