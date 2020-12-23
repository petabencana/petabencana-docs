# Rate Limits

The Petabencana API employs rate limiting that cap the number of requests that can be made against an endpoint. If you exceed a rate limit, your request will be throttled and you will receive `HTTP 429 Too Many Requests responses from the API.`

You are encouraged to always stay within your allocated quota and implement retries in your code where applicable.

