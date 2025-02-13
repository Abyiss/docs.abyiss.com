---
description: Get liquidity returns the total liquidity for a crypto pair on an exchange.
---

# Liquidity

{% hint style="danger" %}
**The `liquidity` endpoint is in beta. We do not recommend use in production.**&#x20;
{% endhint %}

## Get Liquidity

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/liquidity/{exchange}/{market}`

Returns an object containing the total liquidity for a crypto pair on an exchange.

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
<pre class="language-javascript"><code class="lang-javascript">{
<strong>    "exchange": "coinbasepro",
</strong>    "market": "BTC-USD",
    "nonce": 5640375978,
    "liquidity": 37224813.18828725
}
</code></pre>
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
curl -H "apiKey: API KEY" https://api.abyiss.com/v2/liquidity/coinbasepro/btc-usd
```
{% endtab %}

{% tab title="Python" %}
```python
import urllib.request
url = "https://api.abyiss.com/v2/liquidity/coinbasepro/btc-usd?apiKey=*"
print(urllib.request.urlopen(url).read())
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v2/liquidity/coinbasepro/btc-usd?apiKey=*")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v2/liquidity/coinbasepro/btc-usd?apiKey=*")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v2/liquidity/coinbasepro/btc-usd?apiKey=*")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### Response Object

Example URL: [https://api.abyiss.com/v2/liquidity/coinbasepro/btc-usd?apiKey=](https://api.abyiss.com/v2/liquidity/coinbasepro/btc-usd?apiKey=)

```json
{
    "exchange": "coinbasepro",
    "market": "BTC-USD",
    "nonce": 5640375978,
    "liquidity": 37224813.18828725
}
```

### Response Attributes

| Attribute Name | Data Type | Description                                                     |
| -------------- | --------- | --------------------------------------------------------------- |
| exchange       | string    | The exchange id.                                                |
| market         | string    | The crypto pair.                                                |
| nonce          | integer   | The serial unique identifier of the order book on the exchange. |
| liquidity      | integer   | The total liquidity for a crypto market pair.                   |

