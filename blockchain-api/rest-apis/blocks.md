---
description: >-
  Get blocks returns real-time or historical blockchain block numbers and
  timestamps.
---

# Blocks

## Get Blocks

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/blocks`

Provides a list of compatible blockchains for retrieving block numbers and timestamps in an array.

#### Query Parameters

| Name                                     | Type   | Description         |
| ---------------------------------------- | ------ | ------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key |

{% tabs %}
{% tab title="200: OK Success" %}
```json
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

## Get Blockchain Blocks

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/blocks/{blockchain}`

Returns an array of real-time or historical blockchain block numbers and timestamps.&#x20;

#### Path Parameters

| Name                                         | Type   | Description                       |
| -------------------------------------------- | ------ | --------------------------------- |
| blockchain<mark style="color:red;">\*</mark> | string | Blockchain for the block numbers. |

#### Query Parameters

| Name                                     | Type   | Description                                                                                                    |
| ---------------------------------------- | ------ | -------------------------------------------------------------------------------------------------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key                                                                                            |
| limit                                    | int    | Number of results per request. Maximum 1,0000 (defualt 100)                                                    |
| skip                                     | int    | Number of results to skip per request.                                                                         |
| orderBy                                  | string | Sort the returned data by any field in the API response, such as `id`, `name`, `symbol`, `volumeUSD` and more. |
| orderDirection                           | string | `asc` or `desc` return the results sorted by that field in either ascending or descending order.               |
| block                                    | int    | The blockchain block number for historical data.                                                               |
| from                                     | int    | The start of the aggregate time window for historical data. Unix timestamp in milliseconds.                    |
| to                                       | int    | The end of the aggregate time window for historical data. Unix timestamp in milliseconds.                      |

{% tabs %}
{% tab title="200: OK Success" %}
```javascript
[
    {
        "number": "17017595",
        "timestamp": "1681127183",
        "size": "379123",
        "gasLimit": "30000000",
        "gasUsed": "21721808",
        "totalDifficulty": "58750003716598352816469",
        "author": "0x4838b106fce9647bdf1e7877bf73ce8b0bad5f97"
    }
]
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

### **Copy & Paste Code**

{% tabs %}
{% tab title="Curl" %}
```bash
curl -H "apiKey: API KEY" https://api.abyiss.com/v2/blocks/ethereum
```
{% endtab %}

{% tab title="Python" %}
```python
import urllib.request
url = "https://api.abyiss.com/v2/blocks/ethereum?apiKey="
print(urllib.request.urlopen(url).read())
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v2/blocks/ethereum?apiKey=")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v2/blocks/ethereum?apiKey=")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v2/blocks/ethereum?apiKey=")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### **Response Object**

Example URL: [https://api.abyiss.com/v2/blocks/ethereum?apiKey=](https://api.abyiss.com/v2/blocks/ethereum?apiKey=)

```json
[
    {
        "number": "17017595",
        "timestamp": "1681127183",
        "size": "379123",
        "gasLimit": "30000000",
        "gasUsed": "21721808",
        "totalDifficulty": "58750003716598352816469",
        "author": "0x4838b106fce9647bdf1e7877bf73ce8b0bad5f97"
    }
]
```

### Response Attributes

| Attribute Name  | Data Type | Description             |
| --------------- | --------- | ----------------------- |
| number          | string    | Blockchain block number |
| timestamp       | string    | Block number timestamp  |
| size            | string    | Block size              |
| gasLimit        | string    | Block gas limit         |
| gasUsed         | string    | Block gas used          |
| totalDifficulty | string    | Block total difficulty  |
| author          | string    | Block author            |

