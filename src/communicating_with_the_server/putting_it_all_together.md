# Putting it all together

Earlier, we made a test POST using the `Gateway.getDatetime` component. Let's break that down using what we now know.

The execute object for our post looks like this:

```json
{
    "component": "Gateway.getDatetime",
    "parameters": {},
    "echo": "Hello World!"
}
```

*We have defined the component we want to call (`Gateway.getDatetime`), and added an echo just because we can. This component does not require any parameters, so we could have left that property out if we wanted.*

We then wrap the execute object inside a request object, and end up with this:

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
Our request object is using the handy 'test' `app_id`, and running in debug mode using `debug`.

Finally, we POST a value named 'request' to the gateway, using our JSON-encoded **input object** as the value.

