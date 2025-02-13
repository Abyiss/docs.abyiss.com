---
description: How to get started with the Abyiss API.
---

# Getting Started

{% hint style="info" %}
**API access differs based on your plan**
{% endhint %}

## Getting Started with the Abyiss API

Welcome to the Abyiss API! This guide will walk you through the steps to get started and harness the power of our API, enabling you to connect to over 100+ cryptocurrency exchanges and access real-time data for more than 100,000+ cryptocurrencies.

## Step 1: Get Your API Keys

To begin using the Abyiss API, you'll need to [sign up for an account](https://abyiss.com/signin). Once you have an account, you can find your API Key in the [dashboard](https://abyiss.com/home). API keys are used for authentication in all your API requests. Requests without a valid API key will result in an error.&#x20;

To learn more about Authentication and API Keys please reference the [API Keys - Authentication](api-architecture/api-keys-authentication.md) section under [API Architecture](api-architecture/).&#x20;

## Step 2: Explore Available Endpoints

Our API Endpoints are broken up into a few categories:

* [**Crypto API**](broken-reference): Access real-time and historical data for over 100,000+ cryptocurrencies across 100+ centralized exchanges. Retrieve information such as market prices, trading volumes, and more.
* [**Blockchain API**](broken-reference): Interact with blockchain networks and retrieve data related to decentralized exchanges, blocks, tokens, liquidity pools, and more. Leverage this API category to build applications that require direct access to blockchain data.
* [**Alerts API**](broken-reference): Set up custom alerts and notifications for specific events or market conditions. Stay informed about price changes, volume fluctuations, or other criteria that are crucial to your cryptocurrency trading or analysis strategies.

You will need an [API Key](api-architecture/api-keys-authentication.md) to access all of our endpoints.

## Step 3: Make Your First Request

To make your first request, just ping our API: [https://api.abyiss.com/ping](https://api.abyiss.com/ping). This will return "Hello from the Abyiss". All requests return JSON-encoded responses.&#x20;

## Ping Abyiss

<mark style="color:blue;">`GET`</mark> `https://api.abyiss.com/ping`

Returns "Hello from the Abyiss"

{% tabs %}
{% tab title="200: OK Success" %}
```javascript
{
    "ping": "Hello from the Abyiss"
}
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Make Your First Request" %}
#### Example URL

{% embed url="https://api.abyiss.com/ping" %}
Click me!
{% endembed %}

#### Response Object

```json
{
    "ping": "Hello from the Abyiss"
}
```
{% endtab %}
{% endtabs %}

## Step 4: Copy & Paste Code

Take a look at how you might call our API using the following programing languages.&#x20;

Feel free to copy and paste this code into your own development environment and try it for yourself.&#x20;

{% tabs %}
{% tab title="Python" %}
```python
from Abyiss import Abyiss

apiKey = "YOUR API KEY"" 
client = Abyiss.Client(apiKey) 


exchanges = client.getExchanges()

exchangeDetails = client.getExchangeDetails("coinbasepro")

exchangeStatus = client.getExchangeStatus("coinbasepro")

exchangeMarkets = client.getExchangeMarkets("coinbasepro")

exchangeMarketDetails = client.getMarketDetails("coinbasepro", "BTC-USDT")

aggregates = client.aggregates("coinbasepro", "BTC-USDT", "1h", '300')

trades = client.trades("coinbasepro", "BTC-USDT", '300')

quotes = client.quotes("coinbasepro", "BTC-USDT")

orderbook = client.orderBook("coinbasepro", "BTC-USDT")
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
import { Abyiss } from 'abyiss'

const A = new Abyiss('YOUR API KEY')

async function showExchanges () {
  console.log(await A.exchanges())
}

async function aggregate () {
    console.log(await A.aggregates('coinbasepro', 'btc-usd', '1m', {limit: 2})) 
}

showExchanges()
aggregate()
```
{% endtab %}

{% tab title="Curl" %}
```shell
curl https://api.abyiss.com/ping
```
{% endtab %}
{% endtabs %}

## Step 5: Client Libraries

To simplify your integration process, we provide [Client Libraries](client-libraries.md) in various programming languages. You can find our client libraries on GitHub. These libraries offer convenient methods and examples to help you interact with our API in your preferred programming language. Feel free to copy and paste the code examples into your development environment and try them out.

Currently, we support client libraries in the following programming languages:

{% embed url="https://github.com/Abyiss/Client-python" %}
Python Client
{% endembed %}

{% embed url="https://github.com/Abyiss/Client-js" %}
Javascript Client
{% endembed %}

{% embed url="https://github.com/Abyiss/Client-http" %}
HTTP Client
{% endembed %}

For more information about our client libraries, please refer to the GitHub documentation.

## Need support?

If you need any additional support please contact us on our website [Abyiss.com](https://abyiss.com/contact) or send us an email at [support@abyiss.com](mailto:support@abyiss.com). We are here to help.
