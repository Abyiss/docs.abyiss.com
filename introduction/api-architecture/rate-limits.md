---
description: How rate limits work with the Abyiss API.
---

# Rate Limits

## Rate Limit for REST API

The Abyiss REST API enforces rate limits to ensure fair usage and maintain system performance. When a rate limit is exceeded, a response with a status of **`429 Too Many Requests`** will be returned.

By default, all API endpoints are throttled based on the requesting IP address. The general rate limit is set to 10 requests per second, with the ability to handle bursts of up to 15 requests per second. Please note that certain endpoints may have custom rate limits depending on their specific usage and requirements.

## Higher Rate Limits

If you require a higher rate limit for your application or have specific business needs, we offer custom rate limit options. To discuss a higher rate limit tailored to your requirements, please contact our team at [**support@abyiss.com**](<mailto:support@abyiss.com >). They will be happy to assist you with your request.

## How It Works

Our rate limiting uses a lazy-fill token bucket implementation. A TokenBucket stores a maximum amount of tokens which is the burst size and fills at a given rate called the refresh rate. The bucket will start full and as requests are received a token is removed for each request. Tokens are continuously added to the bucket at the refresh rate until full.

When a user sends a request, here's how TokenBucket calculates whether or not to rate limit the user:

1. Fill the user's TokenBucket to a token size based on the following formula:\
   `token_amount = min(burst, previous_token_amount + (current_time - previous_request_time) * refresh_rate)`
2. Remove 1 token if possible, otherwise rate limit the request.
3. Repeat Steps 1 and 2 for each subsequent request.

## Example

Let's say you have a TokenBucket with burst = 3 and refresh\_rate = 1. The table below represents the state of your token bucket after a series of requests

<table><thead><tr><th width="150">Action</th><th width="150">Time</th><th width="150">Tokens</th><th>Notes</th></tr></thead><tbody><tr><td>Initial State</td><td>0.0</td><td>3.0</td><td>New TokenBucket is initialized to max capacity (burst)</td></tr><tr><td>Request 1</td><td>0.5</td><td>2.0</td><td>First fill the TokenBucket, then remove a token. Because we are at max capacity, just subtract 1 token from 3</td></tr><tr><td>Request 2</td><td>0.8</td><td>1.3</td><td>Fill the TokenBucket to 2.3 (min(3, (2 + (.8 - .5) * 1.0)) = min(3, 2.3) = 2.3), then subtract 1</td></tr><tr><td>Request 3</td><td>0.9</td><td>0.4</td><td>Fill the TokenBucket to 1.4 (min(3, (1.3 + (.9 - .8) * 1.0)) = min(3, 1.4) = 1.4), then subtract 1</td></tr><tr><td>Request 4 </td><td>1.0</td><td>0.5</td><td>Fill the TokenBucket to 0.5 (<code>min(3, (.4 + (1.0 - .9) * 1.0)) = min(3, 0.5) = 0.5</code>). <strong>Ratelimit</strong> because we don't have enough tokens available</td></tr><tr><td>Request 5</td><td>1.4</td><td>0.9</td><td>Fill the TokenBucket to 0.9 (<code>min(3, (0.5 + (1.4 - 1.0) * 1.0)) = min(3, 0.9) = 0.9</code>). <strong>Ratelimit</strong> because we don't have enough tokens available</td></tr><tr><td>Request 6</td><td>1.8</td><td>0.3</td><td>Fill the TokenBucket to 1.3 (<code>min(3, (0.9 + (1.8 - 1.4) * 1.0)) = min(3, 1.3) = 1.3</code>), then remove 1</td></tr><tr><td>Request 7</td><td>5.0</td><td>2.0</td><td>Fill the TokenBucket to 3.0 (<code>min(3, (0.3 + (5.0 - 1.8) * 1.0)) = min(3, 3.5) = 3</code>) since we would "overflow" with our calculations. Then subtract 1 token</td></tr></tbody></table>
