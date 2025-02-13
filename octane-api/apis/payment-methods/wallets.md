---
description: The Crypto Wallets API
---

# Wallets

{% hint style="warning" %}
**The Endpoint is in Beta**
{% endhint %}

## Introduction

The Octane Wallets API provides developers with functionality to manage and retrieve information related to crypto wallets with their accounts.&#x20;

* **Wallets:**
  * Obtain a detailed list of wallets linked to a specific API key.
  * Fetch specific wallet details by querying with the wallet ID.
  * Facilitate the creation of new wallets by submitting wallet information in the request body.
  * Deletes a specific wallet by providing the wallet ID.

## Wallet API Endpoints

### Post Wallets

<mark style="color:green;">`POST`</mark> `https://api.abyiss.com/v2/octane/paymentMethods/wallets`

Create a new crypto wallet by providing the required wallet details. Upon a successful request, it returns a 201 status code along with the details of the created wallet.

**Headers**

| Name                                     | Type   | Description         |
| ---------------------------------------- | ------ | ------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key |

**Request Body**

| Name                                         | Type   | Description                                   |
| -------------------------------------------- | ------ | --------------------------------------------- |
| address<mark style="color:red;">\*</mark>    | string | The wallet address,                           |
| blockchain<mark style="color:red;">\*</mark> | string | The blockchain the wallet is associated with. |

{% tabs %}
{% tab title="201: Created -- Success" %}
```json
{
    "id": "wal-123456785",
    "userId": "usr-123456788",
    "address": "some-addy",
    "blockchain": "some-chain",
    "isActive": true,
    "isVerified": false,
    "createdAt": "2024-02-02T02:09:55.963",
    "updatedAt": "2024-02-02T02:09:55.958"
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

### Get Wallets

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/octane/paymentMethods/wallets`

Retrieves all crypto wallets associated with the provided API key. Upon a successful request, it returns a 200 status code and a list of wallets.

**Headers**

| Name                                     | Type   | Description         |
| ---------------------------------------- | ------ | ------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key |

{% tabs %}
{% tab title="200: OK -- Success" %}
```json
[
    {
        "id": "wal-123456788",
        "userId": "usr-123456788",
        "address": "someAddress",
        "blockchain": "ethereum",
        "isActive": true,
        "isVerified": true,
        "createdAt": "2024-01-30T15:06:08.568",
        "updatedAt": "2024-01-30T15:06:08.563"
    },
    {
        "id": "wal-123456785",
        "userId": "usr-123456788",
        "address": "1234568",
        "blockchain": "bitcoin",
        "isActive": true,
        "isVerified": false,
        "createdAt": "2024-02-02T02:09:55.963",
        "updatedAt": "2024-02-02T02:09:55.958"
    }
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

### Get Wallet by ID

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/octane/paymentMethods/wallets/{walletId}`

Retrieves the details of a specific crypto wallet using its unique wallet ID. Upon a successful request, it returns a 200 status code and the details of the requested wallet.

**Headers**

| Name                                     | Type   | Description         |
| ---------------------------------------- | ------ | ------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key |

**Query Parameters**

| Name                                       | Type   | Description |
| ------------------------------------------ | ------ | ----------- |
| walletId<mark style="color:red;">\*</mark> | string | Wallet Id   |

{% tabs %}
{% tab title="200: OK -- Success" %}
```json
{
    "id": "wal-123456785",
    "userId": "usr-123456788",
    "address": "some-addy",
    "blockchain": "bitcoin",
    "isActive": true,
    "isVerified": false,
    "createdAt": "2024-02-02T02:09:55.963",
    "updatedAt": "2024-02-02T02:09:55.958"
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

### Delete Wallet by ID

<mark style="color:red;">`DELETE`</mark>`https://api.abyiss.com/v2/octane/paymentMethods/wallets/{walletId}`

Deletes a specified crypto wallet using its unique wallet ID. Upon a successful request, it returns a 204 status code indicating that the wallet has been deleted.

**Headers**

| Name                                     | Type   | Description         |
| ---------------------------------------- | ------ | ------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key |

**Query Parameters**

| Name                                       | Type   | Description |
| ------------------------------------------ | ------ | ----------- |
| walletId<mark style="color:red;">\*</mark> | string | Wallet Id   |

**Response**

{% tabs %}
{% tab title="204: No Content -- Deleted" %}
```json
No Content
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

### **POST Wallets**

{% tabs %}
{% tab title="Curl" %}
```bash
curl -X POST \
  -H "Content-Type: application/json" \
  -H "apiKey: 123abc" \
  -d '{
    "wallet": {
      "address": "0xsome-address",
      "blockchain": "Ethereum",
    }
  }' \
  https://api.abyiss.com/v2/octane/paymentMethods/wallets
```
{% endtab %}

{% tab title="Python" %}
```python
import requests
import json

url = "https://api.abyiss.com/v2/octane/paymentMethods/wallets"
headers = {
    "Content-Type": "application/json",
    "apiKey": "123abc"
}

wallet_data = {
    "wallet": {
        "address": "0xsome-address",
        "blockchain": "Ethereum"
    }
}

response = requests.post(url, headers=headers, data=json.dumps(wallet_data))

print(response.status_code)
print(response.json())
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
const axios = require('axios');

const url = 'https://api.abyiss.com/v2/octane/paymentMethods/wallets';
const headers = {
    'Content-Type': 'application/json',
    'apiKey': '123abc'
};

const walletData = {
    wallet: {
        address: '0xsome-address',
        blockchain: 'Ethereum'
    }
};

axios.post(url, walletData, { headers })
    .then(response => {
        console.log(response.status);
        console.log(response.data);
    })
    .catch(error => {
        console.error(error.response.status);
        console.error(error.response.data);
    });
```
{% endtab %}
{% endtabs %}

### **GET Wallets**

{% tabs %}
{% tab title="Curl" %}
```bash
curl "https://api.abyiss.com/v2/octane/paymentMethods/wallets?apiKey=YOUR_API_KEY_HERE"
```
{% endtab %}

{% tab title="Python" %}
```python
import requests

url = 'https://api.abyiss.com/v2/octane/paymentMethods/wallets?apiKey=YOUR_API_KEY_HERE'

response = requests.get(url)

print(response.status_code)  # This will print the status code of the response
print(response.json())  # This will print the response content as JSON
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
const url = 'https://api.abyiss.com/v2/octane/paymentMethods/wallets?apiKey=YOUR_API_KEY_HERE';

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

## **Wallets Response Object**

{% tabs %}
{% tab title="POST Wallets" %}
Example URL: [https://api.abyiss.com/v2/octane/paymentMethods/wallets?apiKey=](https://api.abyiss.com/v2/octane/paymentMethods/wallets?apiKey=)

```json
{
    "id": "wal-123456785",
    "userId": "usr-123456788",
    "address": "some-addy",
    "blockchain": "some-chain",
    "isActive": true,
    "isVerified": false,
    "createdAt": "2024-02-02T02:09:55.963",
    "updatedAt": "2024-02-02T02:09:55.958"
}
```
{% endtab %}

{% tab title="Get Wallets" %}
Example URL: [https://api.abyiss.com/v2/octane/paymentMethods/wallets?apiKey=](https://api.abyiss.com/v2/octane/paymentMethods/wallets?apiKey=)

```json
[
    {
        "id": "wal-123456788",
        "userId": "usr-123456788",
        "address": "someAddress",
        "blockchain": "ethereum",
        "isActive": true,
        "isVerified": false,
        "createdAt": "2024-01-30T15:06:08.568",
        "updatedAt": "2024-01-30T15:06:08.563"
    },
    {
        "id": "wal-123456785",
        "userId": "usr-123456788",
        "address": "some-addy",
        "blockchain": "some-chain",
        "isActive": true,
        "isVerified": false,
        "createdAt": "2024-02-02T02:09:55.963",
        "updatedAt": "2024-02-02T02:09:55.958"
    }
]
```
{% endtab %}

{% tab title="Get Wallet by Id" %}
Example URL: [https://api.abyiss.com/v2/octane/paymentMethods/wallets/wal-123456785?apiKey=](https://api.abyiss.com/v2/octane/paymentMethods/wallets/wal-123456785?apiKey=)

```json
{
    "id": "wal-123456785",
    "userId": "usr-123456788",
    "address": "some-addy",
    "blockchain": "some-chain",
    "isActive": true,
    "isVerified": false,
    "createdAt": "2024-02-02T02:09:55.963",
    "updatedAt": "2024-02-02T02:09:55.958"
}
```
{% endtab %}
{% endtabs %}

## Wallets Response Attributes

<table><thead><tr><th width="259.3333333333333">Attribute Name</th><th>Data Type</th><th>Description </th></tr></thead><tbody><tr><td>id</td><td>string</td><td>Wallet Id for the user.</td></tr><tr><td>userId</td><td>string </td><td>Unique user Id. </td></tr><tr><td>address</td><td>string</td><td>The crypto wallet address.</td></tr><tr><td>blockchain</td><td>string</td><td>The blockchain the wallet is on.</td></tr><tr><td>isActive</td><td>boolean</td><td>If the wallet is currently active. True or False.</td></tr><tr><td>isVerified</td><td>boolean</td><td>Indicates whether the wallet has been verified to exist.</td></tr><tr><td>createdAt</td><td>string</td><td>The timestamp the wallet was updated at.</td></tr><tr><td>updatedAt</td><td>string</td><td>The last timestamp the wallet was updated at.</td></tr></tbody></table>

