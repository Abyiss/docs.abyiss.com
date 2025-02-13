---
description: Decentralized exchange error handling and codes.
---

# Error Handling

All requests and responses are `application/json` content type and follow typical HTTP response status codes for success and failure.&#x20;

## Success

A successful response is indicated by HTTP status code 200 and may contain an optional body. If the response has a body it will be documented.

## Errors

{% hint style="info" %}
**To access additional information about our error codes, please refer to the documentation on** [**Common Error Codes**](../../introduction/api-architecture/requests-and-error-codes.md)**.**
{% endhint %}

```json
{
   "message": "Exchange Not Found"
}
```

Unless otherwise stated, errors to bad requests will respond with HTTP 4xx or status codes. The body will also contain a `message` parameter indicating the cause. Your language's http library should be configured to provide message bodies for non-2xx requests so that you can read the message field from the body.

### Block Number

This error occurs when there is a failure to decode the `block.number` value. It is caused by the unavailability of data for a specific block number. This can happen when a token or liquidity pool did not exist at a certain block number and time.

To resolve this issue, you need to ensure that the requested token or liquidity pool exists at the specified block number. You may need to adjust the block number or time to a more recent point in the blockchain's history where the token or liquidity pool was already created.

If you encounter the following error message:

```json
{
    "message": "Failed to decode `block.number` value: `only has data starting at block number 12369620 and data for block number 1 is therefore not available`"
}
```

You can try specifying a higher block number, such as `12369621` or a later block number, depending on when the token or liquidity pool was created.

{% hint style="warning" %}
**Each blockchain has its own unique block number system, so be sure to consult the appropriate documentation for the blockchain you are using.**
{% endhint %}

### Contract Address

This error occurs when there is an error fetching the liquidity pool or token for a specified contract address id. It can happen when the contract address id does not exist on the blockchain.

To resolve this issue, you need to verify that the contract address id exists on the specified blockchain. Check that you have entered the correct contract address id and that the contract has been deployed on the blockchain.

If you encounter the following error message:

<pre class="language-json"><code class="lang-json">{
<strong>    "message": "Error fetching liquidity pool for address: "XXX"
</strong>}
</code></pre>

Double-check that the specified contract address id exists on the blockchain. You may need to consult the relevant documentation to ensure that the contract has been deployed and is active on the blockchain.

{% hint style="warning" %}
**Each blockchain has its own unique system for managing contract addresses. Be sure to consult the appropriate documentation for the blockchain you are using to verify the contract address.**
{% endhint %}
