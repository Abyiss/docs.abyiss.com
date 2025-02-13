---
description: How to increase API data limit for centralized exchanges using pagination.
---

# Pagination

{% hint style="info" %}
**Get `/trades?limit=500`**
{% endhint %}

Abyiss implements cursor pagination for all REST requests that return arrays of data. This includes endpoints such as `/trades`, `/aggregates`, and `/orders`. By default, these endpoints return the latest items. To retrieve more results per page, you can specify the `limit` parameter.

The `limit` parameter determines the number of results to be included in each page of the response. It's important to note that the maximum pagination limit may vary depending on the specific exchange. Some exchanges may support higher pagination limits than others.

## Example

To fetch a page of trades with a limit of 500 results, you can use the following API request:

```bash
GET /trades?limit=500
```

**Example URL:**

[https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/trades?limit=500\&apiKey=YOUR\_API\_KEY](https://api.abyiss.com/v2/cex/coinbasepro/BTC-USD/trades?limit=500\&apiKey=YOUR_API_KEY)

## Parameters

<table><thead><tr><th width="150">Parameter</th><th width="211.4">Default</th><th>Description</th></tr></thead><tbody><tr><td>limit</td><td>200</td><td>Number of results per request. Maximum 50,000. (default 200)</td></tr></tbody></table>
