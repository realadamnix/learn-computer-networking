
# Questions

## What is a default Gateway?

## How is a default gateway is configured?

## What is trunking?

Trunking is a technique used in computer networking to enable the transmission of multiple VLANs (Virtual Local Area Networks) over a single physical link. By using trunking, it's possible to connect two LANs (Local Area Networks) together while preserving VLAN information, allowing devices on one LAN to communicate with devices on the other LAN as if they were part of the same network.

## How to LAN's connect with trunking?

Here's how two LANs can connect via trunking:

Configure Trunk Ports: On the switches connecting the two LANs, you'll need to configure the ports that will carry the trunk traffic. These ports need to be configured as trunk ports to allow for the transmission of multiple VLANs. Depending on the switch model and operating system, the commands to configure trunk ports may vary, but typically you would use a command like switchport mode trunk.

Specify Allowed VLANs: Once the trunk ports are configured, you'll need to specify which VLANs are allowed to traverse the trunk link. This is done by configuring the trunk ports to allow specific VLANs using the switchport trunk allowed vlan command. By default, all VLANs are allowed on a trunk, but you can restrict this to only the VLANs necessary for communication between the two LANs.

Connect the Trunk Ports: Physically connect the trunk ports on the switches that are connecting the two LANs. This can be done using Ethernet cables, typically Cat5e or Cat6 cables, depending on the distance and speed requirements of the network.

Configure VLAN Interfaces: If the LANs are using different VLANs for segmentation, you'll need to configure VLAN interfaces on each switch to route traffic between the VLANs. This involves assigning IP addresses to the VLAN interfaces and configuring routing protocols or static routes to enable communication between the VLANs.

Test Connectivity: Once the trunk ports are configured and connected, and VLAN interfaces are configured, you should test connectivity between devices on the two LANs to ensure that traffic is successfully traversing the trunk link and VLANs.

By following these steps, you can connect two LANs via trunking, enabling communication between devices on different VLANs while maintaining VLAN segregation and security. Trunking is commonly used in enterprise networks to connect different parts of the network together and facilitate communication between VLANs

## Explain the purpose of Trunking

Imagine I have a company that needs to implement Virtual LAN's and the universe splits in 2.  In universe A we implemented Trunking , In universe B we did not .  What happens to the company in each universe?

Breaking down the scenarios in both Universe A (where trunking is implemented) and Universe B (where trunking is not implemented) for a company that requires Virtual LANs (VLANs).

Universe A (Trunking Implemented):

1. Company Setup: The company has implemented VLANs within its network for segmentation and organization purposes. Different departments or groups may be assigned to separate VLANs to enhance network security and manage traffic more effectively.
2. Trunking Implementation: In Universe A, trunking is implemented. This means that switches connecting different parts of the network are configured to carry traffic for multiple VLANs over a single physical link.
3. Inter-VLAN Communication: With trunking in place, devices within the company can communicate seamlessly across VLANs. For example, a device in the Sales VLAN can communicate with a device in the Marketing VLAN as if they were on the same network, even though they are logically separated for security and management purposes.
4. Flexibility and Scalability: Trunking provides flexibility and scalability for the company's network. As the company grows or changes, VLANs can be easily added or modified without needing to reconfigure physical connections.
5. Efficient Use of Network Resources: Trunking helps optimize network resources by allowing multiple VLANs to share the same physical infrastructure, reducing the need for additional cabling and switches.

Universe B (Trunking Not Implemented):

1. Company Setup: Similar to Universe A, the company has implemented VLANs within its network for segmentation and organization purposes.
2. No Trunking Implementation: In Universe B, trunking is not implemented. This means that switches connecting different parts of the network are not configured to carry traffic for multiple VLANs over a single physical link.
3. Isolated VLANs: Without trunking, VLANs are isolated from each other. Devices within a VLAN can communicate with each other, but communication between devices in different VLANs is not possible without routing through a layer 3 device such as a router.
4. Inter-VLAN Communication Challenges: Inter-VLAN communication requires routing through a layer 3 device. This may introduce additional complexity and latency to the network, especially if there are many VLANs or frequent communication between VLANs.
5. Potential for Bottlenecks: Without trunking, each VLAN may require its own dedicated physical link between switches, leading to potential bottlenecks and inefficient use of network resources, especially in larger networks.
6. In summary, implementing trunking provides a more efficient and flexible solution for connecting VLANs within a network, allowing for seamless communication between devices across VLAN boundaries. Without trunking, VLANs are isolated from each other, and inter-VLAN communication requires routing through a layer 3 device, potentially introducing complexity and inefficiencies.

## How does a default gateway work/allow devices to be on multiple networks, with different configurations?

A default gateway plays a crucial role in allowing devices to communicate with other networks, including networks beyond their own local network or subnet. Let's break down how a default gateway works and how it enables devices to be on multiple networks with different configurations:

1. Definition of Default Gateway: The default gateway is the IP address of the router or layer 3 switch that serves as the exit point for traffic originating from devices on the local network. When a device needs to communicate with a device on another network (either a different subnet within the same organization or an external network like the internet), it forwards the traffic to the default gateway.
1. Routing Decisions: When a device wants to communicate with another device on a different network, it checks its routing table to determine the appropriate next hop for the traffic. If the destination IP address is not on the same subnet as the device itself, the device forwards the traffic to its default gateway.
1. Routing at the Default Gateway: Once the traffic reaches the default gateway, the router or layer 3 switch examines the destination IP address and makes routing decisions based on its own routing table. It determines the next hop for the traffic based on the destination network's IP address.
1. Inter-Network Communication: The default gateway enables devices on one network to communicate with devices on other networks. This allows for the creation of complex networks where devices can be on multiple networks (subnets) with different configurations.
1. VLANs and Subnets: In a network with VLANs and multiple subnets, each VLAN typically corresponds to a separate subnet. Devices within the same VLAN (and subnet) can communicate directly with each other without needing to go through the default gateway. However, if a device in one VLAN needs to communicate with a device in another VLAN (on a different subnet), it sends the traffic to the default gateway, which routes the traffic to the appropriate destination.
1. Configuring Default Gateway: Each device on the network needs to be configured with the IP address of the default gateway. This is typically done manually or through dynamic methods such as DHCP (Dynamic Host Configuration Protocol), where the default gateway is provided along with other network configuration parameters.

In summary, the default gateway facilitates communication between devices on different networks by serving as the exit point for traffic leaving the local network. It plays a crucial role in enabling devices to be on multiple networks with different configurations, allowing for inter-network communication within complex network environments.

![Network Example](<out/diagrams/network/Networking Example.png>)

## How IPv6 addressing works?


IPv6 addressing works similarly to IPv4 addressing in that it provides a way to uniquely identify devices on a network. However, IPv6 addresses are 128 bits long, compared to the 32-bit addresses used in IPv4. This vastly expands the address space, allowing for a practically unlimited number of unique addresses.

Here's how IPv6 addressing works:

1. Representation: IPv6 addresses are typically represented as eight groups of four hexadecimal digits separated by colons. For example, a typical 1. IPv6 address might look like 2001:0db8:85a3:0000:0000:8a2e:0370:7334.
2. Address Types: IPv6 defines several types of addresses, including:
   - Unicast: An address identifying a single interface on a network.
   - Multicast: An address used to send packets to multiple interfaces.
   - Anycast: An address that identifies multiple interfaces, with packets routed to the nearest interface.
3. Address Components: An IPv6 address has two main components:
   - Network Prefix: The leftmost part of the address, which identifies the network or subnet.
   - Interface Identifier: The rightmost part of the address, which identifies the specific interface on the network.
4. Prefix Length: Similar to IPv4 subnet masks, IPv6 addresses are often assigned with a prefix length, represented as a number after a slash (/). 1. For example, 2001:0db8:85a3::/64 indicates that the first 64 bits represent the network prefix. 
5. Address Allocation: IPv6 addresses are typically allocated in a hierarchical manner, with Internet Assigned Numbers Authority (IANA) assigning 1. address blocks to Regional Internet Registries (RIRs), who in turn allocate smaller blocks to Internet Service Providers (ISPs) and 1. organizations.
6. Link-Local Addresses: Every IPv6-enabled interface automatically generates a link-local address, which is used for communication on the local 1. network segment. Link-local addresses are prefixed with fe80::.
7. Stateless Address Autoconfiguration (SLAAC): IPv6 includes a mechanism called SLAAC, which allows devices to automatically configure their IPv6 1. addresses without the need for manual configuration or DHCP servers. Devices use information from router advertisements (RAs) to generate their 1. addresses.
   - IPv6 Address Types: IPv6 defines several types of addresses, including:
   - Global Unicast Addresses: Similar to public IPv4 addresses, these are routable on the Internet.
   - Unique Local Addresses (ULAs): Used for communication within a site or organization, similar to IPv4 private addresses.
   - Multicast Addresses: Used to send packets to multiple interfaces.
   - Anycast Addresses: Used to send packets to the nearest interface among a group of interfaces.

Overall, IPv6 addressing provides a larger address space, improved address allocation, and simplified address configuration compared to IPv4, helping to accommodate the growing number of devices connected to the Internet.

## How do domains work?

Domains, in the context of the internet, provide a hierarchical naming system for addressing resources, such as websites, servers, and other services. The Domain Name System (DNS) is the underlying technology that translates domain names into IP addresses, allowing users to access resources using human-readable names rather than numerical IP addresses. Here's how domains work:

1. Domain Names: A domain name is a human-readable label that represents a specific resource or organization on the internet. For example, "example.com" is a domain name. Domain names consist of multiple parts separated by dots, with the rightmost part indicating the top-level domain (TLD), such as .com, .org, or .net.
2. Domain Name System (DNS): The DNS is a distributed hierarchical system that translates domain names into IP addresses and vice versa. It consists of multiple DNS servers organized into a hierarchy, with each server responsible for a specific part of the domain namespace.
3. DNS Resolution: When a user enters a domain name (e.g., "example.com") into their web browser or other network application, the application needs to resolve the domain name to an IP address to establish a connection to the corresponding server. The DNS resolution process typically involves the following steps:
   - Local DNS Cache Lookup: The application first checks its local DNS cache to see if it has a recent record of the domain name's IP address. If a cached record is found, the resolution process ends here.
   - Recursive DNS Query: If there is no cached record, the application sends a DNS query to a recursive DNS resolver, typically provided by the user's Internet Service Provider (ISP) or configured manually. The recursive resolver is responsible for finding the IP address associated with the domain name.
   - Iterative DNS Resolution: If the recursive resolver does not have the IP address in its cache, it starts the resolution process by querying the root DNS servers, which provide information about the authoritative DNS servers for the top-level domains.
   - Authority DNS Server Query: The recursive resolver then queries the authoritative DNS server responsible for the top-level domain (e.g., .com) to obtain information about the domain's authoritative name servers.
   - Domain Name Resolution: Finally, the recursive resolver queries the authoritative name servers for the domain name to obtain the IP address associated with the domain. The authoritative name servers respond with the IP address, which is returned to the user's application.
4. Domain Registration: To use a domain name, an organization or individual must register it with a domain registrar, which is responsible for managing the registration process and maintaining the domain name in the central registry for the corresponding top-level domain. Domain registration involves providing contact information and paying a registration fee for the desired domain name.
5. Domain Name Hierarchy: Domains are organized hierarchically, with each level representing a subdivision of the domain namespace. For example, "example.com" is a subdomain of the ".com" top-level domain. Subdomains can be further divided into additional subdomains, creating a hierarchical structure.

Overall, domains provide a human-readable naming system for addressing resources on the internet, and the DNS enables the translation of domain names into IP addresses, allowing users to access websites and other services using easy-to-remember names.

## What is the Difference between a collision domain to a broadcast domain?

A collision domain and a broadcast domain are two concepts in computer networking that define different aspects of how data is transmitted and managed within a network. Here's the difference between them:

1. **Collision Domain**:
   - **Definition**: A collision domain is a network segment where collisions can occur when two or more devices attempt to transmit data on the network at the same time. In Ethernet networks, collisions can occur in shared media environments, such as Ethernet hubs or repeaters, where multiple devices share the same physical communication medium (e.g., a single Ethernet cable or a shared segment of a network switch).
   - **Collision Detection**: In a collision domain, collision detection mechanisms are used to detect when collisions occur and take corrective action, such as backing off and retrying the transmission. Collision detection is a fundamental feature of CSMA/CD (Carrier Sense Multiple Access with Collision Detection), which is used in Ethernet networks.
   - **Impact on Performance**: Collisions can impact network performance by causing delays and retransmissions, particularly in heavily congested or high-traffic environments. As the number of devices sharing the same collision domain increases, the likelihood of collisions also increases, leading to decreased network efficiency.
   - **Examples**: Traditional Ethernet hubs and repeaters create single collision domains, where all devices connected to the hub or repeater share the same collision domain.

2. **Broadcast Domain**:
   - **Definition**: A broadcast domain is a logical division of a network where broadcast traffic is contained. Broadcast traffic consists of packets sent to all devices within the network segment, typically for purposes such as address resolution (ARP), network discovery, or service advertisement. Each broadcast domain defines the scope of broadcast traffic propagation within the network.
   - **Broadcast Propagation**: Devices within the same broadcast domain receive broadcast packets sent by other devices in the same domain. Broadcast packets are typically not forwarded beyond the boundaries of the broadcast domain, preventing unnecessary broadcast traffic from congesting other parts of the network.
   - **Impact on Network Traffic**: The size of the broadcast domain can impact network performance and efficiency, particularly in large networks. As the number of devices within a broadcast domain increases, so does the amount of broadcast traffic, potentially leading to network congestion and reduced performance.
   - **Examples**: LAN segments defined by routers or layer 3 switches create separate broadcast domains, as routers and layer 3 switches typically do not forward broadcast packets between different network segments.

In summary, a collision domain is a physical segment of a network where collisions can occur during data transmission, while a broadcast domain is a logical division of a network where broadcast traffic is contained. Understanding the distinction between collision domains and broadcast domains is important for designing and managing efficient and reliable networks.
