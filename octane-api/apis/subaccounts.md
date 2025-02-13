---
description: >-
  The Octane Subaccounts API allows you to manage and retrieve information about
  subaccounts associated with your master account.
---

# Subaccounts

{% hint style="danger" %}
**The Endpoint is in Alpha**
{% endhint %}

Subaccounts are a way to create and manage user accounts under a master account. They can be interacted with using the master account's API key.

* **Subaccount:**
  * A subaccount is specified via the `userId` field in the request body or request query, serving as another part of the apiKey.
  * The master account can interact with subaccount payment methods and transactions.
  * The master account cannot interact with subaccounts of a subaccount.
  * Each subaccount can only have one master account.

## Subaccounts API Endpoints

## Post Subaccount

<mark style="color:green;">`POST`</mark> `https://api.abyiss.com/v2/octane/subaccounts`

Returns a 201 status code upon successful query. Then returns the successful account created.

#### Headers

| Name                                     | Type   | Description   |
| ---------------------------------------- | ------ | ------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Blockchain ID |

#### Request Body

| Name                                    | Type   | Description                              |
| --------------------------------------- | ------ | ---------------------------------------- |
| name<mark style="color:red;">\*</mark>  | string | User name including first and last name. |
| email<mark style="color:red;">\*</mark> | string | The users email address.                 |

{% tabs %}
{% tab title="201: Created Success" %}
```json
{
    "newSubAccountId": "usr-123456790"
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

## Get Subaccounts

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/octane/subaccounts`

Returns an array of all the accounts for an associated `apiKey`.

#### Headers

| Name                                     | Type   | Description         |
| ---------------------------------------- | ------ | ------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key |

{% tabs %}
{% tab title="200: OK Success" %}
```json
[{
  "id": "usr-123456790",
  "email": "test@account.com",
  "name": "subAccountName",
  "createdAt": "2023-12-10T00:46:14.786",
  "updatedAt": "2023-12-10T00:46:14.783"
},{
  "id": "usr-123457800",
  "email": "zeekdonuts@gmail.com",
  "name": "Zeek Zubert",
  "createdAt": "2023-12-10T02:18:32.022",
  "updatedAt": "2023-12-10T02:18:32.018"
}]
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

## Get Subaccount by ID

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/octane/subaccounts/{accountId}`

Returns an object for the `accountId`for an associated `apiKey`.

#### Query Parameters

| Name                                        | Type   | Description |
| ------------------------------------------- | ------ | ----------- |
| accountId<mark style="color:red;">\*</mark> | string | Order ID    |

#### Headers

| Name                                     | Type   | Description         |
| ---------------------------------------- | ------ | ------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key |

{% tabs %}
{% tab title="200: OK Success" %}
```json
{
  "id": "usr-123456790",
  "email": "test@account.com",
  "name": "subAccountName",
  "createdAt": "2023-12-10T00:46:14.786",
  "updatedAt": "2023-12-10T00:46:14.783"
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

**POST Subaccounts**

{% tabs %}
{% tab title="Curl" %}
```bash
curl -X POST \
  -H "Content-Type: application/json" \
  -d '{
    "api-key": "dev-api-key",
    "subAccount": {
      "name": "Zeek Zubert",
      "email": "zeekdonuts@gmail.com"
    }
  }' \
  https://api.abyiss.com/v2/octane/subaccounts
```
{% endtab %}

{% tab title="Python" %}
```python
import requests
import json

url = "https://api.abyiss.com/v2/octane/subaccounts"
headers = {
    "Content-Type": "application/json"
}

subaccount_data = {
    "api-key": "dev-api-key",
    "subAccount": {
        "name": "Zeek Zubert",
        "email": "zeekdonuts@gmail.com"
    }
}

response = requests.post(url, headers=headers, data=json.dumps(subaccount_data))

print(response.status_code)
print(response.json())
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
const axios = require('axios');

const url = 'https://api.abyiss.com/v2/octane/subaccounts';
const headers = {
    'Content-Type': 'application/json'
};

const subaccountData = {
    'api-key': 'dev-api-key',
    'subAccount': {
        'name': 'Zeek Zubert',
        'email': 'zeekdonuts@gmail.com'
    }
};

axios.post(url, subaccountData, { headers })
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

**GET Subaccounts**

{% tabs %}
{% tab title="Curl" %}
```bash
curl "https://api.abyiss.com/v2/octane/subaccounts?apiKey=YOUR_API_KEY_HERE"
```
{% endtab %}

{% tab title="Python" %}
```python
import requests

url = 'https://api.abyiss.com/v2/octane/subaccounts?apiKey=YOUR_API_KEY_HERE'

response = requests.get(url)

print(response.status_code)  # This will print the status code of the response
print(response.json())  # This will print the response content as JSON
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
const url = 'https://api.abyiss.com/v2/octane/subaccounts?apiKey=YOUR_API_KEY_HERE';

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

## Subaccounts **Response Object**

{% tabs %}
{% tab title="POST Subaccounts" %}
Example URL: [https://api.abyiss.com/v2/octane/subaccounts?apiKey=](https://api.abyiss.com/v2/octane/subaccounts?apiKey=)

```json
{
    "newSubAccountId": "usr-123456790"
}
```
{% endtab %}

{% tab title="Get Subaccounts" %}
Example URL: [https://api.abyiss.com/v2/octane/subaccounts?apiKey=](https://api.abyiss.com/v2/octane/subaccounts?apiKey=)

```json
[{
  "id": "usr-123456790",
  "email": "test@account.com",
  "name": "subAccountName",
  "createdAt": "2023-12-10T00:46:14.786",
  "updatedAt": "2023-12-10T00:46:14.783"
},{
  "id": "usr-123457800",
  "email": "zeekdonuts@gmail.com",
  "name": "Zeek Zubert",
  "createdAt": "2023-12-10T02:18:32.022",
  "updatedAt": "2023-12-10T02:18:32.018"
}]
```
{% endtab %}

{% tab title="Get Subaccount by Id" %}
Example URL: [https://api.abyiss.com/v2/octane/subaccounts/usr-123457800?apiKey=](https://api.abyiss.com/v2/octane/subaccounts/usr-123457800?apiKey=)

```json
{
  "id": "usr-123457800",
  "email": "zeekdonuts@gmail.com",
  "name": "Zeek Zubert",
  "createdAt": "2023-12-10T02:18:32.022",
  "updatedAt": "2023-12-10T02:18:32.018"
}
```
{% endtab %}
{% endtabs %}

## Subaccounts Response Attributes

| Attribute Name | Data Type | Description                                         |
| -------------- | --------- | --------------------------------------------------- |
| id             | string    | Unique user id.                                     |
| email          | string    | User email address.                                 |
| name           | string    | User first and last name.                           |
| createdAt      | string    | The timestamp the user account was created.         |
| updatedAt      | string    | The last timestamp the user account was updated at. |

