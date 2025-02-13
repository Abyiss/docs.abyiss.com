---
description: Get order books returns a full order book for a crypto pair from an exchange.
---

# Order Books

## Get Order Books

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/cex/{exchange}/{market}/orders`

Returns a snapshot of the recent level 2 orderbook for a crypto pair on an exchange.

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
    "market":"BTC/USD",
    "nonce":14601360013,
    "bids":
    [
        [
            61947.91,
            1.48088
        ],
        [
            61947.9,
            0.5
        ],
        [
            61944.07,
            0.44094
        ]
    ],
    "asks":
    [
        [
            61947.92,
            2.28573
        ],
        [
            61952.89,
            0.11214
        ],
        [
            61952.9,
            0.50224
        ]
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
curl -H "apiKey: API KEY" https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/orders?apiKey=*
```
{% endtab %}

{% tab title="Python" %}
```python
from Abyiss import Abyiss

apiKey = "YOUR API KEY" 
client = Abyiss.Client(apiKey)

orderbook = client.orderBook("coinbasepro", "BTC-USDT")

print(orderBook)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/orders?apiKey=*")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/orders?apiKey=*")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/orders?apiKey=*")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### Response Object

Example URL: [https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/orders?apiKey=](https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/orders?apiKey=)

```json
{
    "exchange":"coinbasepro",
    "market":"BTC/USD",
    "nonce":14601360013,
    "bids":
    [
        [
            61947.91,
            1.48088
        ],
        [
            61947.9,
            0.5
        ],
        [
            61944.07,
            0.44094
        ]
    ],
    "asks":
    [
        [
            61947.92,
            2.28573
        ],
        [
            61952.89,
            0.11214
        ],
        [
            61952.9,
            0.50224
        ]
    ]
}
```

### Response Attributes

| Attribute Name | Data Type | Description                                                      |
| -------------- | --------- | ---------------------------------------------------------------- |
| exchange       | string    | The exchange id the order book is from.                          |
| market         | string    | The crypto pair the order book is about.                         |
| nonce          | integer   | The serial unique identifier of the order book on the exchange.  |
| bids           | array     | Arrays of bids in the market \[\[float, float], \[float, float]] |
| asks           | array     | Arrays of asks in the market \[\[float, float], \[float, float]] |

