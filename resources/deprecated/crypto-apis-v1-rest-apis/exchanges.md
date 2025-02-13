---
description: Get exchanges endpoint returns all crypto exchanges Abyiss supports.
---

# Exchanges

## Get Exchanges

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v1/exchanges`

Returns an array of all supported exchanges in the form of market objects.

#### Query Parameters

| Name                                     | Type   | Description         |
| ---------------------------------------- | ------ | ------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key |

{% tabs %}
{% tab title="200: OK Success" %}
```javascript
[
    {
        "name":"Binance",
        "id":"binance"
    },
    {
        "name":"Binance US",
        "id":"binanceus"
    },
    {
        "name":"Coinbase Pro",
        "id":"coinbasepro"
    },
    {
        "name":"BitBay",
        "id":"bitbay"
    }
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

### **Copy & Paste Code**

{% tabs %}
{% tab title="Curl" %}
```bash
curl -H "apiKey: API KEY" https://api.abyiss.com/v1/exchanges
```
{% endtab %}

{% tab title="Python" %}
```python
from Abyiss import Abyiss

apiKey = "YOUR API KEY" 
client = Abyiss.Client(apiKey)

exchanges = client.getExchanges()

print(exchanges)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v1/exchanges?apiKey=*")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v1/exchanges?apiKey=*")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v1/exchanges?apiKey=*")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### **Response Object**

Example URL: [https://api.abyiss.com/v1/exchanges?apiKey=](https://api.abyiss.com/v1/exchanges?apiKey=)

```json
{
    "name":"Binance",
    "id":"binance"
},
{
    "name":"Coinbase Pro",
    "id":"coinbasepro"
},
```

### Response Attributes

| Attribute Name | Data Type | Description                                |
| -------------- | --------- | ------------------------------------------ |
| name           | string    | The official name of the exchange.         |
| id             | string    | Unique exchange identifier used by Abyiss. |

