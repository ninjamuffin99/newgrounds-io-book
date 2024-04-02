# Multitasking

To help keep your games snappy, you can call up to 10 components in a single post. This is done by using an array as the `execute` value in your 'request object'.

Let's look at two separate calls, and what they return:

Calling `Gateway.getVersion` with...

```json
{
    "app_id": "test",
    "call": {
        "component": "Gateway.getVersion"
    }
}
```
...returns
```json
{
    "success": true,
    "app_id": "test",
    "result": {
        "component": "Gateway.getVersion",
        "data": {
            "success": true,
            "version": "3.0.0"
        }
    }
}
```

And calling `Gateway.getDatetime` with...
```json
{
    "app_id": "test",
    "call": {
        "component": "Gateway.getDatetime"
    }
}
```

...returns

```json
{
    "success": true,
    "app_id": "test",
    "result": {
        "component": "Gateway.getDatetime",
        "data": {
            "success": true,
            "datetime": "2016-07-29T17:37:24-04:00"
        }
    }
}
```
In both examples, the 'execute' property and corresponding `result` property are flat objects.

By using an array in the 'call' property (to call BOTH components) like so...
```json
{
    "app_id": "test",
    "execute": [
        {
            "component": "Gateway.getVersion"
        },{
            "component": "Gateway.getDatetime"
        }
    ]
}
```

... we get an array back in the `result` property:

```json
{
    "success": true,
    "app_id": "test",
    "result": [
        {
            "component": "Gateway.getVersion",
            "data": {
                "success": true,
                "version": "3.0.0"
            }
        },
        {
            "component": "Gateway.getDatetime",
            "data": {
                "success": true,
                "datetime": "2016-07-29T17:37:24-04:00"
            }
        }
    ]
}
```
