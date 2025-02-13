---
description: Get exchange status returns the current status of a crypto exchange.
---

# Exchange Status

## Get Exchange Status

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/cex/{exchange}/status`

Returns an object with properties that describe an exchange's status.

#### Path Parameters

| Name                                       | Type   | Description                                |
| ------------------------------------------ | ------ | ------------------------------------------ |
| exchange<mark style="color:red;">\*</mark> | string | Unique exchange identifier used by Abyiss. |

#### Query Parameters

| Name   | Type   | Description         |
| ------ | ------ | ------------------- |
| apiKey | string | Your Abyiss API Key |

{% tabs %}
{% tab title="200: OK Success" %}
```javascript
{
    "status":"ok",
    "updated":1634929487916
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
curl -H "apiKey: API KEY" https://api.abyiss.com/v2/cex/coinbasepro/status
```
{% endtab %}

{% tab title="Python" %}
```python
from Abyiss import Abyiss

apiKey = "YOUR API KEY" 
client = Abyiss.Client(apiKey)

exchangeStatus = client.getExchangeStatus("coinbasepro")

print(exchangeStatus)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v2/cex/coinbasepro/status?apiKey=*")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v2/cex/coinbasepro/status?apiKey=*")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```javascript
require 'net/http'
uri = URI("https://api.abyiss.com/v2/cex/coinbasepro/status?apiKey=*")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### Response Object&#x20;

Example URL: [https://api.abyiss.com/v2/cex/coinbasepro/status?apiKey=](https://api.abyiss.com/v2/cex/coinbasepro/status?apiKey=)

```json
{
    "status":"ok",
    "updated":1634929487916
}
```

### Response Attribute

| Attribute Name | Data Type | Description                                                      |
| -------------- | --------- | ---------------------------------------------------------------- |
| status         | string    | Status of the exchange. 'ok' is good.                            |
| updated        | integer   | Unix timestamp of the last time the exchange status was updated. |
