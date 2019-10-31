---
title: Revoke a client certificate
type: Tutorials
---

After you have established a secure connection with Compass, you can revoke a client certificate generated for your Application. Revocation prevents a certificate from being [renewed](08-02-maintain-secure-connection-with-compass.md). A revoked certificate, however, continues to be valid until it expires.

## Prerequisites

- Established secure connection with Compass

> **NOTE**: To see how to establish a secure connection with Compass, see [this](08-01-establish-secure-connection-with-compass.md) document. To see how to maintain a secure connection with Compass, see [this](08-02-maintain-secure-connection-with-compass.md) document. 

<!--- TODO: link in the note above --->

## Revoke the client certificate 

To revoke a client certificate, send a request to the Certificate-Secured Connector URL using the client certificate. The Certificate-Secured Connector URL is the `certificateSecuredConnectorURL` obtained when establishing a secure connection with Compass. Pass the certificate you want to revoke and the key that matches this certificate in the call.

In the request body, send this GraphQL mutation to the Certificate-Secured Connector URL together with the certificate you want to revoke and the matching key:

```graphql
mutation { 
    result: revokeCertificate 
}
```

A successful call results in the certificate revocation. 
