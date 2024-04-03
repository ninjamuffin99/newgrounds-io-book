# The Result Object

Result objects are the counterpart of execute objects. They contain information about what the component returned.

A result object will have the following properties:

**`component`** (*always*)<br>
This will be the name of the component that was called.

**`data`**<br>
The results from the component. This object will always have a 'success' value. If 'success' is true, it will also contain all of the expected properties associated with the component that was called. If 'success' is false, it will also have an 'error' object with 'code' and 'message' values. If the component was called in debug mode, there will also be a debug property.

In our example post, we received a successful result with a 'data' value of:

```json
"data": {
    "success": true,
    "datetime": "2016-07-29T16:33:55-04:00",
    "debug": true
}
```

We know it worked because '`success`' is true, and we received the expected '`datetime`' value!

Check the components list page for details on what each component will return in these 'data' objects.