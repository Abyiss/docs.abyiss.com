---
description: >-
  Get exchange data returns real-time or historical decentralized exchange
  information.
---

# Exchange Data

## Get Exchange Data

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/dex/{exchange}/{blockchain}`

Returns an array of real-time or historical decentralized exchange data.

#### Path Parameters

| Name                                         | Type   | Description                           |
| -------------------------------------------- | ------ | ------------------------------------- |
| exchange<mark style="color:red;">\*</mark>   | string | Decentralized exchange Id             |
| blockchain<mark style="color:red;">\*</mark> | string | Blockchain for decentralized exchange |

#### Query Parameters

| Name                                     | Type   | Description                                       |
| ---------------------------------------- | ------ | ------------------------------------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key                               |
| block                                    | int    | The blockchain block number for historical data.  |

{% tabs %}
{% tab title="200: OK Success" %}
```javascript
[
    {
        "id": "0x1F98431c8aD98523631AE4a59f267346ea31F984",
        "poolCount": "10950",
        "txCount": "29888206",
        "totalVolumeUSD": "916847401937.370607825600628166657",
        "untrackedVolumeUSD": "418167060018759.7426039553582786604",
        "totalVolumeETH": "423116538.4473012264357507657269329",
        "totalValueLockedUSD": "1523577228461.761271658156460855197",
        "totalValueLockedETH": "843327060.2839120939378000489695211",
        "totalFeesUSD": "1369740249.46500696391926330064492",
        "totalFeesETH": "575159.1527922034001220649655581179",
        "owner": "0x0000000000000000000000000000000000000000"
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
curl -H "apiKey: API KEY" https://api.abyiss.com/v2/dex/uniswap/ethereum
```
{% endtab %}

{% tab title="Python" %}
```python
import urllib.request
url = "https://api.abyiss.com/v2/dex/uniswap/ethereum?apiKey=*"
print(urllib.request.urlopen(url).read())
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v2/dex/uniswap/ethereum?apiKey=*")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v2/dex/uniswap/ethereum?apiKey=*")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v2/dex/uniswap/ethereum?apiKey=*")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### **Response Object**

Example URL: [https://api.abyiss.com/v2/dex/uniswap/ethereum?apiKey=](https://api.abyiss.com/v2/dex/uniswap/ethereum?apiKey=)

```json
[
    {
        "id": "0x1F98431c8aD98523631AE4a59f267346ea31F984",
        "poolCount": "10950",
        "txCount": "29888206",
        "totalVolumeUSD": "916847401937.370607825600628166657",
        "untrackedVolumeUSD": "418167060018759.7426039553582786604",
        "totalVolumeETH": "423116538.4473012264357507657269329",
        "totalValueLockedUSD": "1523577228461.761271658156460855197",
        "totalValueLockedETH": "843327060.2839120939378000489695211",
        "totalFeesUSD": "1369740249.46500696391926330064492",
        "totalFeesETH": "575159.1527922034001220649655581179",
        "owner": "0x0000000000000000000000000000000000000000"
    }
]
```

### Response Attributes

| Attribute Name      | Data Type | Description                                      |
| ------------------- | --------- | ------------------------------------------------ |
| id                  | string    | Exchange contact address                         |
| poolCount           | string    | Amount of pools created                          |
| txCount             | string    | Amount of transactions all-time                  |
| totalVolumeUSD      | string    | Total volume all-time in derived USD             |
| untrackedVolumeUSD  | string    | All volume even through less reliable USD values |
| totalVolumeETH      | string    | Total volume all-time in derived ETH             |
| totalValueLockedUSD | string    | TVL derived in USD                               |
| totalValueLockedETH | string    | TVL derived in ETH                               |
| totalFeesUSD        | string    | Total swap fees all-time in USD                  |
| totalFeesETH        | string    | Total swap fees all-time in ETH                  |
| owner               | string    | Current owner of the cotnract address.           |

