# Request Spamming

Because many users of the Newgrounds.io API are novices, we have taken measures to handle things like bad loops, excessive packet sizes, and so on. If your app spams our gateway, it will be treated like any other DDOS attack, and the end user will be blocked.

For this reason, we strongly encourage you to only make API calls when they are necessary (you don't need to save your game, or post your current score on every single iteration of your game loop!).

