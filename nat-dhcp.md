## NAT

NAT (Network Address Translation) is used in routers to translate a set of IP addresses to another set of IP addresses.

Due to limited amount of public IPv4 addresses that can be assigned globally, network engineers developed the concept of private IP Addresses and NAT to convert the private addresses to public and vice versa.

Public IP address are publicly registered and can be used to connect to the internet. On the other hand a private IP address is not publicly registered and cannot be used to connect to the internet. Private IPs are handed out by your network router using DHCP (dynamic host configuration protocol).

If you want your device to go online it needs a public IP Address. But if each device is assigned a public IP address then it will quickly exhaust the IPv4 address space. So alternatively, a local network router, that has one public IP Address, assigns a private IP address to each device connected to it. When a datapacket is outbound to the internet from your device and reaches the router, it's private IP is translated to the public IP using NAT. Similarly, when a datapacket is inbound to your computer, the public IP will be translated to private to make the datapacket to reach the desired host


## DHCP:

DHCP (Dynamic Host Configuration Protocol) allows a router or a DHCP server to dynamically assign IP Address to the hosts connected to it. This removes the need to manually assign IPs to each device, and also prevents IP Conflict.

Using DHCP, the IP Address are handed out on a lease. When that lease expires, the host must request for a new IP from the DHCP server to remain connected. This allows the DHCP server to reclaim any IP addresses that have their lease expired but a renewal hasn't been requested, as would happen if a device has left the network. This prevents exhaustion of the scope of addresses allowed to a DHCP server.

Most routers in use concurrently have the DHCP service inbuilt in them to hand out IP Addresses using DHCP