# Why Use Encryption?

TLDR: It makes it harder to cheat.

**Full explanation:**

As described in the '[Communicating with the Server](../communicating_with_the_server/posting_to_the_gateway.md)' page, Newgrounds.io is a network API that works by POSTing http requests to a gateway server.

In most modern browsers, you can right-click any page and see an 'Inspect' option. This will open a developer toolbar, and that will typically contain a 'Network' inspector.

Any user playing a web-based game can see EXACTLY what is being posted to the gateway script. And there are applications (like Fiddler 2) that can show network traffic from native games as well.

These tools make it incredibly easy for a user to copy something like a high score post, change some values, and post it from a simple HTML form.

By using encryption, the data that gets posted to the server is completely obfuscated and incredibly hard to edit.

