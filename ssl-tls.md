## SSL and TLS

Protocols for establishing authenticated and encrypted links between networked computer. SSL was succeeded by TLS in 1999 but we still refer to it SSL, even though most certificates in use currently are TLS

When SSL is used in conjunction with HTTP, we call it HTTPS or secure HTTP

SSL has broadly two functions - Identification and Encryption

When an organization wishes their website to be secured using SSL/TLS, they need to contact a CA (Certificate Authority) and ask for a digital certificate to be issued. This along with the private key of a key pair will be stored on their servers. 

When a client (browser) attempts to make a connection with website, A SSL handshake will take place, so that an SSL session can be established. SSL handshake occurs after a TCP handshake has taken place to establish a TCP connection.

Things established during an SSL handshake for further client-server communication:

1. Specify which version of TLS to be used.
2. Decide which cipher suite (encryption algorithm - ECDSA or RSA) to be used
3. Authenticate the identity of the server using the public key and the SSL certificate
4. Generate session keys to use symmetric encryption after the handshake is complete 

Steps of SSL handshake:

1. 'Client hello': Client initiates handshake by sending "hello" message to server. This message will have the TLS versions and the encryption algorithms that the client supports, along with a string of random bytes called client random
2. 'Server Hello': Server replies to the client with a message providing the server's SSL certificate, servers chosen encryption algorithm, and server random.
3. Authentication: Client verifies server's SSL certificate with the CA that issues it and confirms that the server is who it says it is.
4. Premaster Secret: Client generates a pre-master secret, which is encrypted using the servers public key.
5. Server decrypts this premaster secret using it's private key
6. Session keys created: Both client and server will use client random, server random and premaster secret to create a common session key. Post this both client and server will send a 'finished' message encrypted with the session key
7. Secure symmetric encryption is achieved


## Levels of SSL certificates:

1. Domain Validated (DV) Certificates
2. Organization Validated (OV) Ceritficates
3. Extended Validation (EV) Certificates