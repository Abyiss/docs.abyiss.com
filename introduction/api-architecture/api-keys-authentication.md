---
description: Abyiss API Keys and Authentication.
---

# API Keys - Authentication

## Generating an API Key

{% hint style="info" %}
**Generate an API Key** [**Here**](https://abyiss.com/dashboard)
{% endhint %}

Before being able to make any requests, you must sign up and create an API Key via [Abyiss.com](https://abyiss.com/dashboard). After signing up you will be redirected to your dashboard where you can find your API Key.

The API Key will be randomly generated and provided by Abyiss. Sign up for free [here](https://abyiss.com/signup).

## API Key Permissions

API Key functionality is restricted by your account plan. Free plans are giving permission to access reference data while premium plans get access to market data.

To learn more about our pricing and plans click [here](https://abyiss.com/pricing/).

## Passing Your API Key

{% hint style="warning" %}
**You can pass your API Key in the URL Query, Header, or Body of a Request**
{% endhint %}

We recommend passing your API Key within the header of the request, as it provides more security. The Abyiss Client Libraries automatically pass API Keys in the header of every request.

Below is an example of how to pass your API Key in the URL Query:

[`https://api.abyiss.com/v2/cex/exchanges?apiKey=YOUR_API_KEY`](https://api.abyiss.com/v2/cex/exchanges?apiKey=YOUR_API_KEY)

Below is an example of how to pass your API Key in the Header of a Curl Request:

```url
curl -H "apiKey: API KEY" https://api.abyiss.com/v2/cex/exchanges
```

Below is an example of how to pass your API Key in the Body of a Curl Request:

```url
curl -X POST -H "Content-Type: application/json" -d '{"apiKey": "API KEY"}' https://api.abyiss.com/v2/cex/exchanges
```
