# JavaScriptImplicitClient
Authenticate user with authentication providers Facebook, Google, Linkedin
Implicit Flow
The implicit grant type is used for mobile apps and web applications (i.e. applications that run in a web browser), where the client secret confidentiality is not guaranteed. The implicit grant type is also a redirection-based flow but the access token is given to the user-agent to forward to the application, so it may be exposed to the user and other applications on the user's device. Also, this flow does not authenticate the identity of the application, and relies on the redirect URI (that was registered with the service) to serve this purpose.

The implicit grant type does not support refresh tokens.

The implicit grant flow basically works as follows: the user is asked to authorize the application, then the authorization server passes the access token back to the user-agent, which passes it to the application. If you are curious about the details, read on.
Is used for browser-based (web) or mobile applications, where you can't secure client secret so yopu can't use it to obtain access token.

Request for access token:

GET //oauth.presenter.url/authorization?response_type=token&client_id=CLIENT_ID&redirect_uri=REDIRECT_URI&scope=email
[REQUIRED] response_type - since you request access token from Resource owner, you must tell you want an access token (not authorization code)
[REQUIRED] client_id - client ID (e.g. application) that requests for access token
[REQUIRED] redirect_uri - URL where to redirect in case of success or error
[OPTIONAL] scope - specify the scope of access request
Access token response

Redirect to redirect_uri

//redirect_uri/#access_token=AnlSCIWYbchsCc5sdc5ac4caca8a2&expires_in=3600&token_type=bearer
In case or error, redirects to:

//redirect_uri/#error=unauthorized_client&error_description=Client+is+not+found
