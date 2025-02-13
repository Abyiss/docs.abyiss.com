---
description: The Bank Accounts API
---

# Bank Accounts

{% hint style="warning" %}
**The Endpoint is in Beta**
{% endhint %}

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

| Name                                             | Type   | Description                                                                          |
| ------------------------------------------------ | ------ | ------------------------------------------------------------------------------------ |
| routingNumber<mark style="color:red;">\*</mark>  | string | The bank account routing number.                                                     |
| accountNumber<mark style="color:red;">\*</mark>  | string | The bank account number.                                                             |
| wireNumber<mark style="color:red;">\*</mark>     | string | The bank account wire number.                                                        |
| bankName                                         | string | The bank name.                                                                       |
| ibanNumber                                       | string | International Bank Account Number (IBAN)                                             |
| type                                             | string | Bank Account Type ("BUSINESS\_CHECKING", "BUSINESS\_SAVINGS", "SAVINGS", "CHECKING") |
| fiatCurrency                                     | string | Bank Account Fiat Currency Type. Default USD.                                        |
| swiftCode                                        | string | International Bank Account Swift Code.                                               |
| nationalId                                       | string | International Bank Account National Id.                                              |
| bankAddress                                      | object | Customers bank details.                                                              |
| city                                             | string | City where the bank is located.                                                      |
| country                                          | string | Country where the bank is located.                                                   |
| line1                                            | string | Address line 1 of the bank.                                                          |
| line2                                            | string | Address line 2 of the bank.                                                          |
| province                                         | string | Province or state where the bank is located.                                         |
| billingDetails<mark style="color:red;">\*</mark> | object | Customers billing details.                                                           |
| city<mark style="color:red;">\*</mark>           | string | City in the billing address.                                                         |
| country<mark style="color:red;">\*</mark>        | string | Country in the billing address.                                                      |
| line1<mark style="color:red;">\*</mark>          | string | Address line 1 in the billing address.                                               |
| line2                                            | string | Address line 2 in the billing address.                                               |
| province<mark style="color:red;">\*</mark>       | string | Province or state in the billing address.                                            |
| fullName<mark style="color:red;">\*</mark>       | string | Full name of the billing contact.                                                    |
| phone<mark style="color:red;">\*</mark>          | string | Phone number of the billing contact.                                                 |
| postalCode<mark style="color:red;">\*</mark>     | string | Postal code in the billing address.                                                  |

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
    "isActive": true,
    "isVerifiedForWires": false,
    "wireNumber": null,
    "ibanNumber": null,
    "type": "BUSINESS_CHECKING",
    "fiatCurrency": "USD",
    "swiftCode": null,
    "nationalId": null,
    "bankAddress": {
        "city": null,
        "country": "UNITED_STATES",
        "line1": null,
        "line2": null,
        "province": null,
        "createdAt": "2024-07-23T14:04:28.788",
        "updatedAt": "2024-07-23T14:04:28.781"
    },
    "billingDetails": {
        "city": null,
        "country": "UNITED_STATES",
        "line1": null,
        "line2": null,
        "province": null,
        "createdAt": "2024-07-23T14:04:28.788",
        "updatedAt": "2024-07-23T14:04:28.781",
        "fullName": null,
        "phone": null,
        "postalCode": null
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
[
    {
        "id": "bac-123456788",
        "routingNumber": "12345",
        "accountNumber": "67890",
        "bankName": "Bank of America",
        "createdAt": "2024-07-23T14:04:28.788",
        "updatedAt": "2024-07-23T14:04:28.781",
        "userId": "usr-123456788",
        "isActive": true,
        "isVerifiedForWires": false,
        "wireNumber": null,
        "ibanNumber": null,
        "type": "BUSINESS_CHECKING",
        "fiatCurrency": "USD",
        "swiftCode": null,
        "nationalId": null,
        "bankAddress": {
            "city": null,
            "country": "UNITED_STATES",
            "line1": null,
            "line2": null,
            "province": null,
            "createdAt": "2024-07-23T14:04:28.788",
            "updatedAt": "2024-07-23T14:04:28.781"
        },
        "billingDetails": {
            "city": null,
            "country": "UNITED_STATES",
            "line1": null,
            "line2": null,
            "province": null,
            "createdAt": "2024-07-23T14:04:28.788",
            "updatedAt": "2024-07-23T14:04:28.781",
            "fullName": null,
            "phone": null,
            "postalCode": null
        }
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
    "isActive": true,
    "isVerifiedForWires": false,
    "wireNumber": null,
    "ibanNumber": null,
    "type": "BUSINESS_CHECKING",
    "fiatCurrency": "USD",
    "swiftCode": null,
    "nationalId": null,
    "bankAddress": {
        "city": null,
        "country": "UNITED_STATES",
        "line1": null,
        "line2": null,
        "province": null,
        "createdAt": "2024-07-23T14:04:28.788",
        "updatedAt": "2024-07-23T14:04:28.781"
    },
    "billingDetails": {
        "city": null,
        "country": "UNITED_STATES",
        "line1": null,
        "line2": null,
        "province": null,
        "createdAt": "2024-07-23T14:04:28.788",
        "updatedAt": "2024-07-23T14:04:28.781",
        "fullName": null,
        "phone": null,
        "postalCode": null
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
    "wireNumber": "44335534",
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
    "wireNumber": "44335534",
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
    wireNumber: '44335534',
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
    "isActive": true,
    "isVerifiedForWires": false,
    "wireNumber": null,
    "ibanNumber": null,
    "type": "BUSINESS_CHECKING",
    "fiatCurrency": "USD",
    "swiftCode": null,
    "nationalId": null,
    "bankAddress": {
        "city": null,
        "country": "UNITED_STATES",
        "line1": null,
        "line2": null,
        "province": null,
        "createdAt": "2024-07-23T14:04:28.788",
        "updatedAt": "2024-07-23T14:04:28.781"
    },
    "billingDetails": {
        "city": null,
        "country": "UNITED_STATES",
        "line1": null,
        "line2": null,
        "province": null,
        "createdAt": "2024-07-23T14:04:28.788",
        "updatedAt": "2024-07-23T14:04:28.781",
        "fullName": null,
        "phone": null,
        "postalCode": null
    }
}
```
{% endtab %}

{% tab title="Get Bank Accounts" %}
Example URL: [https://api.abyiss.com/v2/octane/paymentMethods/bankAccounts?apiKey=](https://api.abyiss.com/v2/octane/paymentMethods/bankAccounts?apiKey=)

```json
[
    {
        "id": "bac-123456788",
        "routingNumber": "12345",
        "accountNumber": "67890",
        "bankName": "Bank of America",
        "createdAt": "2024-07-23T14:04:28.788",
        "updatedAt": "2024-07-23T14:04:28.781",
        "userId": "usr-123456788",
        "isActive": true,
        "isVerifiedForWires": false,
        "wireNumber": null,
        "ibanNumber": null,
        "type": "BUSINESS_CHECKING",
        "fiatCurrency": "USD",
        "swiftCode": null,
        "nationalId": null,
        "bankAddress": {
            "city": null,
            "country": "UNITED_STATES",
            "line1": null,
            "line2": null,
            "province": null,
            "createdAt": "2024-07-23T14:04:28.788",
            "updatedAt": "2024-07-23T14:04:28.781"
        },
        "billingDetails": {
            "city": null,
            "country": "UNITED_STATES",
            "line1": null,
            "line2": null,
            "province": null,
            "createdAt": "2024-07-23T14:04:28.788",
            "updatedAt": "2024-07-23T14:04:28.781",
            "fullName": null,
            "phone": null,
            "postalCode": null
        }
    }, {
        "id": "bac-12345678810",
        "routingNumber": "1234510",
        "accountNumber": "6789010",
        "bankName": "Bank of America",
        "createdAt": "2024-07-23T14:04:28.788",
        "updatedAt": "2024-07-23T14:04:28.781",
        "userId": "usr-123456788",
        "isActive": true,
        "isVerifiedForWires": false,
        "wireNumber": null,
        "ibanNumber": null,
        "type": "BUSINESS_CHECKING",
        "fiatCurrency": "USD",
        "swiftCode": null,
        "nationalId": null,
        "bankAddress": {
            "city": null,
            "country": "UNITED_STATES",
            "line1": null,
            "line2": null,
            "province": null,
            "createdAt": "2024-07-23T14:04:28.788",
            "updatedAt": "2024-07-23T14:04:28.781"
        },
        "billingDetails": {
            "city": null,
            "country": "UNITED_STATES",
            "line1": null,
            "line2": null,
            "province": null,
            "createdAt": "2024-07-23T14:04:28.788",
            "updatedAt": "2024-07-23T14:04:28.781",
            "fullName": null,
            "phone": null,
            "postalCode": null
        }
    }
]
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
    "isActive": true,
    "isVerifiedForWires": false,
    "wireNumber": null,
    "ibanNumber": null,
    "type": "BUSINESS_CHECKING",
    "fiatCurrency": "USD",
    "swiftCode": null,
    "nationalId": null,
    "bankAddress": {
        "city": null,
        "country": "UNITED_STATES",
        "line1": null,
        "line2": null,
        "province": null,
        "createdAt": "2024-07-23T14:04:28.788",
        "updatedAt": "2024-07-23T14:04:28.781"
    },
    "billingDetails": {
        "city": null,
        "country": "UNITED_STATES",
        "line1": null,
        "line2": null,
        "province": null,
        "createdAt": "2024-07-23T14:04:28.788",
        "updatedAt": "2024-07-23T14:04:28.781",
        "fullName": null,
        "phone": null,
        "postalCode": null
    }
}
```
{% endtab %}
{% endtabs %}

## Bank Accounts Response Attributes

| Attribute Name     | Type    | Description                                                                          |
| ------------------ | ------- | ------------------------------------------------------------------------------------ |
| id                 | string  | Unique bank account id.                                                              |
| routingNumber      | string  | The bank account routing number.                                                     |
| accountNumber      | string  | The bank account number.                                                             |
| wireNumber         | string  | The bank account wire number.                                                        |
| bankName           | string  | The bank name.                                                                       |
| createdAt          | string  | The timestamp the bank account was created at.                                       |
| updatedAt          | string  | The timestamp the bank account was updated at.                                       |
| userId             | string  | Unique user id.                                                                      |
| isActive           | boolean | If the bank account is currently active. True or False.                              |
| isVerifiedForWires | boolean |                                                                                      |
| ibanNumber         | string  | International Bank Account Number (IBAN)                                             |
| type               | string  | Bank Account Type ("BUSINESS\_CHECKING", "BUSINESS\_SAVINGS", "SAVINGS", "CHECKING") |
| fiatCurrency       | string  | Bank Account Fiat Currency Type. Default USD.                                        |
| swiftCode          | string  | International Bank Account Swift Code.                                               |
| nationalId         | string  | International Bank Account National Id.                                              |
| bankAddress        | object  | Customers bank detials.                                                              |
| city               | string  | City where the bank is located.                                                      |
| country            | string  | Country where the bank is located.                                                   |
| line1              | string  | Address line 1 of the bank.                                                          |
| line2              | string  | Address line 2 of the bank.                                                          |
| province           | string  | Province or state where the bank is located.                                         |
| billingDetails     | object  | Customers billing details.                                                           |
| city               | string  | City in the billing address.                                                         |
| country            | string  | Country in the billing address.                                                      |
| line1              | string  | Address line 1 in the billing address.                                               |
| line2              | string  | Address line 2 in the billing address.                                               |
| province           | string  | Province or state in the billing address.                                            |
| fullName           | string  | Full name of the billing contact.                                                    |
| phone              | string  | Phone number of the billing contact.                                                 |
| postalCode         | string  | Postal code in the billing address.                                                  |

