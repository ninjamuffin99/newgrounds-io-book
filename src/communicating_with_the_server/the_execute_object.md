# The Execute Object

The execute object defines which component to run, and what parameters to call it with.

An execute object can have any, or all, of the following properties:

**`component`** (*required*)<br>
This is the name of the server component you want to call, ie Gateway.getDatetime.

**`parameters`**<br>
This is an object of parameters you want to call the component with. (See components list for details on what parameters each component expects.)

**`echo`**<br>
You can set this to ANY value, and it will be returned, verbatim, in the server response.


## Secure Executions

Some components can use encryption (see [Encryption](../newgrounds-io-encryption/newgrounds-io-encryption.md) help page) to obfuscate what gets sent over the network.

If you have encryption enabled on your Newgrounds.com Project/API Tools dashboard (this is enabled by default), you will need to convert 'call objects' to 'secure call' objects.

Secure calls have the following properties:

**`secure`** (*required*)<br>
This is a regular '`execute` object' (see above), that has been encoded into a JSON string, encrypted using a cipher, and encoded to a hexadecimal or base64 string, depending on your encryption settings (see Getting Started page for details).

*Note: You will only need to do this for components that indicate they support encryption, and only if you have encryption enabled on your Newgrounds.com Project/API Tools dashboard. Encryption is 100% optional if you are not using a pre-made library.*