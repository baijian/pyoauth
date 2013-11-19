## OAuth 2.0

[Specification](http://tools.ietf.org/html/rfc6749)

## Authorization Code Flow

The `Authorization Code` grant type is the most common workflow for OAuth2.0.
The follow is :

* Redirect to OAuth Server which show a login page for you to login in.

* Login successful and OAuth Server will redirect to the url which you register and also pass a code to you.

* You use client\_id and client\_secret which you register as well as the received code to exchange your access token with a POST request.

With the access token(along with its expiry time) you can get the data you want.

Authorization code grant的认证流程适合于有server端的应用授权


```
    |-------|   |-----|   |-----|   |-----|
    |Client |   |Third|   |Login|   |Token|
    |-------|   |-----|   |-----|   |-----|
        |          |         |         |
        |-appid-url-state--> |         |
        |          |         |         |
        |          |<--code--|         |
        |          |   state |         |
        |          |         |         |
        |          |---code----appid--->
        |          |         |         |
        |          |<----------token---|    
        |          |         |         |
        |<---------|         |         |
```

## Implicit Flow

The `Implicit` grant type is similar with `Authorization Code` grant type, the difference is that OAuth
Server will return the access token directly when you login then OAuth Server successfully.

Implicit grant的认证流程适合于通过客户端访问的应用授权

## Resource Owner Password Flow

Username and password are used directly as an authorization grant to obtain an access token.

## Client Credentials Flow

There is no redirect to the server, a POST request is done diretcly to the oauth2 server with
the client credentials, an access token is received.
