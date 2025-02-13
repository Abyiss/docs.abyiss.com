---
description: >-
  The Transactions API within Octane empowers you to efficiently manage and
  retrieve orders associated with your account.
---

# Transactions

{% hint style="warning" %}
**The Endpoint is in Beta**
{% endhint %}

Creating and managing transactions with the Octane Transactions API is a straightforward process:

* **Create Transaction (POST):**
  * Use the `/v2/octane/transactions` endpoint.
  * Provide essential details like blockchain type, currency pairs, quantities, and associated wallet and bank account information in the request body.
  * Results in successful order creation with timestamp and transaction type details.
* **Retrieve All Orders (GET):**
  * Utilize the `/v2/octane/transactions` endpoint with a GET request.
  * Retrieve all orders linked to the provided apiKey.
  * Access detailed information such as IDs, blockchain specifics, currencies involved, and timestamps.
  * Upcoming filtering options allow you to refine results.
* **Retrieve Specific Order (GET):**
  * Access details of a specific order using the `/v2/octane/transactions/:Id` endpoint.
  * Provide the order's ID and apiKey.
  * Retrieve comprehensive details, including transaction types, completion status, and precise currency exchange specifics.

## Transactions API Endpoints

## Post Transaction

<mark style="color:green;">`POST`</mark> `https://api.abyiss.com/v2/octane/transactions`

Returns a 201 status code upon successful query. Then returns the successful order. Requires user to have associated bank account and wallet.

#### Headers

| Name                                     | Type   | Description   |
| ---------------------------------------- | ------ | ------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Blockchain ID |

#### Request Body

| Name                                            | Type   | Description                                                    |
| ----------------------------------------------- | ------ | -------------------------------------------------------------- |
| sellOrder<mark style="color:red;">\*</mark>     | object | Information about the sell order.                              |
| walletId<mark style="color:red;">\*</mark>      | string | ID of the wallet associated with the sell order.               |
| blockchain<mark style="color:red;">\*</mark>    | string | Blockchain used for the sell order.                            |
| currency<mark style="color:red;">\*</mark>      | string | Currency to be sold.                                           |
| quantity<mark style="color:red;">\*</mark>      | string | Quantity of the currency to be sold.                           |
| buyOrder<mark style="color:red;">\*</mark>      | object | Information about the buy order                                |
| bankAccountId<mark style="color:red;">\*</mark> | string | The bank ID which the money will be sent to or received from.  |
| currency<mark style="color:red;">\*</mark>      | string | Currency to be bought                                          |

{% tabs %}
{% tab title="201: Created Success" %}
```json
{
    "id": "txn-123456815",
    "type": "OFF_RAMP",
    "createdAt": "2024-02-02T01:40:48.492",
    "flaggedAt": null,
    "completedAt": null,
    "updatedAt": "2024-02-02T01:40:48.487",
    "sellOrder": {
        "id": "ord-123456870",
        "bankAccountId": null,
        "blockchain": "avalanche",
        "createdAt": "2024-02-02T01:40:48.492",
        "currency": "AVAX",
        "feeUsd": null,
        "priceUsd": "6.85",
        "quantity": ".2004",
        "updatedAt": "2024-02-02T01:40:48.486",
        "walletId": "wal-123456790"
    },
    "buyOrder": {
        "id": "ord-123456871",
        "bankAccountId": "bac-123456788",
        "blockchain": null,
        "createdAt": "2024-02-02T01:40:48.492",
        "currency": "USD",
        "feeUsd": "0.17",
        "priceUsd": "6.85",
        "quantity": "6.67",
        "updatedAt": "2024-02-02T01:40:48.486",
        "walletId": "0x065149eab6eFa05F4639Da6305B58C91BD92d456"
    }
}
```
{% endtab %}

{% tab title="401: Unauthorized Unauthorized -- Invalid API Key" %}
```json
{
    "Unauthorized": "Invaild API Key"
}
```
{% endtab %}
{% endtabs %}

## Get Transactions

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/octane/transactions`

Returns an array of all the orders for an associated `apiKey`.

#### Headers

| Name                                     | Type   | Description         |
| ---------------------------------------- | ------ | ------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key |

{% tabs %}
{% tab title="200: OK Success" %}
```json
[
    {
        "id": "txn-123456791",
        "type": "OFF_RAMP",
        "createdAt": "2024-01-30T16:31:06.407",
        "flaggedAt": null,
        "completedAt": null,
        "updatedAt": "2024-01-30T16:31:06.401",
        "sellOrder": {
            "id": "ord-123456790",
            "bankAccountId": null,
            "blockchain": "ethereum",
            "createdAt": "2024-01-30T16:31:06.407",
            "currency": "ETH",
            "feeUsd": null,
            "priceUsd": null,
            "quantity": "54.555544",
            "updatedAt": "2024-01-30T16:31:06.4",
            "walletId": "wal-123456790"
        },
        "buyOrder": {
            "id": "ord-123456791",
            "bankAccountId": "bac-123456788",
            "blockchain": null,
            "createdAt": "2024-01-30T16:31:06.407",
            "currency": "USD",
            "feeUsd": null,
            "priceUsd": null,
            "quantity": null,
            "updatedAt": "2024-01-30T16:31:06.4",
            "walletId": null
        }
    },
    {
        "id": "txn-123456790",
        "type": "OFF_RAMP",
        "createdAt": "2024-01-30T16:31:21.479",
        "flaggedAt": null,
        "completedAt": null,
        "updatedAt": "2024-01-30T16:31:21.475",
        "sellOrder": {
            "id": "ord-123456784",
            "bankAccountId": null,
            "blockchain": "avalanche",
            "createdAt": "2024-01-30T16:31:21.479",
            "currency": "AVAX",
            "feeUsd": null,
            "priceUsd": null,
            "quantity": "54.555544",
            "updatedAt": "2024-01-30T16:31:21.475",
            "walletId": "wal-123456790"
        },
        "buyOrder": {
            "id": "ord-123456785",
            "bankAccountId": "bac-123456788",
            "blockchain": null,
            "createdAt": "2024-01-30T16:31:21.479",
            "currency": "USD",
            "feeUsd": null,
            "priceUsd": null,
            "quantity": null,
            "updatedAt": "2024-01-30T16:31:21.475",
            "walletId": null
        }
    }
]
```
{% endtab %}

{% tab title="401: Unauthorized Unauthorized -- Invalid API Key" %}
```json
{
    "Unauthorized": "Invaild API Key"
}
```
{% endtab %}
{% endtabs %}

## Get Transaction by ID

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/octane/transactions/{transactionId}`

Returns an object for the `transactionId`for an associated `apiKey`.

#### Query Parameters

| Name                                            | Type   | Description    |
| ----------------------------------------------- | ------ | -------------- |
| transactionId<mark style="color:red;">\*</mark> | string | Transaction ID |

#### Headers

| Name                                     | Type   | Description         |
| ---------------------------------------- | ------ | ------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key |

{% tabs %}
{% tab title="200: OK Success" %}
```json
{
    "id": "txn-123456815",
    "type": "OFF_RAMP",
    "createdAt": "2024-02-02T01:40:48.492",
    "flaggedAt": null,
    "completedAt": null,
    "updatedAt": "2024-02-02T01:40:48.487",
    "sellOrder": {
        "id": "ord-123456870",
        "bankAccountId": null,
        "blockchain": "avalanche",
        "createdAt": "2024-02-02T01:40:48.492",
        "currency": "AVAX",
        "feeUsd": null,
        "priceUsd": "6.85",
        "quantity": ".2004",
        "updatedAt": "2024-02-02T01:40:48.486",
        "walletId": "wal-123456790"
    },
    "buyOrder": {
        "id": "ord-123456871",
        "bankAccountId": "bac-123456788",
        "blockchain": null,
        "createdAt": "2024-02-02T01:40:48.492",
        "currency": "USD",
        "feeUsd": "0.17",
        "priceUsd": "6.85",
        "quantity": "6.67",
        "updatedAt": "2024-02-02T01:40:48.486",
        "walletId": "0x065149eab6eFa05F4639Da6305B58C91BD92d456"
    }
}
```
{% endtab %}

{% tab title="401: Unauthorized Unauthorized -- Invalid API Key" %}
```json
{
    "Unauthorized": "Invaild API Key"
}
```
{% endtab %}
{% endtabs %}

## **Copy & Paste Code**

**POST Transactions**

{% tabs %}
{% tab title="Curl" %}
```bash
curl -X POST https://api.abyiss.com/v2/octane/transactions?apiKey=YOUR_API_KEY_HERE \
-H "Content-Type: application/json" \
-d '{
  "transaction": {
    "sellOrder": {
        "walletId": "wal-123456790",
        "blockchain": "avalanche",
        "currency": "AVAX",
        "quantity": ".2004"
    },
    "buyOrder": {
        "bankAccountId": "bac-123456788",
        "currency": "USD"
    }
  }
}'
```
{% endtab %}

{% tab title="Python" %}
```python
import requests
import json

url = "https://api.abyiss.com/v2/octane/transactions?apiKey=YOUR_API_KEY_HERE"

headers = {
    'Content-Type': 'application/json'
}

# Replace the below dictionary with your order details
payload = {
  "transaction": {
    "sellOrder": {
        "walletId": "wal-123456790",
        "blockchain": "avalanche",
        "currency": "AVAX",
        "quantity": ".2004"
    },
    "buyOrder": {
        "bankAccountId": "bac-123456788",
        "currency": "USD"
    }
  }
}

response = requests.post(url, headers=headers, data=json.dumps(payload))

print(response.status_code)  # This will print the status code of the response
print(response.json())  # This will print the response content as JSON
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
const url = 'https://api.abyiss.com/v2/octane/transactions?apiKey=YOUR_API_KEY_HERE';

const payload = {
  "transaction": {
    "sellOrder": {
        "walletId": "wal-123456790",
        "blockchain": "avalanche",
        "currency": "AVAX",
        "quantity": ".2004"
    },
    "buyOrder": {
        "bankAccountId": "bac-123456788",
        "currency": "USD"
    }
  }
};

fetch(url, {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify(payload)
})
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

**GET Transactions**

{% tabs %}
{% tab title="Curl" %}
```bash
curl "https://api.abyiss.com/v2/octane/transactions?apiKey=YOUR_API_KEY_HERE"
```
{% endtab %}

{% tab title="Python" %}
```python
import requests

url = 'https://api.abyiss.com/v2/octane/transactions?apiKey=YOUR_API_KEY_HERE'

response = requests.get(url)

print(response.status_code)  # This will print the status code of the response
print(response.json())  # This will print the response content as JSON
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
const url = 'https://api.abyiss.com/v2/octane/transactions?apiKey=YOUR_API_KEY_HERE';

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

## **Transactions Response Object**

{% tabs %}
{% tab title="POST Transactions" %}
Example URL: [https://api.abyiss.com/v2/octane/transactions?apiKey=](https://api.abyiss.com/v2/octane/transactions?apiKey=)

```json
{
    "id": "txn-123456815",
    "type": "OFF_RAMP",
    "createdAt": "2024-02-02T01:40:48.492",
    "flaggedAt": null,
    "completedAt": null,
    "updatedAt": "2024-02-02T01:40:48.487",
    "sellOrder": {
        "id": "ord-123456870",
        "bankAccountId": null,
        "blockchain": "avalanche",
        "createdAt": "2024-02-02T01:40:48.492",
        "currency": "AVAX",
        "feeUsd": null,
        "priceUsd": "6.85",
        "quantity": ".2004",
        "updatedAt": "2024-02-02T01:40:48.486",
        "walletId": "wal-123456790"
    },
    "buyOrder": {
        "id": "ord-123456871",
        "bankAccountId": "bac-123456788",
        "blockchain": null,
        "createdAt": "2024-02-02T01:40:48.492",
        "currency": "USD",
        "feeUsd": "0.17",
        "priceUsd": "6.85",
        "quantity": "6.67",
        "updatedAt": "2024-02-02T01:40:48.486",
        "walletId": "0x065149eab6eFa05F4639Da6305B58C91BD92d456"
    }
}
```
{% endtab %}

{% tab title="Get Transactions" %}
Example URL: [https://api.abyiss.com/v2/octane/transactions?apiKey=](https://api.abyiss.com/v2/octane/transactions?apiKey=)

```json
[
    {
        "id": "txn-123456791",
        "type": "OFF_RAMP",
        "createdAt": "2024-01-30T16:31:06.407",
        "flaggedAt": null,
        "completedAt": null,
        "updatedAt": "2024-01-30T16:31:06.401",
        "sellOrder": {
            "id": "ord-123456790",
            "bankAccountId": null,
            "blockchain": "ethereum",
            "createdAt": "2024-01-30T16:31:06.407",
            "currency": "ETH",
            "feeUsd": null,
            "priceUsd": null,
            "quantity": "54.555544",
            "updatedAt": "2024-01-30T16:31:06.4",
            "walletId": "wal-123456790"
        },
        "buyOrder": {
            "id": "ord-123456791",
            "bankAccountId": "bac-123456788",
            "blockchain": null,
            "createdAt": "2024-01-30T16:31:06.407",
            "currency": "USD",
            "feeUsd": null,
            "priceUsd": null,
            "quantity": null,
            "updatedAt": "2024-01-30T16:31:06.4",
            "walletId": null
        }
    },
    {
        "id": "txn-123456790",
        "type": "OFF_RAMP",
        "createdAt": "2024-01-30T16:31:21.479",
        "flaggedAt": null,
        "completedAt": null,
        "updatedAt": "2024-01-30T16:31:21.475",
        "sellOrder": {
            "id": "ord-123456784",
            "bankAccountId": null,
            "blockchain": "avalanche",
            "createdAt": "2024-01-30T16:31:21.479",
            "currency": "AVAX",
            "feeUsd": null,
            "priceUsd": null,
            "quantity": "54.555544",
            "updatedAt": "2024-01-30T16:31:21.475",
            "walletId": "wal-123456790"
        },
        "buyOrder": {
            "id": "ord-123456785",
            "bankAccountId": "bac-123456788",
            "blockchain": null,
            "createdAt": "2024-01-30T16:31:21.479",
            "currency": "USD",
            "feeUsd": null,
            "priceUsd": null,
            "quantity": null,
            "updatedAt": "2024-01-30T16:31:21.475",
            "walletId": null
        }
    }
]
```
{% endtab %}

{% tab title="Get Transaction by Id" %}
Example URL: [https://api.abyiss.com/v2/octane/transactions/txn-123456815?apiKey=](https://api.abyiss.com/v2/octane/transactions/txn-123456815?apiKey=)

```json
{
    "id": "txn-123456815",
    "type": "OFF_RAMP",
    "createdAt": "2024-02-02T01:40:48.492",
    "flaggedAt": null,
    "completedAt": null,
    "updatedAt": "2024-02-02T01:40:48.487",
    "sellOrder": {
        "id": "ord-123456870",
        "bankAccountId": null,
        "blockchain": "avalanche",
        "createdAt": "2024-02-02T01:40:48.492",
        "currency": "AVAX",
        "feeUsd": null,
        "priceUsd": "6.85",
        "quantity": ".2004",
        "updatedAt": "2024-02-02T01:40:48.486",
        "walletId": "wal-123456790"
    },
    "buyOrder": {
        "id": "ord-123456871",
        "bankAccountId": "bac-123456788",
        "blockchain": null,
        "createdAt": "2024-02-02T01:40:48.492",
        "currency": "USD",
        "feeUsd": "0.17",
        "priceUsd": "6.85",
        "quantity": "6.67",
        "updatedAt": "2024-02-02T01:40:48.486",
        "walletId": "0x065149eab6eFa05F4639Da6305B58C91BD92d456"
    }
}
```
{% endtab %}
{% endtabs %}

## Transactions Response Attributes

| Attribute Name | Data Type | Description                                                            |
| -------------- | --------- | ---------------------------------------------------------------------- |
| id             | string    | Unique identifier for the transaction.                                 |
| type           | string    | Type of transaction (OFF\_RAMP, ON\_RAMP).                             |
| createdAt      | string    | Timestamp indicating when the transaction was created.                 |
| flaggedAt      | string    | Timestamp indicating when the transaction was flagged (if applicable). |
| completedAt    | string    | Timestamp indicating when the transaction was completed.               |
| updatedAt      | string    | Timestamp indicating when the transaction was last updated             |
| sellOrder      | object    | Information about the sell order.                                      |
| buyOrder       | object    | Information about the buy order.                                       |
| id             | string    | Unique identifier for the order.                                       |
| bankAccountId  | string    | ID of the bank account associated with the order.                      |
| blockchain     | string    | Blockchain used for the order.                                         |
| createdAt      | string    | Timestamp indicating when the order was created.                       |
| currency       | string    | Currency to be sold or bought.                                         |
| feeUsd         | string    | Fee in USD for the order.                                              |
| priceUsd       | string    | Price in USD for the order.                                            |
| quantity       | string    | Quantity of the currency to be bought or sold.                         |
| updatedAt      | string    | Timestamp indicating when the order was last updated.                  |
| walletId       | string    | ID of the wallet associated with the order.                            |

