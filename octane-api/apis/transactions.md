---
description: >-
  The Transactions API within Octane empowers you to efficiently manage and
  retrieve orders associated with your account.
---

# Transactions

## Pre-Requisites

Before you can POST transactions, you need to have the following:
  1. POST your [bank account](./payment-methods/bank-accounts.md) & retrieve your bank account ID
  2. POST your [wallet](./payment-methods/wallets.md) & retrieve your wallet ID
  3. Get [KYC approved by Abyiss](https://abyiss.com/home/onboarding). Please note - if you get redirected to the home page, you are already KYC approved.

## Introduction

Creating and managing transactions with the Octane Transactions API is a straightforward process:

* **Create Transaction (POST):**
  * Use the `/v2/octane/transactions` endpoint.
  * Provide essential details like blockchain type, currency pairs, quantities, and associated wallet and bank account information in the request body. More on this below.
  * Results in successful order creation with timestamp and transaction type details.
* **Retrieve All Orders (GET):**
  * Utilize the `/v2/octane/transactions` endpoint with a GET request.
  * Retrieve all orders linked to the provided apiKey.
  * Access detailed information such as IDs, blockchain specifics, currencies involved, and timestamps.
  * Upcoming filtering options allow you to refine results.
* **Retrieve Specific Order (GET):**
  * Access details of a specific order using the `/v2/octane/transactions/:id` endpoint.
  * Provide the order's ID and apiKey.
  * Retrieve comprehensive details, including transaction types, completion status, and precise currency exchange specifics.

## Transactions API Endpoints

## Post Transaction

<mark style="color:green;">`POST`</mark> `https://api.abyiss.com/v2/octane/transactions`

Returns a 201 status code upon successful query. Then returns the successful order. Requires user to have associated bank account and wallet.

### Headers

| Name                                     | Type   | Description   |
| ---------------------------------------- | ------ | ------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Blockchain ID |

### Request Body

The transaction request object is broken up into two levels. The top-level transaction request object contains the three fields in the following table. The second level contains the information inside the sourceOrder and destinationOrder objects.

| Top Level Transaction Field Name                  | Type   | Description                                                    |
| ------------------------------------------------- | ------ | -------------------------------------------------------------- |
| settlementMethod<mark style="color:red;">\*</mark>| string | How the fiat-side of the transaction will be settled.          |
| sourceOrder<mark style="color:red;">\*</mark>     | object | Information about where you are sending the currency from.     |
| destinationOrder<mark style="color:red;">\*</mark>| object | Information about where you are sending the currency to.       |

The sourceOrder and the Destination Order are identical in structure. It is worth noting that not all fields are required for each destination and source order. However, a combination of all fields are required amongst the entire transaction. Please reference [transaction customization](#transaction-customization) for more information. The fields for source and destination order request objects are outlined below.

| Order Field Name                                  | Type   | Description                                                    |
| --------------------------------------------------| ------ | -------------------------------------------------------------- |
| walletId<mark style="color:red;">\*</mark>        | string | The user's wallet ID associated with the order.                |
| blockchain<mark style="color:red;">\*</mark>      | string | Blockchain used for the order.                                 |
| currency<mark style="color:red;">\*</mark>        | string | Currency of the order.                                         |
| quantity<mark style="color:red;">\*</mark>        | string | Quantity of the currency in the order.                         |
| bankAccountId<mark style="color:red;">\*</mark>   | string | The user's bank ID which the fiat will be sent or received.    |

{% tabs %}
{% tab title="201: Created Success" %}
```json
{
  "id": "txn-123456815",
  "type": "OFF_RAMP",
  "createdAt": "2025-02-02T01:40:48.492",
  "flaggedAt": null,
  "completedAt": null,
  "updatedAt": "2025-02-02T01:40:48.487",
  "feeUsd": "0.5",
  "priceUsd": "50",
  "sourceOrder": {
    "bankAccountId": null,
    "blockchain": "ethereum",
    "currency": "USDC",
    "quantity": "50",
    "walletId": "wal-123456790"
  },
  "destinationOrder": {
    "bankAccountId": "bac-123456788",
    "blockchain": null,
    "currency": "USD",
    "quantity": "49.5",
    "walletId": null,
    "walletAddress": "0x065149eab6eFa05F4639Da6305B58C91BD92d456"
  }
}
```
{% endtab %}

{% tab title="400: Bad Request" %}
```json
{
  "errors": [{
    "message": "Invalid Request: Missing required field"
  }],
  "code": 400
}
```
{% endtab %}

{% tab title="401: Unauthorized" %}
```json
{
  "errors": [{
    "message": "Unauthorized: Invalid API Key"
  }],
  "code": 401
}
```
{% endtab %}

{% tab title="403: Forbidden" %}
```json
{
  "errors": [{
    "message": "Forbidden: Account is not KYC/KYB verified. Please contact support@abyiss.com"
  }],
  "code": 403
}
```
{% endtab %}
{% endtabs %}

### Transaction Customization

#### Selecting a Settlement Method
Abyiss supports `ACH` and `WIRE` as settlement methods. You can select the settlement method by providing one of the othe former values in the `transaction.settlementMethod` field. Please note that for on ramping, we only support `WIRE` transactions. This means that if you would like to buy crypto with a fiat currency, you must send Abyiss a wire transfer. For off ramping, we support both `ACH` and `WIRE` transactions. This means that if you would like to sell crypto for a fiat currency, you can choose to receive USD directly in your bank account via either WIRE or ACH.

##### WIRES

Wires cost $25 when OFF RAMPing.
We do not charge for WIRES when ON RAMPing, however, your bank may charge you a wire fee.

When off ramping via wire, you will receive your funds in your bank account within 1-2 business days. Often times, you will receive your funds the same day that we send them. Please note that since Abyiss is a US-based company, we only send wires during US business hours. This means that if you request a wire after 5 PM EST, it will most likely be sent the next business day.

##### ACH

ACH transactions are completely free on the Abyiss network. ACH transactions can take 2-5 business days to settle. ACH transactions are only available for off ramping. This means that if you would like to sell crypto for a fiat currency, you can choose to receive USD directly in your bank account via ACH.

#### Selecting a Blockchain

Please ensure that when selecting a blockchain, that you are using a wallet address that has been registered to that blockchain. For example, if you are using the Ethereum blockchain, you must use an Ethereum wallet address. If you are using the Avalanche blockchain, you must use an Avalanche wallet address. For wallet addresses that are usable across multiple blockchains, you must register the wallet address to each blockchain that you would like to use it with.

#### Off Ramp Transaction

Off ramp transactions are inferred from the request. If the source order contains wallet and blockchain information and the destination order contains bank account information, then the transaction is an off-ramp transaction. Off ramp transactions may be settled in your bank account via ACH or WIRE.

#### On Ramp Transaction

On ramp transactions are inferred from the request. If the source order contains bank account information and the destination order contains wallet and blockchain information, then the transaction is an on-ramp transaction. On ramp transactions are settled directly in your wallet.

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
    "id": "txn-123456804",
    "type": "ON_RAMP",
    "settlementMethod": "WIRE",
    "priceUsd": "100.00",
    "feeUsd": "2.50",
    "createdAt": "2025-02-13T23:21:05.666",
    "flaggedAt": null,
    "completedAt": null,
    "updatedAt": "2025-02-13T23:21:05.665",
    "userId": "usr-123456788",
    "sourceOrder": {
      "id": "ord-123456887",
      "bankAccountId": "bac-123456788",
      "blockchain": null,
      "createdAt": "2025-02-13T23:21:05.666",
      "currency": "USD",
      "quantity": "100.00",
      "updatedAt": "2025-02-13T23:21:05.659",
      "walletId": null
    },
    "destinationOrder": {
      "id": "ord-123456884",
      "bankAccountId": null,
      "blockchain": "ethereum",
      "createdAt": "2025-02-13T23:21:05.666",
      "currency": "ETH",
      "quantity": "0.03647559689040861",
      "updatedAt": "2025-02-13T23:21:05.659",
      "walletId": "wal-123456788"
    }
  },
  {
    "id": "txn-123456807",
    "type": "OFF_RAMP",
    "settlementMethod": "WIRE",
    "priceUsd": "100.00",
    "feeUsd": "27.50",
    "createdAt": "2025-02-13T23:21:24.592",
    "flaggedAt": null,
    "completedAt": null,
    "updatedAt": "2025-02-13T23:21:24.589",
    "userId": "usr-123456788",
    "sourceOrder": {
      "id": "ord-123456881",
      "bankAccountId": null,
      "blockchain": "ethereum",
      "createdAt": "2025-02-13T23:21:24.592",
      "currency": "ETH",
      "quantity": "0.03740792973294478",
      "updatedAt": "2025-02-13T23:21:24.589",
      "walletId": "wal-123456788"
    },
    "destinationOrder": {
      "id": "ord-123456886",
      "bankAccountId": "bac-123456788",
      "blockchain": null,
      "createdAt": "2025-02-13T23:21:24.592",
      "currency": "USD",
      "quantity": "72.5",
      "updatedAt": "2025-02-13T23:21:24.589",
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
    "walletId": null,
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
    "walletId": null,
    "walletAddress": "0x065149eab6eFa05F4639Da6305B58C91BD92d456"
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
      "wallet": null,
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
    "walletId": null
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

