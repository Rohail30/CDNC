# Networking

##### Breakdown of some terminologies using the example IP address 192.168.1.100 with a subnet mask of 255.255.255.0 (/24):

1. **IP Address**: An IP address is a unique numerical label assigned to each device connected to a computer network that uses the Internet Protocol for communication. It identifies the location of a device in the network. In our example, the IP address is `192.168.1.100`.

2. **Network IP**: The network IP address is the address used to identify the network to which a device belongs. It is obtained by setting all host bits to 0 in the subnet. For the example IP address `192.168.1.100` with a subnet mask of `255.255.255.0`, the network IP address is `192.168.1.0`.

3. **Usable Hosts**: Usable hosts are the IP addresses within a subnet that can be assigned to devices. They exclude the network address (which identifies the network) and the broadcast address (which is used to send data to all devices on the network). For the example subnet, the usable host addresses range from `192.168.1.1` to `192.168.1.254`.

4. **Broadcast IP**: The broadcast IP address is used to send data to all devices on a specific network. It is obtained by setting all host bits to 1 in the subnet. For the example subnet, the broadcast IP address is `192.168.1.255`.

5. **Network Portion**: The network portion of an IP address represents the part of the address that identifies the network. It is determined by the subnet mask. In our example, the network portion is `192.168.1`.

6. **Host Portion**: The host portion of an IP address represents the individual device within the network. It is determined by the subnet mask. In our example, the host portion is `.100`.

7. **Number of Zeros**: The number of zeros in the subnet mask indicates the number of bits reserved for the network portion of the IP address. In our example, the subnet mask `255.255.255.0` has `24` zeros, indicating that the first `24` bits represent the network portion.

8. **Number of Ones**: The number of ones in the subnet mask indicates the number of bits reserved for the host portion of the IP address. In our example, the subnet mask `255.255.255.0` has `8` ones, indicating that the last `8` bits represent the host portion.

9. **Subnet**: A subnet is a logical subdivision of an IP network. It allows a single network to be divided into multiple smaller networks for organizational or security purposes. Subnetting involves dividing the available IP addresses into smaller blocks to accommodate different network requirements. In our example, the subnet is defined by the network IP address `192.168.1.0` and the subnet mask `255.255.255.0`.

## Class tasks

### Formulae: 
- Total host = 2^(# of zeros) = 2^8 = 256
- Usable host = Total host - 2

### 192.168.200.0/24
- **IP Address in Binary:** 11000000.10101000.11001000.00000000
- **IP Address in Decimal:** 192.168.200.0
- **Class:** Class C
- **Subnet Mask in Binary:** 11111111.11111111.11111111.00000000
- **Subnet Mask in Decimal:** 255.255.255.0
- **Network IP:** 192.168.200.0
- **Usable Host Range:** 192.168.200.1 to 192.168.200.254
- **Broadcast IP:** 192.168.200.255

### 192.168.10.0/30
- **IP Address in Binary:** 11000000.10101000.00001010.00000000
- **IP Address in Decimal:** 192.168.10.0
- **Class:** Class C
- **Subnet Mask in Binary:** 11111111.11111111.11111111.11111100
- **Subnet Mask in Decimal:** 255.255.255.252
- **Network IP:** 192.168.10.0
- **Usable Host Range:** 192.168.10.1 to 192.168.10.2
- **Broadcast IP:** 192.168.10.3

### 172.16.0.0/16
- **IP Address in Binary:** 10101100.00010000.00000000.00000000
- **IP Address in Decimal:** 172.16.0.0
- **Class:** Class B
- **Subnet Mask in Binary:** 11111111.11111111.00000000.00000000
- **Subnet Mask in Decimal:** 255.255.0.0
- **Network IP:** 172.16.0.0
- **Usable Host Range:** 172.16.0.1 to 172.16.255.254
- **Broadcast IP:** 172.16.255.255

## LAN
### Local Area Network (LAN)

A local area network (LAN) is a network that connects computers and devices within a limited geographical area, such as a home, school, office building, or campus. LANs typically use wired or wireless connections to enable communication and resource sharing between devices, such as computers, printers, servers, and storage devices. They are commonly used for tasks like accessing the internet, sharing files and resources, and running applications within the local network. LANs are characterized by high-speed data transfer rates, low latency, and relatively low cost of implementation and maintenance compared to wide area networks (WANs).

### LAN Connected to the Internet

No, a LAN connected to the internet is typically not considered just a LAN but rather an interconnected network comprising both LAN and WAN (Wide Area Network) components. While the LAN portion refers to the local network within a limited geographical area, the WAN component encompasses the broader network infrastructure that facilitates internet connectivity. The connection between the LAN and the internet usually involves a router or gateway device that serves as the interface between the local network and the external internet.

## Network Topology
![Untitled Diagram drawio](https://github.com/Rohail30/CNDC/assets/96627590/7d3cf915-2906-4d2f-bf50-309be61934be)

## Identifying Number of Networks in a network topology
The number of networks in a network topology is determined by the number of routers present. Each router represents a boundary between different IP subnets, separating them into distinct network segments.The picture of network topology above shows 3 networks,

**Here is how:**

![Untitled Diagram drawio](https://github.com/Rohail30/CNDC/assets/96627590/3acb87b7-1721-4bbd-a882-5aee1482cd94)

## Subnetting and VLSM

**Subnetting** involves dividing a network into smaller subnetworks to improve performance, security, and manageability. It allows for efficient use of IP addresses by allocating them based on network requirements.

**Variable Length Subnet Masking (VLSM)** is a subnetting technique that enables the allocation of different-sized subnets, allowing for more efficient use of IP addresses within a network hierarchy.

## VLSM Task Example
### Apply subnetting on the below networks using 192.168.1.0/24 IP Address
![Untitled Diagram drawio](https://github.com/Rohail30/CNDC/assets/96627590/7d3cf915-2906-4d2f-bf50-309be61934be)

### Networks: 
There are 3 three networks, let's number them from left to right.
- **Network-1:** 1Router+1Switch+2PCs+NetworkIP+BroadcastIP
- **Network-2:** 2Routers+NetworkIP+BroadcastIP
- **Network-3:** 1Router+2witches+4PCs+NetworkIP+BroadcastIP

### Steps for Subnetting:

1. **Arrange Networks:** Organize the networks in descending order based on their size or number of devices. For example, list Network3 first, followed by Network1, and then Network2.

2. **Calculate Usable Hosts:** Determine the total number of devices (hosts) in each network. This includes computers, servers, printers, routers, switches, etc. Count all devices that require individual IP addresses. For instance, if Network3 has 7 devices, there are initially 7 usable hosts.

3. **Allocate Subnet Addresses:** Allocate enough subnet addresses to accommodate the required number of hosts. Use the formula 2^(n+2) where 'n' is the number of bits borrowed for subnetting. For example, if Network3 needs 7 usable hosts, allocate enough bits in the subnet mask to accommodate at least 14 hosts, which might require borrowing 4 bits (2^4 = 16, but 2 addresses are reserved for network address and broadcast address). So, for Network3, allocate a subnet with a subnet mask that can support 16 addresses, providing 7 usable hosts.

4. **Determine Subnet Mask:** Calculate the subnet mask based on the number of bits borrowed for subnetting. For example, if 4 bits are borrowed for Network3, the subnet mask would be 255.255.255.240 (/28 in CIDR notation).

5. **Assign Subnet Addresses:** Assign subnet addresses to each network according to their requirements. Ensure that each network has enough subnet addresses to accommodate the expected number of hosts. For example, if Network3 requires 14 usable hosts, assign a subnet address range with at least 16 addresses.

### Network-3:
- **Devices:** 1 Router + 2 Switches + 4 PCs + Network IP + Broadcast IP = 9 devices
- **Total host:** 2^4 = 16
- **Usable Hosts Required:** 16 - 2 (Network IP and Broadcast IP) = 14 usable hosts
- **Subnet Allocation:** We need to allocate enough subnet addresses to accommodate at least 7 usable hosts.
- **Subnet Mask:** Since we need 7 usable hosts, a subnet mask of /28 (255.255.255.240) will provide 16 total addresses (14 usable hosts).
- **Subnet Range:** 192.168.1.15/28
  - Network Address: 192.168.1.0
  - First Usable Host: 192.168.1.1 
  - Last Usable Host: 192.168.1.14 
  - Broadcast Address: 192.168.1.15

### Network-1:
- **Devices:** 1 Router + 1 Switches + 2 PCs + Network IP + Broadcast IP = 6 devices
- **Total host:**  2^3 = 8
- **Usable Hosts Required:** 8 - 2 (Network IP and Broadcast IP) = 6 usable hosts
- **Subnet Allocation:** We need to allocate enough subnet addresses to accommodate at least 4 usable hosts.
- **Subnet Mask:** Since we need 4 usable hosts, a subnet mask of /29 (255.255.255.248) will provide 8 total addresses (6 usable hosts).
- **Subnet Range:** 192.168.1.23/29
  - Network Address: 192.168.1.16
  - First Usable Host: 192.168.1.17 
  - Last Usable Host: 192.168.1.22 
  - Broadcast Address: 192.168.1.23
 
  ### Network-2:
- **Devices:** 2 Routers + Network IP + Broadcast IP = 4 devices
- **Total host:**  2^2 = 4
- **Usable Hosts Required:** 4 - 2 (Network IP and Broadcast IP) = 2 usable hosts
- **Subnet Allocation:** We need to allocate enough subnet addresses to accommodate at least 2 usable hosts.
- **Subnet Mask:** Since we need 2 usable hosts, a subnet mask of /30 (255.255.255.252) will provide 4 total addresses (2 usable hosts).
- **Subnet Range:** 192.168.1.31/30
  - Network Address: 192.168.1.24
  - First Usable Host: 192.168.1.25 
  - Last Usable Host: 192.168.1.26 
  - Broadcast Address: 192.168.1.27
 
**Tip!** The Network address will always be an even number and broadcast IP will always be an odd.

