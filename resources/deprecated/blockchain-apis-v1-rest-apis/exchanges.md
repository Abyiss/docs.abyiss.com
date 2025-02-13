---
description: Get exchanges returns all decentralized exchanges supported by Abyiss.
---

# Exchanges

## Get Exchanges

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v1/dex`

Returns an array of all supported decentralized exchanges.

#### Query Parameters

| Name                                     | Type   | Description         |
| ---------------------------------------- | ------ | ------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key |

{% tabs %}
{% tab title="200: OK Success" %}
```javascript
[
    {
        "name": "Uniswap",
        "id": "uniswap"
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
curl -H "apiKey: API KEY" https://api.abyiss.com/v1/dex
```
{% endtab %}

{% tab title="Python" %}
```python
import urllib.request
url = "https://api.abyiss.com/v1/dex?apiKey=*"
print(urllib.request.urlopen(url).read())
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v1/dex?apiKey=*")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v1/dex?apiKey=*")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v1/dex?apiKey=*")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### **Response Object**

Example URL: [https://api.abyiss.com/v1/dex?apiKey=](https://api.abyiss.com/v1/dex?apiKey=)

```json
[
    {
        "name": "Uniswap",
        "id": "uniswap"
    }
]
```

### Response Attributes

| Attribute Name | Data Type | Description                                |
| -------------- | --------- | ------------------------------------------ |
| name           | string    | The official name of the exchange.         |
| id             | string    | Unique exchange identifier used by Abyiss. |

