---
description: Abyiss API requests and error codes.
---

# Requests & Error Codes

All requests and responses are `application/json` content type and follow typical HTTP response status codes for success and failure.&#x20;

## Errors

```json
{
   "message": "Exchange Not Found"
}
```

Unless otherwise stated, errors to bad requests will respond with HTTP 4xx or status codes. The body will also contain a `message` parameter indicating the cause. Your language's http library should be configured to provide message bodies for non-2xx requests so that you can read the message field from the body.

## Success

A successful response is indicated by HTTP status code 200 and may contain an optional body. If the response has a body it will be documented.

## Common Error Codes

<table><thead><tr><th width="297">Status Code</th><th>Reason</th></tr></thead><tbody><tr><td>400</td><td>Bad Request - Invalid request format</td></tr><tr><td>401</td><td>Unauthorized -- Invalid API Key</td></tr><tr><td>402</td><td>Maximum API Query Limit</td></tr><tr><td>403</td><td>Forbidden -- You do not have access to the requested resource</td></tr><tr><td>404</td><td>Not Found</td></tr><tr><td>405</td><td>Exchange Data Unavailable</td></tr><tr><td>500</td><td>Internal Server Error -- We had a problem with our server</td></tr></tbody></table>
