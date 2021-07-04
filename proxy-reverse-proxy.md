## Proxy

Proxies are used to hide the identities of clients from the server that they are trying to connect. 

A proxy takes a request intended to a server from a client and modifies it in a manner that to the server it seems that the request came from the proxy itself. This is done by modifying the origin IP address in a request to that of the proxy itself. Once the server sends the response, it is collected by the proxy and forwards it to the client. 

Other than anonymizing the clients, proxies can be used for following: 

* Cache common requests from its clients to speed up responses.
* Act as a web filter to block clients from accessing specific content.
* Privacy

In an organization, proxies sit close the client terminals and can be used to apply an organization wide policy for the users accessing the internet.


A *`VPN`* is a common example of a proxy. But more than a simple forward proxy, a VPN also establishes an encrypted connection between itself and the client.



## Reverse Proxy

Reverse proxies are functionally opposite of proxy. They hide the identity of the servers serving a given request.

A reverse proxy takse a request from a client, forwards it to one of the servers, and then sends the response back to the client as if the response is originating from the reverse proxy itself. So for the client the response seems to have come from the reverse proxy.

An example of a reverse proxy can be a *`Load Balancer`*, though functionally they can be a little different. An LB primarily concerns itself with forwarding the user request to a server with low load so that the user experience is consistent. It can also be used to create end to end sessions so that a returning user can be connected to the same server, in order to prevent user state.

Other functions of a reverse proxy can be:

* Dynamically scale the infrastructure of an organization by allowing addition/deletions of servers sitting behing the reverse proxy
* Be a SSL terminal in charge of decrypting requests and encrypting responses so that this overhead can be removed from the actual servers catering to the user request.