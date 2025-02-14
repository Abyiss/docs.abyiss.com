---
description: >-
  The Octane Assets API gets the all the cryptocurrencies and blockchains
  supported for transactions.
---

# Assets

Crypto API for Octane: Crypto On and Off Ramp. This endpoint gets the cryptocurrencies supported for transactions.

## Asset API Endpoint

## Get Cryptocurrencies

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/octane/crypto`

Returns an object containing information related to what assets the Abyiss Network supports.&#x20;

#### Headers

| Name                                     | Type   | Description         |
| ---------------------------------------- | ------ | ------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key |

{% tabs %}
{% tab title="200: OK -- Success" %}
```json
{
  "supportedBlockchains": [
    "ethereum",
    "solana",
    "bitcoin",
    "dogecoin"
  ],
  "fiatCurrencies": {
    "USD": {
      "name": "United States Dollar",
      "base": "USD",
      "logo": "https://raw.githubusercontent.com/abyiss/cryptoicons/master/SVG/usd.svg"
    }
  },
  "tokens": {
    "AAVE": {
      "base": "AAVE",
      "logo": "https://raw.githubusercontent.com/abyiss/cryptoicons/master/SVG/aave.svg",
      "name": "Aave",
      "quotes": ["USD"],
      "blockchains": ["ethereum"],
      "decimals": 18,
      "limits": { "min": 0.001, "max": null }
    },
    "ALI": {
      "base": "ALI",
      "logo": "https://raw.githubusercontent.com/abyiss/cryptoicons/master/SVG/ali.svg",
      "name": "Alethea Artificial Liquid Intelligence",
      "quotes": ["USD"],
      "blockchains": ["ethereum"],
      "decimals": 18,
      "limits": { "min": 2, "max": null }
    }
  },
  "tokensbyBlockchain": {
    "ethereum": [{
      "base": "AAVE",
      "logo": "https://raw.githubusercontent.com/abyiss/cryptoicons/master/SVG/aave.svg",
      "name": "Aave",
      "quotes": ["USD"],
      "blockchains": ["ethereum"],
      "decimals": 18,
      "limits": { "min": 0.001, "max": null }
    }],
    "solana": [{
      "base": "BOME",
      "logo": "https://raw.githubusercontent.com/abyiss/cryptoicons/master/SVG/bome.svg",
      "name": "BOOK OF MEME",
      "quotes": ["USD"],
      "blockchains": ["solana"],
      "decimals": 6,
      "limits": { "min": 10, "max": null }
    },
  }
}
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

| Attribute Name       | Data Type        | Description |
| -------------------- | ---------------- | ----------- |
| supportedBlockchains | array of strings | Blockchains Supported by Abyiss |
| fiatCurrencies       | object           | Supported Fiat Currencies |
| tokens               | object           | Supported Tokens |
| tokensbyBlockchain   | object           | Supported Tokens by Blockchain |
| defaultTokens        | object           | Default Tokens Displayed on Abyiss Widget |
