---
description: Decentralized exchange API query parameters.
---

# Query Parameters

## Introduction

The Abyiss DEX API supports a range of query parameters to help you customize your data requests. These parameters allow you to filter, sort, and paginate the data returned by the API, making it easier to extract the information you need more efficiently.

Here are the four main query parameters available in the Abyiss DEX APIs. For the following API endpoints:

* [**Tokens**](../rest-apis/tokens.md)
* [**Token Aggregates (Bars)**](../rest-apis/token-aggregates-bars.md)
* [**Liquidity Pool Aggregates (Bars)**](../rest-apis/pool-aggregates-bars.md)

By using the query parameters available in the Abyiss DEX API, you can fine-tune your data requests and get the most relevant and up-to-date information from your preferred decentralized exchanges.

## Query Parameters

### Limit

This parameter specifies the number of results to return per request. The maximum value is 1,000, and the default value is 100.

**Example URL**: [https://api.abyiss.com/v2/dex/uniswap/ethereum/tokens?limit=500\&apiKey=](https://api.abyiss.com/v2/dex/uniswap/ethereum/tokens?limit=500\&apiKey=)

| Query Parameter | Data Type | Description                                                  |
| --------------- | --------- | ------------------------------------------------------------ |
| `limit`         | int       | Number of results per request. Maximum 1,0000 (default 100). |

### Order By

This `orderBy` parameter allows you to specify the field to sort the returned data by. You can enter the name of any field in the API response, such as `id`, `name`, `symbol`, `volumeUSD` and more.&#x20;

The API will return the results sorted by that field in either ascending or descending order. For example, if you specify `orderBy=id`, the API will sort the results by ID in ascending order.

**Example URL**: [https://api.abyiss.com/v2/dex/uniswap/ethereum/tokens?orderBy=volumeUSD\&apiKey=](https://api.abyiss.com/v2/dex/uniswap/ethereum/tokens?orderBy=volumeUSD\&apiKey=)

| Query Parameter | Type   | Description                                                                                                    |
| --------------- | ------ | -------------------------------------------------------------------------------------------------------------- |
| `orderBy`       | string | Sort the returned data by any field in the API response, such as `id`, `name`, `symbol`, `volumeUSD` and more. |

### Order Direction

This `orderDirection` parameter specifies the direction to sort the results in. You can choose between `asc` (ascending) and `desc` (descending) order.

**Example URL**: [https://api.abyiss.com/v2/dex/uniswap/ethereum/tokens?orderDirection=asc\&apiKey=](https://api.abyiss.com/v2/dex/uniswap/ethereum/tokens?orderDirection=asc\&apiKey=)

| Query Parameter  | Type   | Description                                                                                      |
| ---------------- | ------ | ------------------------------------------------------------------------------------------------ |
| `orderDirection` | string | `asc` or `desc` return the results sorted by that field in either ascending or descending order. |

### Skip

This `skip` parameter specifies the number of results to skip per request. For example, if you set skip=100, the API will skip the first 100 results and return the next 100 results.

**Example URL**: [https://api.abyiss.com/v2/dex/uniswap/ethereum/tokens?skip=1000\&apiKey=](https://api.abyiss.com/v2/dex/uniswap/ethereum/tokens?skip=1000\&apiKey=)

<table><thead><tr><th width="212.33333333333331">Query Parameter</th><th>Type</th><th>Description</th></tr></thead><tbody><tr><td><code>skip</code></td><td>int</td><td>Number of results to skip per request.</td></tr></tbody></table>

### Block

The `block` parameter specifies the blockchain block number for historical data. For example, if you set block=123456, the API will return data for the specified block number.

**Example URL**: [https://api.abyiss.com/v2/dex/uniswap/ethereum?block=16309685\&apiKey=](https://api.abyiss.com/v2/dex/uniswap/ethereum?block=16309685\&apiKey=)

| Query Parameter | Type | Description                                      |
| --------------- | ---- | ------------------------------------------------ |
| `block`         | int  | The blockchain block number for historical data. |

### From

The `from` parameter specifies the start of the aggregate time window for historical data, and it must be provided as a Unix timestamp in milliseconds.&#x20;

For example, if you set from=1617644400000, the API will return data starting from April 5th, 2021 at 12:00:00 AM UTC.

**Example URL**: [https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2/aggregate?timeframe=day\&from=1617644400000\&apiKey=](https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2/aggregate?timeframe=day\&from=1617644400000\&apiKey=)

| Query Parameter | Type | Description                                                                                 |
| --------------- | ---- | ------------------------------------------------------------------------------------------- |
| `from`          | int  | The start of the aggregate time window for historical data. Unix timestamp in milliseconds. |

### To

The `to` parameter specifies the end of the aggregate time window for historical data, and it must be provided as a Unix timestamp in milliseconds.&#x20;

For example, if you set to=1617730799000, the API will return data up until April 6th, 2021 at 11:59:59 PM UTC.

**Example URL**: [https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2/aggregate?timeframe=day\&to=1617730799000\&apiKey=](https://api.abyiss.com/v2/dex/uniswap/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2/aggregate?timeframe=day\&to=1617730799000\&apiKey=)

| Query Parameter | Type | Description                                                                               |
| --------------- | ---- | ----------------------------------------------------------------------------------------- |
| `to`            | int  | The end of the aggregate time window for historical data. Unix timestamp in milliseconds. |

### Mint

The `mint` parameter is a boolean data type that is only applicable to the trades endpoints. By default, it is set to 'true', which means that the API will return the mints array on the trades endpoints. However, if you set 'mint' to 'false', the mints array will not be returned.

**Example URL**: [https://api.abyiss.com/v2/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640/trades?mint=false\&apiKey=](https://api.abyiss.com/v2/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640/trades?mint=false\&apiKey=)

| Query Parameter | Type    | Description                            |
| --------------- | ------- | -------------------------------------- |
| `mint`          | boolean | Set to false to not return mint array. |

### Burn

The `burn` parameter is a boolean data type that is only applicable to the trades endpoints. By default, it is set to 'true', which means that the API will return the burns array on the trades endpoints. However, if you set 'burn' to 'false', the burns array will not be returned.

**Example URL**: [https://api.abyiss.com/v2/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640/trades?burn=false\&apiKey=](https://api.abyiss.com/v2/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640/trades?burn=false\&apiKey=)

| Query Parameter | Type    | Description                            |
| --------------- | ------- | -------------------------------------- |
| `burn`          | boolean | Set to false to not return burn array. |

### Swap

The `swap` parameter is a boolean data type that is only applicable to the trades endpoints. By default, it is set to 'true', which means that the API will return the swaps array on the trades endpoints. However, if you set 'swap' to 'false', the swaps array will not be returned.

**Example URL**: [https://api.abyiss.com/v2/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640/trades?swap=false\&apiKey=](https://api.abyiss.com/v2/dex/uniswap/ethereum/pool/0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640/trades?swap=false\&apiKey=)

| Query Parameter | Type    | Description                            |
| --------------- | ------- | -------------------------------------- |
| `swap`          | boolean | Set to false to not return swap array. |

### Logo

The token `logo` parameter is a boolean data type that is only applicable to the tokens endpoint. By default, it is set to 'false', which means that the API will not return the token logos. However, if you set '`logo`' to 'true', the tokens logos will be returned.

**Example URL**:&#x20;

[https://api.abyiss.com/v2/dex/uniswap/ethereum/tokens?tokenSymbol=WETH\&logo=true\&apiKey=YOUR\_API\_KEY](https://api.abyiss.com/v2/dex/uniswap/ethereum/tokens?tokenSymbol=WETH\&logo=true\&apiKey=YOUR_API_KEY)
