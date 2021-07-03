# SSO and SAML

SSO is an authetication tool that allows users to login into multiple applications via one set of credentials.

## How does SSO work?

SSO works on the concept of federated identit, in which the identity attributes of a given users are shared across trusted but autonomous systems. As such, if the user is trusted by one system, they are automatically granted access to all the other systems that have a trusted relationship with that one system.

SSO systems use one of the following two protocols to assert a users identity between communicating systems:

1. OpenID Connect: Based on OAuth 2.0 and uses a JWT (JSON web token) to share credentials.

2. SAML: Security Assertion Markup Language. Uses XML SAML format for authentication, as opposed to JWT.


## SAML

SAML is an XML based protocol for exchanging authentication and authorization data between an Identity Provider (IdP) and a Service Provider(SP).


Once a SP is configured to authenticate via SAML, users accessing it will no longer be prompted for a username and password specific to SP. Instead the SP will reach out to the IdP for the user's identity and permissions, and then either grant or deny access to the user.

There are two types of flows for a SAML assertion, depending on where the user starts:

1. SP Initiatied: 

    * Users goes to the SP login page.
    * Instead of asking the user for creds, SP generates a SAML requests and redirects the users browser to SSO URL which belongs to the IdP.
    * The IdP authenticates the users (may involve MFA).
    * Once the IdP has authenticated the user, IdP sends a SAML response to the Authorization Consumer Service (ACS) url belonging to the SP.
    * ACS verifies the response, which includes attributes that identifies the user (NameID attribute), that the user has successfully authenticated into Okta, and that SAML response itself hasn't been alterted using a Digital Signature. That last attribute is encrypted and can be verified by SP using a Public Key that SP has in form of IdP's certificate.
    * Once the assertion (SAML response) is successfully parsed, the user will either be sent to the SP's default relay state (default page), or the page that they tried to access.

2. IdP Initiated:

    IdP initiated workflow comes into picture when the user directly logs into the IdPs app page and then access an app (SP) using the clicking it's icon (chiclet) in their IdP Apps page.

    The steps are the same from the step 3 in above workflow, so there's no SAML request, but a response


## Important fields in SAML response

1. NameID
2. Destination: Same as ACS
3. InResponseTo: Refers to the ID of SAML request for which the SAML response is meant
4. DigestMethod 
5. DigestValue
6. SignatureValue
7. X509Certificate
8. Conditions (`NotBefore` and `NotOnOrAfter`)
9. AudienceRestriction: Mostly has the ACS for which the response is meant
10. Default Relay State: The URL that users will be directed to after a successful authentication through SAML.