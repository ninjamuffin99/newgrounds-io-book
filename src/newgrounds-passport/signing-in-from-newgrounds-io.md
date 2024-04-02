# Signing in from Newgrounds.io

Newgrounds.io uses a special session ID to create a link between the end user and the server. A session ID can tell the server wich app is being used, and who the end user is. In order to make any calls that are not read-only, you will need a sesssion id, and the associated user will need to be signed in.

## Acquiring a Session ID

If you have a web-based game that will be running on Newgrounds.com, it will be hosted in an iframe and a valid session ID will be included in the URL as the request parameter 'ngio_session_id'. If you have this value, you can call `App.checkSession` to verify the user.

For all other cases, or if the Newgrounds user is not logged in, you can use the `App.startSession` component.

Having a session ID is not a guarantee that the user has signed in, so you will need to verify it.

## Verifying a Session

Both `App.startSession` and `App.checkSession` will return a session object. This object contains a few parameters:

- `id` - The Session ID
- `user` - A user Object (if the user is signed in)
- `remember` - Will be set to true if the user wants you to remember this session.
- `passport_url` - A web address you can open if the user is not logged in.

The primary property you'll want to check in the session object is 'user'. If that value is null, your end-user needs to sign in still. If there IS a valid user object, you can skip the next step.

_**Note**: `App.startSession` will always create a NEW session. Once you have a session, use App.checkSession to see if a user has logged in!_

## Gettin the User Logged In

Using the address in the session's 'passport_url' property, open a new browser window. The user will be asked to sign in or create a new account.

While you user is doing this, make a call to `App.checkSession` every 5 seconds or so (hitting the API too fast could trigger our DDOS protection and block your app). If they complete their login, you will eventually get a valid 'user' object in the session result. If they cancel the login, you will get an error in the return. Either way, you will know they have completed some action from the browser window you sent them to.

It is good practice to also include a 'cancel login' button in your game. If a user clicks that, you can call `App.endSession` to make sure their session gets cleared out on the server right away.

## Remembering Sessions

When you get a valid user session, always check the 'remember' property. Typical sessions expire after a few hours, but if the user has checked this box, the session will remain valid for 30 days. If you save the session id locally, you can use it with `App.checkSession` right away, and your user will likely be logged in immediately with no need to open a browser window.

# Keeping Sessions Alive

ALL session expirations get reset whenever a call is made to the server. If a user session is remembered, it will remain valid indefinitely as long as the session is used at least once every 30 days.

All other sessions could expire while the user is playing your game if you do not make any calls to the server for a long period of time. You should call `Gateway.ping` once every 5 minutes or so to prevent this from happening.

# Logging Out

You should always provide a way for users to log out of Newgrounds Passport. This is done by simply calling the `App.endSession` component.

