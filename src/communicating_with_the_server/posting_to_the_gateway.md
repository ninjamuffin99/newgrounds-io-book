# Posting to the Gateway

All calls to the API are done by posting to the Newgrounds.io Gateway at <https://newgrounds.io/gateway_v3.php>. This 'gateway' processes any data you post to it, and responds with a JSON-encoded object.

Go ahead and [load the gateway](https://newgrounds.io/gateway_v3.php) in your browser, and you will immediately see how it responds with a JSON object containing an error about missing required request.

The gateway script expects a single query parameter named `request`, and expects to receive it using the POST method.

If you were to load <https://newgrounds.io/gateway_v3.php?request=test> (GET method) in your browser, you would see the same 'Missing required request' error as before. However, if we use the POST method, we get a different result:

Click here to test the POST method

We still get an error, but now it says 'Invalid JSON object in request'. This is because the request value is expected to be a JSON-encoded object, which we call the 'request object' (see below).

Let's do one more quick example, using a proper JSON-encoded request object:


```json
{
    "app_id": "test",
    "debug": true,
    "execute": {
        "component": "Gateway.getDatetime",
        "parameters": {},
        "echo": "Hello World!"
    }
}
```



The above example posts a valid request object, calling the Gateway.getTime component (see components list for more information on components).
