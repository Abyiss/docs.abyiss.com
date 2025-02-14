---
description: The Bank Accounts API
---

# Bank Accounts

## Introduction

The Octane Bank Accounts API provides developers with functionality to manage and retrieve information related to bank accounts with their accounts.&#x20;

* **Bank Accounts:**
  * Retrieve a comprehensive list of bank accounts associated with a given API key.
  * Access specific bank account details by querying with the bank account ID.
  * Create new bank accounts by providing essential details in the request body.
  * Deletes a specific bank account by providing the bank account ID.

## Bank Account API Endpoints

### Post US Bank Account

<mark style="color:green;">`POST`</mark> `https://api.abyiss.com/v2/octane/paymentMethods/bankAccounts`

Create a new US bank account by providing the necessary account details. Upon a successful request, it returns a 201 status code along with the details of the created bank account.

**Headers**

| Name                                     | Type   | Description         |
| ---------------------------------------- | ------ | ------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key |

**Request Body**

| Name                                             | Type   | Description                       |
| ------------------------------------------------ | ------ | ----------------------------------|
| routingNumber<mark style="color:red;">\*</mark>  | string | The bank account routing number.  |
| accountNumber<mark style="color:red;">\*</mark>  | string | The bank account number. |
| billingDetails<mark style="color:red;">\*</mark> | object | Customer's billing details. |
| billingDetails.city<mark style="color:red;">\*</mark>           | string | City in the billing address. |
| billingDetails.country<mark style="color:red;">\*</mark>        | string | Country in the billing address. |
| billingDetails.line1<mark style="color:red;">\*</mark>          | string | Address line 1 in the billing address. |
| billingDetails.line2                                            | string | Address line 2 in the billing address. |
| billingDetails.province<mark style="color:red;">\*</mark>       | string | Province or state in the billing address. |
| billingDetails.fullName<mark style="color:red;">\*</mark>       | string | Full name of the billing contact. |
| billingDetails.phone<mark style="color:red;">\*</mark>          | string | Phone number of the billing contact. |
| billingDetails.postalCode<mark style="color:red;">\*</mark>     | string | Postal code in the billing address. |

{% tabs %}
{% tab title="201: Created -- Success" %}
```json
{
  "id": "bac-123456788",
  "routingNumber": "12345",
  "accountNumber": "67890",
  "bankName": "Bank of America",
  "createdAt": "2024-07-23T14:04:28.788",
  "updatedAt": "2024-07-23T14:04:28.781",
  "userId": "usr-123456788",
  "fiatCurrency": "USD",
  "bankAddress": {
    "city": "ORLANDO",
    "country": "UNITED_STATES",
    "line1": "1123 PROMANADE ST",
    "line2": null,
    "province": "FL",
    "createdAt": "2024-07-23T14:04:28.788",
    "updatedAt": "2024-07-23T14:04:28.781"
  },
  "billingDetails": {
    "city": "BOSTON",
    "country": "UNITED_STATES",
    "line1": "342 MAIN ST",
    "line2": "SUITE 100",
    "province": "MA",
    "createdAt": "2024-07-23T14:04:28.788",
    "updatedAt": "2024-07-23T14:04:28.781",
    "fullName": "GAVIN BELSON",
    "phone": "1112223333",
    "postalCode": "02142"
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

### Get Bank Accounts

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/octane/paymentMethods/bankAccounts`

Retrieves all bank accounts associated with the provided API key. Upon a successful request, it returns a 200 status code and a list of bank accounts.

**Headers**

| Name                                     | Type   | Description         |
| ---------------------------------------- | ------ | ------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key |

{% tabs %}
{% tab title="200: OK -- Success" %}
```json
[{
  "id": "bac-123456788",
  "routingNumber": "12345",
  "accountNumber": "67890",
  "bankName": "Bank of America",
  "createdAt": "2024-07-23T14:04:28.788",
  "updatedAt": "2024-07-23T14:04:28.781",
  "userId": "usr-123456788",
  "fiatCurrency": "USD",
  "bankAddress": {
    "city": "ORLANDO",
    "country": "UNITED_STATES",
    "line1": "1123 PROMANADE ST",
    "line2": null,
    "province": "FL",
    "createdAt": "2024-07-23T14:04:28.788",
    "updatedAt": "2024-07-23T14:04:28.781"
  },
  "billingDetails": {
    "city": "BOSTON",
    "country": "UNITED_STATES",
    "line1": "342 MAIN ST",
    "line2": "SUITE 100",
    "province": "MA",
    "createdAt": "2024-07-23T14:04:28.788",
    "updatedAt": "2024-07-23T14:04:28.781",
    "fullName": "GAVIN BELSON",
    "phone": "1112223333",
    "postalCode": "02142"
  }
}]
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

### Get Bank Account by ID

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/octane/paymentMethods/bankAccounts/{bankAccountId}`

Retrieves the details of a specific bank account using its unique bank account ID. Upon a successful request, it returns a 200 status code and the details of the requested bank account.

**Headers**

| Name                                     | Type   | Description         |
| ---------------------------------------- | ------ | ------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key |

**Query Parameters**

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| bankAccountId<mark style="color:red;">\*</mark> | string | Bank Account Id |

{% tabs %}
{% tab title="200: OK -- Success" %}
```json
{
  "id": "bac-123456788",
  "routingNumber": "12345",
  "accountNumber": "67890",
  "bankName": "Bank of America",
  "createdAt": "2024-07-23T14:04:28.788",
  "updatedAt": "2024-07-23T14:04:28.781",
  "userId": "usr-123456788",
  "fiatCurrency": "USD",
  "bankAddress": {
    "city": "ORLANDO",
    "country": "UNITED_STATES",
    "line1": "1123 PROMANADE ST",
    "line2": null,
    "province": "FL",
    "createdAt": "2024-07-23T14:04:28.788",
    "updatedAt": "2024-07-23T14:04:28.781"
  },
  "billingDetails": {
    "city": "BOSTON",
    "country": "UNITED_STATES",
    "line1": "342 MAIN ST",
    "line2": "SUITE 100",
    "province": "MA",
    "createdAt": "2024-07-23T14:04:28.788",
    "updatedAt": "2024-07-23T14:04:28.781",
    "fullName": "GAVIN BELSON",
    "phone": "1112223333",
    "postalCode": "02142"
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

### Delete Bank Account

<mark style="color:red;">`DELETE`</mark>` ``https://api.abyiss.com/v2/octane/paymentMethods/bankAccounts/{bankAccountId}`

Deletes a specified bank account using its unique bank account ID. Upon a successful request, it returns a 204 status code indicating that the wallet has been deleted.

**Headers**

| Name                                     | Type   | Description         |
| ---------------------------------------- | ------ | ------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key |

**Query Parameters**

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| bankAccountId<mark style="color:red;">\*</mark> | string | Bank Account Id |

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

### **POST Bank Accounts**

{% tabs %}
{% tab title="Curl" %}
```bash
curl -X POST \
  -H "Content-Type: application/json" \
  -H "apiKey: your-api-key" \
  -d '{
    "routingNumber": "12555342345",
    "accountNumber": "67555234890",
    "billingDetails": {
      "city": "Boston",
      "country": "USA",
      "line1": "123 Bill Me Dr",
      "province": "MA",
      "fullName": "Frank Tester",
      "phone": "123345456",
      "postalCode": "123543"
    }
  }' \
  https://api.abyiss.com/v2/octane/paymentMethods/bankAccounts

```
{% endtab %}

{% tab title="Python" %}
```python
import requests
import json

url = "https://api.abyiss.com/v2/octane/paymentMethods/bankAccounts"
headers = {
  "Content-Type": "application/json",
  "apiKey": "your-api-key"
}

bank_account_data = {
  "routingNumber": "12555342345",
  "accountNumber": "67555234890",
  "billingDetails": {
    "city": "Boston",
    "country": "USA",
    "line1": "123 Bill Me Dr",
    "province": "MA",
    "fullName": "Frank Tester",
    "phone": "123345456",
    "postalCode": "123543"
  }
}

response = requests.post(url, headers=headers, data=json.dumps(bank_account_data))

print(response.status_code)
print(response.json())
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
const axios = require('axios');

const url = 'https://api.abyiss.com/v2/octane/paymentMethods/bankAccounts';
const headers = {
  'Content-Type': 'application/json',
  'apiKey': 'your-api-key'
};

const bankAccountData = {
  routingNumber: '12555342345',
  accountNumber: '67555234890',
  billingDetails: {
    city: 'Boston',
    country: 'USA',
    line1: '123 Bill Me Dr',
    province: 'MA',
    fullName: 'Frank Tester',
    phone: '123345456',
    postalCode: '123543'
  }
};

axios.post(url, bankAccountData, { headers })
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

### **GET Bank Accounts**

{% tabs %}
{% tab title="Curl" %}
```bash
curl "https://api.abyiss.com/v2/octane/paymentMethods/bankAccounts?apiKey=YOUR_API_KEY_HERE"
```
{% endtab %}

{% tab title="Python" %}
```python
import requests

url = 'httpshttps://api.abyiss.com/v2/octane/paymentMethods/bankAccounts?apiKey=YOUR_API_KEY_HERE'

response = requests.get(url)

print(response.status_code)  # This will print the status code of the response
print(response.json())  # This will print the response content as JSON
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
const url = 'https://api.abyiss.com/v2/octane/paymentMethods/bankAccounts?apiKey=YOUR_API_KEY_HERE';

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

## **Bank Accounts Response Object**

{% tabs %}
{% tab title="POST Bank Accounts" %}
Example URL: [https://api.abyiss.com/v2/octane/paymentMethods/bankAccounts?apiKey=](https://api.abyiss.com/v2/octane/paymentMethods/bankAccounts?apiKey=)

```json
{
  "id": "bac-123456788",
  "routingNumber": "12345",
  "accountNumber": "67890",
  "bankName": "Bank of America",
  "createdAt": "2024-07-23T14:04:28.788",
  "updatedAt": "2024-07-23T14:04:28.781",
  "userId": "usr-123456788",
  "fiatCurrency": "USD",
  "bankAddress": {
    "city": "ORLANDO",
    "country": "UNITED_STATES",
    "line1": "1123 PROMANADE ST",
    "line2": null,
    "province": "FL",
    "createdAt": "2024-07-23T14:04:28.788",
    "updatedAt": "2024-07-23T14:04:28.781"
  },
  "billingDetails": {
    "city": "BOSTON",
    "country": "UNITED_STATES",
    "line1": "342 MAIN ST",
    "line2": "SUITE 100",
    "province": "MA",
    "createdAt": "2024-07-23T14:04:28.788",
    "updatedAt": "2024-07-23T14:04:28.781",
    "fullName": "GAVIN BELSON",
    "phone": "1112223333",
    "postalCode": "02142"
  }
}
```
{% endtab %}

{% tab title="Get Bank Accounts" %}
Example URL: [https://api.abyiss.com/v2/octane/paymentMethods/bankAccounts?apiKey=](https://api.abyiss.com/v2/octane/paymentMethods/bankAccounts?apiKey=)

```json
[{
  "id": "bac-123456788",
  "routingNumber": "12345",
  "accountNumber": "67890",
  "bankName": "Bank of America",
  "createdAt": "2024-07-23T14:04:28.788",
  "updatedAt": "2024-07-23T14:04:28.781",
  "userId": "usr-123456788",
  "fiatCurrency": "USD",
  "bankAddress": {
    "city": "ORLANDO",
    "country": "UNITED_STATES",
    "line1": "1123 PROMANADE ST",
    "line2": null,
    "province": "FL",
    "createdAt": "2024-07-23T14:04:28.788",
    "updatedAt": "2024-07-23T14:04:28.781"
  },
  "billingDetails": {
    "city": "BOSTON",
    "country": "UNITED_STATES",
    "line1": "342 MAIN ST",
    "line2": "SUITE 100",
    "province": "MA",
    "createdAt": "2024-07-23T14:04:28.788",
    "updatedAt": "2024-07-23T14:04:28.781",
    "fullName": "GAVIN BELSON",
    "phone": "1112223333",
    "postalCode": "02142"
  }
}]
```
{% endtab %}

{% tab title="Get Bank Account by Id" %}
Example URL: [https://api.abyiss.com/v2/octane/paymentMethods/bankAccounts/bac-123456788?apiKey=](https://api.abyiss.com/v2/octane/paymentMethods/bankAccounts/bac-123456788?apiKey=)

```json
{
  "id": "bac-123456788",
  "routingNumber": "12345",
  "accountNumber": "67890",
  "bankName": "Bank of America",
  "createdAt": "2024-07-23T14:04:28.788",
  "updatedAt": "2024-07-23T14:04:28.781",
  "userId": "usr-123456788",
  "fiatCurrency": "USD",
  "bankAddress": {
    "city": "ORLANDO",
    "country": "UNITED_STATES",
    "line1": "1123 PROMANADE ST",
    "line2": null,
    "province": "FL",
    "createdAt": "2024-07-23T14:04:28.788",
    "updatedAt": "2024-07-23T14:04:28.781"
  },
  "billingDetails": {
    "city": "BOSTON",
    "country": "UNITED_STATES",
    "line1": "342 MAIN ST",
    "line2": "SUITE 100",
    "province": "MA",
    "createdAt": "2024-07-23T14:04:28.788",
    "updatedAt": "2024-07-23T14:04:28.781",
    "fullName": "GAVIN BELSON",
    "phone": "1112223333",
    "postalCode": "02142"
  }
}
```
{% endtab %}
{% endtabs %}

## Bank Accounts Response Attributes

| Attribute Name     | Type    | Description             |
| ------------------ | ------- | ------------------------|
| id                 | string  | Unique bank account id. |
| routingNumber      | string  | The bank account routing number. |
| accountNumber      | string  | The bank account number. |
| bankName           | string  | The bank name. |
| createdAt          | string  | The timestamp the bank account was created at. |
| updatedAt          | string  | The timestamp the bank account was updated at. |
| userId             | string  | Unique user id. |
| bankAddress        | object  | Customers bank detials. |
| bankAddress.city          | string  | City where the bank is located. |
| bankAddress.country       | string  | Country where the bank is located. |
| bankAddress.line1         | string  | Address line 1 of the bank. |
| bankAddress.line2         | string  | Address line 2 of the bank. |
| bankAddress.province      | string  | Province or state where the bank is located. |
| billingDetails            | object  | Customers billing details. |
| billingDetails.city       | string  | City in the billing address. |
| billingDetails.country    | string  | Country in the billing address. |
| billingDetails.line1      | string  | Address line 1 in the billing address. |
| billingDetails.line2      | string  | Address line 2 in the billing address. |
| billingDetails.province   | string  | Province or state in the billing address. |
| billingDetails.fullName   | string  | Full name of the billing contact. |
| billingDetails.phone      | string  | Phone number of the billing contact. |
| billingDetails.postalCode | string  | Postal code in the billing address. |

