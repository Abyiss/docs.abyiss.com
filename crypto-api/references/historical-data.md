---
description: How to get centralized exchanges historical data and information.
---

# Historical Data

{% hint style="info" %}
**Historical price trends can indicate the future direction of a cryptocurrency**
{% endhint %}

Historical data provides several years of daily historical crypto prices, volumes, trades, and aggregates for each cryptocurrency.&#x20;

Historical data is exchange specific, so some exchanges provide more historical data than others. If you want to save large amounts of historical data, please [contact us here](mailto:sales@abyiss.com).

## How It Works

Historical data is accessible on the [**`trades`** ](../rest-apis/last-trade.md)and [**`aggregates`** ](../rest-apis/aggregates-bars.md) market data endpoints.

To access historical data, use the **`since`** parameter. The **`since`** parameter accepts a Unix timestamp from where you want the data to start.

To help convert Unix timestamps we use [https://www.unixtimestamp.com](https://www.unixtimestamp.com/).

| Parameter | Data Type | Description                                           |
| --------- | --------- | ----------------------------------------------------- |
| `since`   | Int       | Unix Timestamp from where you want the time to start. |

## Historical Data

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/v1/{exchange}/{market}/trades?since={Unix Timestamp}`

Returns an object with historical trade data.

#### Path Parameters

| Name                                       | Type   | Description                                         |
| ------------------------------------------ | ------ | --------------------------------------------------- |
| exchange<mark style="color:red;">\*</mark> | string | Unique exchange identifier used by Abyiss.          |
| market<mark style="color:red;">\*</mark>   | string | Unique Crypto Pair identifier used by the exchange. |

#### Query Parameters

| Name                                     | Type   | Description                                                             |
| ---------------------------------------- | ------ | ----------------------------------------------------------------------- |
| since<mark style="color:red;">\*</mark>  | int    | Unix Timestamp from where you want the data to start. (Historical Data) |
| limit                                    | int    | Number of results per request. Maximum 50,000. (default 200)            |
| apiKey<mark style="color:red;">\*</mark> | string | Your Abyiss API Key                                                     |

{% tabs %}
{% tab title="200: OK Success" %}
```javascript
{
    "exchange": "binance",
    "market": "BTC/USDT",
    "trades": [
        {
            "id": "2214",
            "timestamp": "1503000000087",
            "price": 4307.56,
            "size": 3.789232,
            "cost": 16322.344193920002,
            "side": "buy"
        },
        {
            "id": "2215",
            "timestamp": "1503000038104",
            "price": 4325.23,
            "size": 0.229059,
            "cost": 990.73285857,
            "side": "buy"
        },
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

### Response Object

**Trades** Example URL:[ https://api.abyiss.com/v2/cex/binance/btc-usdt/trades?since=1503000000000\&limit=100\&apiKey=](https://api.abyiss.com/v2/cex/binance/btc-usdt/trades?since=1503000000000\&limit=100\&apiKey=)

```json
{
    "exchange": "binance",
    "market": "BTC/USDT",
    "trades": [
        {
        "id": "2214",
        "timestamp": "1503000000087",
        "price": 4307.56,
        "size": 3.789232,
        "cost": 16322.344193920002,
        "side": "buy"
        },
}
```

**Aggregates** Example URL: [https://api.abyiss.com/v2/cex/binance/btc-usdt/aggregates/1h?since=1503000000000\&limit=100\&apiKey=](https://api.abyiss.com/v2/cex/binance/btc-usdt/aggregates/1h?since=1503000000000\&limit=100\&apiKey=)

```json
{
    "exchange": "binance",
    "market": "BTC/USDT",
    "aggregates": [
        {
        "t": 1503000000000,
        "o": 4307.56,
        "h": 4354.84,
        "l": 4258.56,
        "c": 4346.74,
        "v": 48.975472
        },
}
```
