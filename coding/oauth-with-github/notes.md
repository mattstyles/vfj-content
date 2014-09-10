# oauth-with-github
_notes_

oauth2 can be a little tricky to get your head round but it basically hinges around obtaining and then using an access token to interact with an api.

Basic auth is user:password based.

This article should be on using oauth2 with super agent and github.

http://developer.github.com/v3/oauth/#create-a-new-authorization

Dev docs at github are pretty good but obviously not specific to a language.

Once you are logged in you can check all of your authorisations at https://github.com/settings/applications.

There are a couple of different ways to access github via super agent with basic authorisation, this is the easiest:

```
request
	.get( 'https://api.github.com/user' )
  .auth( 'username', 'password' )
```

Go through some other ways of using auth, including setting headers (the brute force approach) and using query.

This will send a GET request to /user and retrieve the user information associated with the username and password.  Any public information, i.e. that which you can see without being logged in, can be got at without auth of any kind but getting user info requires some form of auth.

To do more interesting stuff we want to acquire an auth token, again, we can use basic authorisation to do this:

```
request
	.post( 'https://api.github.com/authorizations' )
	.auth( 'username', 'password' )
  .send( {} )
```

Creating an auth token requires a post to /authorizations, basic auth and a JSON hash in the body.  The access token will be in the response `res.body.token` along with other stuff.  It'll look like this:

```
{ id: 4179170,
  url: 'https://api.github.com/authorizations/4179170',
  app: 
   { name: 'GitHub API',
     url: 'http://developer.github.com/v3/oauth/#oauth-authorizations-api',
     client_id: '00000000000000000000' },
  token: '2e89429f1f9888d5573dc0be22e179a783394085',
  note: null,
  note_url: null,
  created_at: '2013-10-24T07:12:42Z',
  updated_at: '2013-10-24T07:12:42Z',
  scopes: [] }
```

Go through what each of those mean and do some examples on setting various different stuff.

Now visit the auth screen and see a shiny new token.  This is a personal access token, to create an authorised application there are a couple of additional steps.

First, in github, register a new application.  Set the url and notes and stuff, although we won't be using those yet.  Get the client ID and secret.

Now, grab a token using basic auth and pass through the id and secret:

```
request
  .post( 'https://api.github.com/authorizations' )
  .auth( 'mattstyles', 'Georgia11' )
  .send( { client_id: '61329e5155c33d7a09bb', client_secret: '5a0fbc0b9b9735a2e5b01e3c952cf0742df4ed7d'} )
```

This will register against the client_id (check github auth docs for what is required), send back a token and register it on github in authorised applications.  Now, keep the token and use it for all subsequent calls.

Go through web flow, using the callback.

Also go through a nice function that checks for a token, acquires one if necessary, authorises and gets some info from github.