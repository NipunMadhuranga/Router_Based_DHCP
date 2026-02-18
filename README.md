# Router_Based_DHCP
configuration of a Router to manage address allocation for  LAN segments using local DHCP pools

Project Overview: Router-Based DHCP
This lab demonstrates the configuration of a Router to manage address allocation for  LAN segments using local DHCP pools. The primary goal was to eliminate manual IP entry for end devices while ensuring full reachability between distinct networks.

1. Network Architecture & Addressing
The topology consists of two local area networks connected via a central router:

LAN 1 (Subnet 192.168.1.0/24): Connected to GigabitEthernet0/0, serving PC1, PC2, and Laptop1.

LAN 2 (Subnet 192.168.2.0/24): Connected to GigabitEthernet0/1, serving PC3, PC4, and Laptop2.

2. Router-as-DHCP-Server Configuration
Rather than using a dedicated external server, the router was configured to handle all IP requests locally.

Excluded Addresses: The router’s own interface IPs (192.168.1.1 and 192.168.2.1) were excluded from the DHCP pools to prevent IP address conflicts.

DHCP Pools: Two pools, "LAN1" and "LAN2," were created. Each pool automatically provides the following to the PCs:

Network Range: Specifies the subnet for the pool.

Default Gateway: Automatically assigns the router’s interface IP as the default-router.

DNS Server: Configured as 8.8.8.8 for external name resolution.

3. Verification & Connectivity Testing
Connectivity and configuration success were verified through multiple layers of testing:

DHCP Acknowledgement: Each PCs,Laptops successfully received the IP addresses from the router's DHCP service.

Ping Verification:

Local Ping: PC4 successfully pinged PC3 (192.168.2.3) with 0ms average latency.

Cross-Network Ping: PC4 successfully pinged PC1 (192.168.1.2) across the router, proving that inter-subnet routing is functional.

Key Outcomes
Scalability: The network can now grow without manual IP configuration for new devices.

Reachability: Successful data transfer was achieved across the gateway for both PC and Laptop devices.
