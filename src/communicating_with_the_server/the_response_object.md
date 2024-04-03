# The Response Object

Response objects contain the results of any components that were executed and/or any errors that may have occurred.

Response objects may have the following properties:

**`success`** (*always*)<br>
If this is true, you were successful in posting to the gateway, and should have a result object.

**`app_id`**<br>
The App ID that was used in your 'request object'.

**`error`** (*if success is false*)<br>
This will be an object with 2 properties: code and message. These objects contain information about anything that may have gone wrong.

**`api_version`** (*if success is false*)<br>
If there was a problem, the server will let you know what version it is at in case you've hit a deprecation issue.

**`result`** (*if success is true*)<br>
This will be a 'result object'(See 'The Result Object' below) or an array of multiple result objects if you used an array as your request object's 'call' property.

**`echo`**<br>
If your 'request object' had an echo value, this will be exactly the same.

**`debug`**<br>
If your 'input object' had debug set to true, this object will contain an '`exec_time`' value indicating how long it took the component to run, and a 'request' value containing a copy of the 'request object' you posted.

In our example, the success property of is true, and we have a [Result Object](./the_result_object.md)