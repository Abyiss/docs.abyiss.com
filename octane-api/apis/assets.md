---
description: >-
  The Octane Assets API gets the all the cryptocurrencies and blockchains
  supported for transactions.
---

# Assets

{% hint style="warning" %}
**The Endpoint is in Beta**
{% endhint %}

Crypto API for Octane: Crypto On and Off Ramp. This endpoint gets the cryptocurrencies supported for transactions.

## Asset API Endpoint

## Get Cryptocurrencies

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/octane/crypto`

Returns an array of cryptocurrencies trading pairs supported for transactions.&#x20;

#### Headers

| Name                                     | Type   | Description         |
| ---------------------------------------- | ------ | ------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key |

{% tabs %}
{% tab title="200: OK -- Success" %}
```json
[
    "BTC/USD",
    "ETH/USD",
    "ZEC/USD",
    "BCH/USD",
    "LTC/USD",
    "BAT/USD",
    "DAI/USD",
    "LINK/USD",
    "OXT/USD",
    "AMP/USD",
    "COMP/USD",
    "PAXG/USD",
    "MKR/USD",
    "ZRX/USD",
    "MANA/USD",
    "STORJ/USD",
    "SNX/USD",
    "CRV/USD",
    "UNI/USD",
    "REN/USD",
    "UMA/USD",
    "YFI/USD",
    "AAVE/USD",
    "FIL/USD",
    "SKL/USD",
    "GRT/USD",
    "LRC/USD",
    "SAND/USD",
    "CUBE/USD",
    "LPT/USD",
    "MATIC/USD",
    "INJ/USD",
    "SUSHI/USD",
    "DOGE/USD",
    "FTM/USD",
    "ANKR/USD",
    "CTX/USD",
    "XTZ/USD",
    "AXS/USD",
    "LUNA/USD",
    "RARE/USD",
    "QNT/USD",
    "MASK/USD",
    "FET/USD",
    "API3/USD",
    "USDC/USD",
    "SHIB/USD",
    "RNDR/USD",
    "GALA/USD",
    "ENS/USD",
    "TOKE/USD",
    "LDO/USD",
    "RLY/USD",
    "SOL/USD",
    "APE/USD",
    "QRDO/USD",
    "ZBC/USD",
    "CHZ/USD",
    "JAM/USD",
    "GMT/USD",
    "ALI/USD",
    "DOT/USD",
    "ERN/USD",
    "GAL/USD",
    "SAMO/USD",
    "IMX/USD",
    "IOTX/USD",
    "AVAX/USD",
    "ATOM/USD",
    "USDT/USD",
    "PEPE/USD",
    "XRP/USD",
    "HNT/USD"
]
```
{% endtab %}

{% tab title="401: Unauthorized -- Invalid API Key" %}
```json
{
    "Unauthorized": "Invaild API Key"
}
```
{% endtab %}
{% endtabs %}

## **Copy & Paste Code**

**GET Assets**

{% tabs %}
{% tab title="Curl" %}
```bash
curl "https://api.abyiss.com/v2/octane/crypto?apiKey=YOUR_API_KEY_HERE"
```
{% endtab %}

{% tab title="Python" %}
```python
import requests

url = 'https://api.abyiss.com/v2/octane/crypto?apiKey=YOUR_API_KEY_HERE'

response = requests.get(url)

print(response.status_code)  # This will print the status code of the response
print(response.json())  # This will print the response content as JSON
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
const url = 'https://api.abyiss.com/v2/octane/crypto?apiKey=YOUR_API_KEY_HERE';

fetch(url)
  .then(response => {
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    return response.json();
  })
  .then(data => {
    console.log(data); // Handle the response data
  })
  .catch(error => {
    console.error('There has been a problem with your fetch operation:', error);
  });
```
{% endtab %}
{% endtabs %}

## Asset **Response Object**

{% tabs %}
{% tab title="Get Crypto" %}
Example URL: [https://api.abyiss.com/v2/octane/crypto?apiKey=YOUR\_API\_KEY\_HERE](https://api.abyiss.com/v2/octane/crypto?apiKey=YOUR_API_KEY_HERE)

```json
[
    "BTC/USD",
    "ETH/USD",
    "ZEC/USD",
    "BCH/USD",
    "LTC/USD",
    "BAT/USD",
    "DAI/USD",
]
```
{% endtab %}
{% endtabs %}

## Asset Response Attributes

| Attribute Name | Data Type | Description         |
| -------------- | --------- | ------------------- |
| cryptoPairs    | string    | Crypto Trading Pair |

