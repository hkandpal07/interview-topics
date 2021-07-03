# Different ways of accessing an API

While accessing an API, we have several ways of authenticating and authorizing our request with the API. Following are the 3 standard ways:

1. API Keys
2. HTTP Basic Auth
3. OAuth (Bearer)

## API Keys

API keys authenticate an application that is accessing an API, without referencing an actual user. So if our app is connecting to an API, we can make the request from the app to API using an API key, but that won't identify which user is using the app at the moment. 

This is helpful when we only want to connect to an API for statistical reasons, and help the API to rate limit incoming request by tying a limit on the number of calls that can be made from an API Key.

This method is easy to use but doesn not identify user of an application. Also it is difficul to keep the key a secret since they often end up in request logs, especially when used as a query param


## HTTP Basic Auth

This method provides a simple username and password style authentication for HTTP requests. To use this, you can send an Authorization header to a request with a base64 representation of username and password.

Although this method identifies the user of an Application that is connecting to an API, it's still not ideal as the user have no way of knowing what their credentials are being used for. Also since this is still a string passed to a request header, it can leak like the API key. Futhermore, it is not possible to use MFA in this method.

## Token Based Authentication using OAuth

In this method a token issued by a third party is generated using user's credentials and this token is used by the API to authenticate the Application making the API Call.

In such cases the API provider must publish an Authetication Server(AS) which issues the tokens. Once the user is logged in to the application, the application can point the user to the AS. The AS on it's part will Authenticate the user itself, and even use MFA to do so. The AS then generates a bearer token which can also be tied down to a specific access scope. When the user accepts this all, the generated token is sent to the application which the application can use to authenticate against the API. The generated tokens can also have TTL so that they expire after a given time.

This is also the structure of OAuth 2.0. API calls made using such method will have a Bearer token in the Authorization header.

Example: We make calls to api.cvent.com/auth/v1/access_token with user_stub and acct_id to get a Bearer token and then call APIs on api.cvent.com.

This method can also be used to generate bearers for applications themselves. (example: Toolbox) 