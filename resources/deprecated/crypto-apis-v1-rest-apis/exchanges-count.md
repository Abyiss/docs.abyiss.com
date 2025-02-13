---
description: Get exchanges count returns the number of crypto exchanges Abyiss supports.
---

# Exchanges Count

## Get Exchange Count

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v1/exchanges/count`

Returns the number of crypto exchanges Abyiss supports.

#### Query Parameters

| Name                                     | Type   | Description         |
| ---------------------------------------- | ------ | ------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key |

{% tabs %}
{% tab title="200: OK Success" %}
```javascript
{
    "count": 118
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
curl -H "apiKey: API KEY" https://api.abyiss.com/v1/exchanges/count
```
{% endtab %}

{% tab title="Python" %}
```python
import urllib.request
url = "https://api.abyiss.com/v1/exchanges/count?apiKey=*"
print(urllib.request.urlopen(url).read())
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v1/exchanges/count?apiKey=*")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v1/exchanges/count?apiKey=*")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v1/exchanges/count?apiKey=*")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### **Response Object**

Example URL: [https://api.abyiss.com/v1/exchanges/count?apiKey=](https://api.abyiss.com/v1/exchanges/count?apiKey=)

```json
{
    "count": 118
}
```

### Response Attributes

| Attribute Name | Data Type | Description                                    |
| -------------- | --------- | ---------------------------------------------- |
| count          | integer   | The number of Crypto Exchanges Abyiss supports |

