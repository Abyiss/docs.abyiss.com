---
description: Get pools returns real-time or historical liquidity pool information.
---

# Pools

## Get Pools

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v2/dex/{exchange}/{blockchain}/pools`

Returns an array of real-time or historical liquidity pool data on a decentralized exchange.

#### Path Parameters

| Name                                         | Type   | Description                           |
| -------------------------------------------- | ------ | ------------------------------------- |
| exchange<mark style="color:red;">\*</mark>   | string | Decentralized exchange Id             |
| blockchain<mark style="color:red;">\*</mark> | string | Blockchain for decentralized exchange |

#### Query Parameters

| Name                                     | Type   | Description                                                                                                    |
| ---------------------------------------- | ------ | -------------------------------------------------------------------------------------------------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key                                                                                            |
| block                                    | string | The blockchain block number for historical data.                                                               |
| orderDirection                           | string | `asc` or `desc` return the results sorted by that field in either ascending or descending order.               |
| limit                                    | int    | Number of results per request. Maximum 1,0000 (default 100).                                                   |
| skip                                     | int    | Number of results to skip per request.                                                                         |
| orderBy                                  | string | Sort the returned data by any field in the API response, such as `id`, `name`, `symbol`, `volumeUSD` and more. |
| pool                                     | string | Pool contract address.                                                                                         |

{% tabs %}
{% tab title="200: OK Success" %}
```javascript
[
    {
        "id": "0x079e7a44f42e9cd2442c3b9536244be634e8f888",
        "createdAtBlockNumber": "13946834",
        "createdAtTimestamp": "1657313501",
        "feeGrowthGlobal0X128": "33523166756957040825870650430606840539",
        "feeGrowthGlobal1X128": "22063097588048839229216940673559101699",
        "feeTier": "3000",
        "feesUSD": "41186.94681670499373145428075267476",
        "liquidity": "275259128840772456455165",
        "liquidityProviderCount": "0",
        "observationIndex": "0",
        "sqrtPrice": "65362472457790533497927346876",
        "tick": "-3848",
        "token0Price": "1.469272072774257022696235099374057",
        "token1Price": "0.6806091387225616540765640838845884",
        "totalValueLockedToken0": "142039.789600282692041837",
        "totalValueLockedETH": "263008.053681041453909217827219603",
        "totalValueLockedToken1": "82332.106028768612285469",
        "totalValueLockedUSD": "179005.6848929508851906505477017337",
        "totalValueLockedUSDUntracked": "0",
        "txCount": "104626",
        "volumeUSD": "13728982.27223499791048476025089143",
        "volumeToken1": "13728566.48633066654357228",
        "volumeToken0": "18460880.139639477926207025",
        "untrackedVolumeUSD": "13728982.27223499791048476025089143",
        "token0": {
            "id": "0x471ece3750da237f93b8e339c536989b8978a438",
            "name": "Celo native asset",
            "symbol": "CELO",
            "decimals": "18",
            "supply": "17944",
            "totalValueLocked": "374576.456855717828257672",
            "totalValueLockedUSD": "254940.1596863188857054923984137805",
            "volume": "23767113.778304894745609846",
            "volumeUSD": "17407269.47751284527203886578825922",
            "untrackedVolumeUSD": "17406491.72059735368630709682542912",
            "txCount": "174411",
            "derivedETH": "1",
            "feesUSD": "52513.09229442114283010429308286935",
            "poolCount": "0"
        },
        "token1": {
            "id": "0x765de816845861e75a25fca122bb6898b8b1282a",
            "name": "Celo Dollar",
            "symbol": "cUSD",
            "decimals": "18",
            "supply": "19016",
            "totalValueLocked": "877370.388895971647748686",
            "totalValueLockedUSD": "877370.3888959716477486859999999994",
            "volume": "33020496.407084955037673747",
            "volumeUSD": "33019355.07616878761990110619958443",
            "untrackedVolumeUSD": "33019086.25410862590614718721990349",
            "txCount": "251660",
            "derivedETH": "1.469272072774257022696235099374057",
            "feesUSD": "55320.67186157799866500784717264333",
            "poolCount": "0"
        }
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
curl -H "apiKey: API KEY" https://api.abyiss.com/v2/dex/uniswap/ethereum/pools
```
{% endtab %}

{% tab title="Python" %}
```python
import urllib.request
url = "https://api.abyiss.com/v2/dex/uniswap/ethereum/pools?apiKey="
print(urllib.request.urlopen(url).read())
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v2/dex/uniswap/ethereum/pools?apiKey=")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v2/dex/uniswap/ethereum/pools?apiKey=")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v2/dex/uniswap/ethereum/pools?apiKey=")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### **Response Object**

Example URL: [https://api.abyiss.com/v2/dex/uniswap/ethereum/pools?apiKey=](https://api.abyiss.com/v2/dex/uniswap/ethereum/pools?apiKey=)

```json
[
    {
        "id": "0x079e7a44f42e9cd2442c3b9536244be634e8f888",
        "createdAtBlockNumber": "13946834",
        "createdAtTimestamp": "1657313501",
        "feeGrowthGlobal0X128": "33523166756957040825870650430606840539",
        "feeGrowthGlobal1X128": "22063097588048839229216940673559101699",
        "feeTier": "3000",
        "feesUSD": "41186.94681670499373145428075267476",
        "liquidity": "275259128840772456455165",
        "liquidityProviderCount": "0",
        "observationIndex": "0",
        "sqrtPrice": "65362472457790533497927346876",
        "tick": "-3848",
        "token0Price": "1.469272072774257022696235099374057",
        "token1Price": "0.6806091387225616540765640838845884",
        "totalValueLockedToken0": "142039.789600282692041837",
        "totalValueLockedETH": "263008.053681041453909217827219603",
        "totalValueLockedToken1": "82332.106028768612285469",
        "totalValueLockedUSD": "179005.6848929508851906505477017337",
        "totalValueLockedUSDUntracked": "0",
        "txCount": "104626",
        "volumeUSD": "13728982.27223499791048476025089143",
        "volumeToken1": "13728566.48633066654357228",
        "volumeToken0": "18460880.139639477926207025",
        "untrackedVolumeUSD": "13728982.27223499791048476025089143",
        "token0": {
            "id": "0x471ece3750da237f93b8e339c536989b8978a438",
            "name": "Celo native asset",
            "symbol": "CELO",
            "decimals": "18",
            "supply": "17944",
            "totalValueLocked": "374576.456855717828257672",
            "totalValueLockedUSD": "254940.1596863188857054923984137805",
            "volume": "23767113.778304894745609846",
            "volumeUSD": "17407269.47751284527203886578825922",
            "untrackedVolumeUSD": "17406491.72059735368630709682542912",
            "txCount": "174411",
            "derivedETH": "1",
            "feesUSD": "52513.09229442114283010429308286935",
            "poolCount": "0"
        },
        "token1": {
            "id": "0x765de816845861e75a25fca122bb6898b8b1282a",
            "name": "Celo Dollar",
            "symbol": "cUSD",
            "decimals": "18",
            "supply": "19016",
            "totalValueLocked": "877370.388895971647748686",
            "totalValueLockedUSD": "877370.3888959716477486859999999994",
            "volume": "33020496.407084955037673747",
            "volumeUSD": "33019355.07616878761990110619958443",
            "untrackedVolumeUSD": "33019086.25410862590614718721990349",
            "txCount": "251660",
            "derivedETH": "1.469272072774257022696235099374057",
            "feesUSD": "55320.67186157799866500784717264333",
            "poolCount": "0"
        }
    }
]
```

### Response Attributes

| Attribute Name               | Data Type | Description                                               |
| ---------------------------- | --------- | --------------------------------------------------------- |
| id                           | string    | Pool contract address                                     |
| createdAtBlockNumber         | string    | Block pool was created at                                 |
| createdAtTimestamp           | string    | Timestamp pool was created at                             |
| feeGrowthGlobal0X128         | string    | Tracker for global fee growth                             |
| feeGrowthGlobal1X128         | string    | Tracker for global fee growth                             |
| feeTier                      | string    | Fee amount                                                |
| feesUSD                      | string    | Fees in USD                                               |
| liquidity                    | string    | In range liquidity                                        |
| liquidityProviderCount       | string    | used to detect new exchanges                              |
| observationIndex             | string    | Current observation index                                 |
| sqrtPrice                    | string    | current price tracker                                     |
| tick                         | string    | current tick                                              |
| token0Price                  | string    | token0 per token1                                         |
| token1Price                  | string    | token1 per token0                                         |
| totalValueLockedToken0       | string    | total token 0 across all ticks                            |
| totalValueLockedETH          | string    | tvl derived ETH                                           |
| totalValueLockedToken1       | string    | total token 1 across all ticks                            |
| totalValueLockedUSD          | string    | tvl USD                                                   |
| totalValueLockedUSDUntracked | string    | TVL derived in USD untracked                              |
| txCount                      | string    | all time number of transactions                           |
| volumeUSD                    | string    | all time USD swapped                                      |
| volumeToken1                 | string    | all time token1 swapped                                   |
| volumeToken0                 | string    | all time token0 swapped                                   |
| untrackedVolumeUSD           | string    | all time USD swapped, unfiltered for unreliable USD pools |
| token0                       | string    | token0                                                    |
| token1                       | string    | token1                                                    |
| id                           | string    | Token contract address                                    |
| name                         | string    | Token name                                                |
| symbol                       | string    | Token symbol                                              |
| decimals                     | string    | token decimals                                            |
| supply                       | string    | token total supply                                        |
| totalValueLocked             | string    | liquidity in token units                                  |
| totalValueLockedUSD          | string    | liquidity in derived USD                                  |
| volume                       | string    | volume in token units                                     |
| volumeUSD                    | string    | volume in derived USD                                     |
| untrackedVolumeUSD           | string    | volume in USD even on pools with less reliable USD values |
| txCount                      | string    | transactions across all pools that include this token     |
| derivedETH                   | string    | derived price in ETH                                      |
| feesUSD                      | string    | fees in USD                                               |
| poolCount                    | string    | number of pools containing this token                     |

