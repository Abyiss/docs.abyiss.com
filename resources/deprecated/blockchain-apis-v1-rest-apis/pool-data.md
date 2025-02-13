---
description: Get pools returns real-time or historical liquidity pool information.
---

# Pool Data

## Get Pool Data

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v1/dex/{exchange}/{blockchain}/pool/{pool}`

Returns an object of real-time or historical liquidity pool data on a decentralized exchange.

#### Path Parameters

| Name                                         | Type   | Description                           |
| -------------------------------------------- | ------ | ------------------------------------- |
| exchange<mark style="color:red;">\*</mark>   | string | Decentralized exchange Id             |
| blockchain<mark style="color:red;">\*</mark> | string | Blockchain for decentralized exchange |
| pool<mark style="color:red;">\*</mark>       | string | Pool contract address.                |

#### Query Parameters

| Name                                     | Type   | Description                                       |
| ---------------------------------------- | ------ | ------------------------------------------------- |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key                               |
| block                                    | string | The blockchain block number for historical data.  |

{% tabs %}
{% tab title="200: OK Success" %}
```javascript
{
    "id": "0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640",
    "createdAtBlockNumber": "12376729",
    "createdAtTimestamp": "1620250931",
    "feeGrowthGlobal0X128": "2339213828374794064772733186730511",
    "feeGrowthGlobal1X128": "1124563782191130285774006530912913360543821",
    "feeTier": "500",
    "feesUSD": "181745183.4919135479914293522951478",
    "liquidity": "28305971624606501584",
    "liquidityProviderCount": "0",
    "observationIndex": "0",
    "sqrtPrice": "1835788354854154061139441696943417",
    "tick": "201023",
    "token0Price": "1862.575758240059621582586480287811",
    "token1Price": "0.0005368909133365377831323097821773732",
    "totalValueLockedToken0": "238462791.284252",
    "totalValueLockedETH": "239468.5785032713504558275883499686",
    "totalValueLockedToken1": "111383.712791182627800798",
    "totalValueLockedUSD": "445832107.7770593355521122003026959",
    "totalValueLockedUSDUntracked": "0",
    "txCount": "4757298",
    "volumeUSD": "363490366983.8270959828587045902679",
    "volumeToken1": "173984279.507713960124759536",
    "volumeToken0": "363465170602.234639",
    "untrackedVolumeUSD": "363490366983.8270959828587045902679",
    "token0": {
        "id": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
        "name": "USD Coin",
        "symbol": "USDC",
        "decimals": "6",
        "supply": "19312",
        "totalValueLocked": "707789671.655521",
        "totalValueLockedUSD": "707789671.6555209999999999999999999",
        "volume": "594284344988.549264",
        "volumeUSD": "594132695519.3544168842644818168896",
        "untrackedVolumeUSD": "593933640776.891916756840567652356",
        "txCount": "9459463",
        "derivedETH": "0.0005371272600739174638130374035007628",
        "feesUSD": "542209018.6537476591450399921439473",
        "poolCount": "0"
    },
    "token1": {
        "id": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
        "name": "Wrapped Ether",
        "symbol": "WETH",
        "decimals": "18",
        "supply": "19848",
        "totalValueLocked": "630444.275881665783438372",
        "totalValueLockedUSD": "1173733531.593437237928802029139364",
        "volume": "344093461.934212462042438875",
        "volumeUSD": "753761660033.2402028813427752717856",
        "untrackedVolumeUSD": "418002379998220.6202981897849956904",
        "txCount": "24829241",
        "derivedETH": "1",
        "feesUSD": "1205941841.69999761982134759117516",
        "poolCount": "0"
    }
}
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
curl -H "apiKey: API KEY" https://api.abyiss.com/v1/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640
```
{% endtab %}

{% tab title="Python" %}
```python
import urllib.request
url = "https://api.abyiss.com/v1/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640?apiKey="
print(urllib.request.urlopen(url).read())
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
fetch("https://api.abyiss.com/v1/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640?apiKey=")
  .then(response => response.json())
  .then(data => console.log(data))
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
require('axios')
  .get("https://api.abyiss.com/v1/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640?apiKey=")
  .then(response => console.log(response))
```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require 'net/http'
uri = URI("https://api.abyiss.com/v1/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640?apiKey=")
puts Net::HTTP.get(uri)
```
{% endtab %}
{% endtabs %}

### **Response Object**

Example URL: [https://api.abyiss.com/v1/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640?apiKey=](https://api.abyiss.com/v1/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640?apiKey=)

```json
{
    "id": "0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640",
    "createdAtBlockNumber": "12376729",
    "createdAtTimestamp": "1620250931",
    "feeGrowthGlobal0X128": "2339213828374794064772733186730511",
    "feeGrowthGlobal1X128": "1124563782191130285774006530912913360543821",
    "feeTier": "500",
    "feesUSD": "181745183.4919135479914293522951478",
    "liquidity": "28305971624606501584",
    "liquidityProviderCount": "0",
    "observationIndex": "0",
    "sqrtPrice": "1835788354854154061139441696943417",
    "tick": "201023",
    "token0Price": "1862.575758240059621582586480287811",
    "token1Price": "0.0005368909133365377831323097821773732",
    "totalValueLockedToken0": "238462791.284252",
    "totalValueLockedETH": "239468.5785032713504558275883499686",
    "totalValueLockedToken1": "111383.712791182627800798",
    "totalValueLockedUSD": "445832107.7770593355521122003026959",
    "totalValueLockedUSDUntracked": "0",
    "txCount": "4757298",
    "volumeUSD": "363490366983.8270959828587045902679",
    "volumeToken1": "173984279.507713960124759536",
    "volumeToken0": "363465170602.234639",
    "untrackedVolumeUSD": "363490366983.8270959828587045902679",
    "token0": {
        "id": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
        "name": "USD Coin",
        "symbol": "USDC",
        "decimals": "6",
        "supply": "19312",
        "totalValueLocked": "707789671.655521",
        "totalValueLockedUSD": "707789671.6555209999999999999999999",
        "volume": "594284344988.549264",
        "volumeUSD": "594132695519.3544168842644818168896",
        "untrackedVolumeUSD": "593933640776.891916756840567652356",
        "txCount": "9459463",
        "derivedETH": "0.0005371272600739174638130374035007628",
        "feesUSD": "542209018.6537476591450399921439473",
        "poolCount": "0"
    },
    "token1": {
        "id": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
        "name": "Wrapped Ether",
        "symbol": "WETH",
        "decimals": "18",
        "supply": "19848",
        "totalValueLocked": "630444.275881665783438372",
        "totalValueLockedUSD": "1173733531.593437237928802029139364",
        "volume": "344093461.934212462042438875",
        "volumeUSD": "753761660033.2402028813427752717856",
        "untrackedVolumeUSD": "418002379998220.6202981897849956904",
        "txCount": "24829241",
        "derivedETH": "1",
        "feesUSD": "1205941841.69999761982134759117516",
        "poolCount": "0"
    }
}
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

