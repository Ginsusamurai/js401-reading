# OAuth

## OAuth 2.0

- `an open standard for access delegation`
  - easier way to grant access without give the application your password
- when using this, it is treating your login as you, even though you are just pressing a button

## how does it work?

1. app gives a 'Login Using X' window 
2. user agrees to this
3. remote service(like google) contacts the application with a one-time-use `Code`
4. the app calls back to a special address with the `Code` to get a `Token`
5. with the token the app will the be able to contact the remote service

<token IS the user>

### Access Code

- <a> tag with some specific info on it
  - `response_type=code` your server wants an auth code
  - `client_id=<your client id>` tells the auth server which app the user is granting access to
  - `redirect_uri=<your url>` tells the auth server which endpoint to redirect to
  - `scope=<list of scopes>` what the user will be able to do
  - `state=<more stuff>` place to store info

### Access Token

- use the `code` to go to a redirect, then exchange the `code` for a `token` with some more info
  - `grant_type=authorization_code`
  - `code=<code received>`
  - `redirect_uri=redirecturi` must be same as what client provided
  - `client_id=<your client id>` telss the auth server which app is making the request
  - `client_secret=<your secret>` authenticates the app making the request is the same as the app registered with the `client_id`


### More resources

#### read

- [OAuth2 simplified](https://aaronparecki.com/oauth-2-simplified/)

#### Videos

- [what is OAuth really all about?](https://www.youtube.com/watch?v=t4-416mg6iU)

#### More things

- [OAuth wiki](https://en.wikipedia.org/wiki/OAuth)
- [build a node api with oauth](https://developer.okta.com/blog/2018/08/21/build-secure-rest-api-with-node)


![Bookmark in study](https://freshome.com/wp-content/uploads/2014/08/30-Classic-Home-Library-Design-Ideas-13.jpg)
