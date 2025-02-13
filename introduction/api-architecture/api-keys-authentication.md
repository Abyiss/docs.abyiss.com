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

Once you receive your API Key, you have access to most of the API endpoints. You are subject to our [rate limits](./rate-limits.md).

You will need to be KYC-verified when using the octane [POST transactions](../../octane-api/apis/transactions.md) endpoint. If you are not KYC-verified, you will receive a 403 Forbidden error.

## Passing Your API Key

{% hint style="warning" %}
**You can pass your API Key in the URL Query, Header, or Body of a Request**
{% endhint %}

We recommend passing your API Key within the header of the request, as it provides more security. The Abyiss Client Libraries automatically pass API Keys in the header of every request.

Below is an example of how to pass your API Key in the URL Query:

[`https://api.abyiss.com/v2/cex/exchanges?apiKey=YOUR_API_KEY`](https://api.abyiss.com/v2/cex/exchanges?apiKey=YOUR_API_KEY)

Below is an example of how to pass your API Key in the Header of a Curl Request:

```url
curl -H "api-key: API KEY" https://api.abyiss.com/v2/cex/exchanges
```

Below is an example of how to pass your API Key in the Body of a Curl Request:

```url
curl -X POST -H "Content-Type: application/json" -d '{"apiKey": "API KEY"}' https://api.abyiss.com/v2/cex/exchanges
```
