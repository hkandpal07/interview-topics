# TCP/IP Addressing:

The TCP/IP config on a device has 3 parts:

1. An IP Address
2. A Subnet Mask
3. A default gateway

## Subnet Mask:

A subnet mask divides an IP in two parts: one that identifies the network and other one that identifies the host

An IP address is a 32 bit number divided into 4 octets.

For example: 192.168.123.124
Binary representation with Octets: 11000000.10101000.01111011.01111100

Since in TCP/IP we have no fixed rule that defines what part of IP address is that of host and what part is determining the network, we apply a subnet mask to determine the host and the network

IP   -> 192.168.123.124
Mask -> 255.255.255.0

To apply the Subnet mask to the IP we can take the binary representation of both. The bits in IP for which the corresponding bit in Submnet mask is 1 are identified as network address. Similarly, the bits in IP for which the corresponding bits in Subnet mask are 0 are identifies as the host address.

Taking Binary representation of IP and mask mentioned above:

IP      -> 11000000.10101000.01111011.01111100

Mask    -> 11111111.11111111.11111111.00000000

Network -> 11000000.10101000.01111011.00000000

Host    -> 00000000.00000000.00000000.01111100

In decimal representation:

Network -> 192.168.123.0
Host    -> 0.0.0.124

## Subnetting:

Depending upon the first octet and subnet mask used, IP address can be divided into 3 classes:

Class A  -> Subnet      -> 255.0.0.0
            First Octet -> 0-127
            Example     -> 10.52.36.11

Class B  -> Subnet      -> 255.255.0.0
            First Octet -> 128-191
            Example     -> 172.16.52.63

Class C  -> Subnet      -> 255.255.255.0
            First Octet -> 192-223
            Example     -> 192.168.123.124
