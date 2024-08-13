# Why?
- Passwords are weak in terms of security
- Third party gets broad access to RO
- Cannot revoke without revoking all third party's access
OAuth fixes it!
# How?
- Instead of credentials, access token and access attributes with defined scope is given to third parties
## Roles
- Resource Owner
- Resource Server
- Client
- Authorization Server
> Authorization server and resource server maybe the same
## The Flow
![[Screenshot 2024-08-13 at 5.55.06 PM.png]]
A. The client requests authorisation from resource owner (Auth server can be an intermediatory ie, Client -> auth server -> RO for requesting grant)
B. Authorization grant will be of four types will be returned

C. With Authorization grant, the client request access token to the Authorization server
D. Client get authenticated if the authorisation grant is valid

E. F. --- Has the token, can do something with resources ---

### Authorisation grant types
- authorisation code
- implicit
- resource owner password credentials
- and client credential
- Can be extended 
#### Authorisation Code
- client directs RO to Auth server
- Auth server provides the code and redirects to client
> The RO's creds are never shared with client, only to the auth server

The benefits
- Access token passed directly to the client, without intervention of RO, user agent at all. What do you mean?
#### Implicit
- The client is issues access token instead of authorisation token from
# References
```embed
title: "RFC 6749: The OAuth 2.0 Authorization Framework"
image: "https://static.ietf.org/dt/12.22.0/ietf/images/ietf-logo-card.png"
description: "The OAuth 2.0 authorization framework enables a third-party application to obtain limited access to an HTTP service, either on behalf of a resource owner by orchestrating an approval interaction between the resource owner and the HTTP service, or by allowing the third-party application to obtain access on its own behalf. This specification replaces and obsoletes the OAuth 1.0 protocol described in RFC 5849. [STANDARDS-TRACK]"
url: "https://datatracker.ietf.org/doc/html/rfc6749"
```
