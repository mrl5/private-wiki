# OAuth 2.0
- API access without an username and password
- Users and services can control clients
- OAuth 2 authentication requires HTTPS

## Grant types
- [Authorization Code](https://oauth.net/2/grant-types/authorization-code/)
- [Implicit](https://oauth.net/2/grant-types/implicit/)
- [Password](https://oauth.net/2/grant-types/password/)
- [Client Credentials](https://oauth.net/2/grant-types/client-credentials/)
- [Device Code](https://oauth.net/2/grant-types/device-code/)
- [Refresh Token](https://oauth.net/2/grant-types/refresh-token/)

### Grants
- Several grant types that impact flows
- Authorization code grant is most common
- Implicit is common in web apps and mobile apps
- Client credentials grant is useful in system-to-system comms

## OAuth 2.0 Authorization Code flow

![OAuth 2.0 Authorization Code](img/oauth-authorization-code-grant-flow.png)

(source: https://www.youtube.com/watch?v=H6MxsFMAoP8&t=07m29s)

## Token types
- Access token - the secret and often short-lived-token that identifies a user
- Refresh token - longer-lived token used to renew access token when it expires
- Scopes provide for right associated with the access token

## Scope
- Define the access a service can use
- Google example: scope says that some application can read contacts and emails but it CAN NOT read google docs

## See also
- [RFC 6749: The OAuth 2.0 Authorization Framework](https://tools.ietf.org/html/rfc6749)
- [RFC 6819: OAuth 2.0 Threat Model and Security Considerations](https://tools.ietf.org/html/rfc6819)
