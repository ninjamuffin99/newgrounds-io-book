# Handling the Server Response

In our example, at the top of the page, we posted a call to the `Gateway.getDatetime` component, and we should have seen the following result (or thereabouts):
```json
{
    "success": true,
    "app_id": "test",
    "result": {
        "echo": "Hello World!",
        "component": "Gateway.getDatetime",
        "data": {
            "success": true,
            "datetime": "2016-07-29T16:33:55-04:00",
            "debug": true
        }
    },
    "debug": {
        "exec_time": 0.002817,
        "request": {
            "app_id": "39685:NJ1KkPGb",
            "debug": true,
            "execute": {
                "component": "Gateway.getDatetime",
                "parameters": {},
                "echo": "Hello World!"
            }
        }
    }
}
```

This [JSON](https://www.json.org/) response is what we call a 'response object'.

