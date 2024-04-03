# The Request Object

As explained previously, the gateway script will always expect a request object. This object is a container that tells the API what application is calling it, who the end-user is (if known), and what components we want to execute.

A request object can have any, or all, of the following properties:

**`app_id`** (*required*)<br>
This is the App ID found on your Newgrounds.com Project/API Tools dashboard (see Getting Started page for details).

**`execute`**  (*required*)<br>
This can be either an 'execute object' (see 'The Execute Object' below) or an array of up-to-ten execute objects if you want to call multiple components in a single post. If you are using encryption, some components will expect a 'secure execute' object here (see 'Secure Executions' below).

**`session_id`**<br>
This is a session ID string associated with your end user. (See [Newgrounds Passport](../newgrounds-passport/newgrounds-passport.md) page for information on obtaining session IDs).

**`debug`**<br>
Set this boolean to true to operate in debug mode (responses will contain more data, some features will only simulate posting).

**`echo`**<br>
You can set this to ANY value, and it will be returned, verbatim, in the server response.
