# OSI Model

The OSI (Open Systems Interconnection) Model is a conceptual framework used to understand and standardize how different networking protocols and technologies interact within a networked system. It consists of seven layers, each with specific functions and responsibilities.

## Layers of the OSI Model

1. **Physical Layer:** Deals with the physical connection between devices and transmission of raw data bits over a communication channel.

2. **Data Link Layer:** Responsible for error detection and correction, as well as controlling the flow of data between adjacent network nodes.

3. **Network Layer:** Handles routing and forwarding of data packets across multiple networks, ensuring they reach their intended destination.

4. **Transport Layer:** Manages end-to-end communication between devices, ensuring data delivery, error detection, and flow control.

5. **Session Layer:** Establishes, maintains, and terminates connections between applications on different devices, facilitating communication sessions.

6. **Presentation Layer:** Translates data between the application layer and the network, ensuring compatibility and providing services such as data encryption and compression.

7. **Application Layer:** Provides interfaces for user applications to access network services, such as email, web browsing, and file transfer.

## Switch as a Layer 2 Device

Switch operates at the Data Link Layer (Layer 2) of the OSI model. It forwards data based on MAC addresses, facilitating communication within the same local network segment. Unlike routers, switches do not inspect IP addresses or perform routing between different subnets.


## IP Address Classes
In an IPv4 address, such as "192.168.1.100", the address is divided into four parts separated by periods. Each part is called an "octet" because it represents 8 bits of the address. The value of each octet ranges from 0 to 255. Here are the classes along with their ranges and examples:

**Class A:**
- **Range:** 1.0.0.0 to 126.255.255.255
- **Example:** 10.0.0.1, 10.0.0.2, 10.0.0.3

**Class B:**
- **Range:** 128.0.0.0 to 191.255.255.255
- **Example:** 172.16.0.1, 172.16.0.2, 172.16.0.3

**Class C:**
- **Range:** 192.0.0.0 to 223.255.255.255
- **Example:** 192.168.0.1, 192.168.0.2, 192.168.0.3

**Class D:**
- **Range:** 224.0.0.0 to 239.255.255.255
- **Example:** 224.0.0.1, 224.0.0.2, 224.0.0.3

 **Class E:**
  - **Range:** 240.0.0.0 to 255.255.255.254
  - **Example:** (Reserved for experimental purposes)

The first and last IP addresses in a subnet are typically reserved for the network address and broadcast address, respectively.

## Public and Private IP Address
1. **Public IP Address**: Identifies devices on the internet.
2. **Private IP Address**: Identifies devices within a local network.

## VLAN (Virtual Local Area Network)

A VLAN (Virtual Local Area Network) is a logical grouping of devices within a network, even if they are not physically located on the same network segment. VLANs are created to segment network traffic, improve network performance, and enhance security by logically dividing a single physical network into multiple isolated networks.

Devices within the same VLAN can communicate with each other as if they were connected to the same physical network, regardless of their physical location. VLANs are commonly used in enterprise networks to segregate traffic based on departments, functions, or security requirements.

### Real-Life Example of VLAN

In a university campus network, VLANs can be used to segregate network traffic based on different departments or functions. For example:

- **Faculty VLAN**: Devices used by faculty members, such as professors and administrative staff, can be assigned to a VLAN dedicated to faculty resources and communication.

- **Student VLAN**: Devices used by students, such as laptops and smartphones, can be assigned to a separate VLAN to access student-specific resources and services, such as online courses and academic databases.

- **Administrative VLAN**: Devices used by administrative offices, such as accounting and human resources, can be assigned to a VLAN that provides access to administrative applications and data.

- **Guest VLAN**: Visitors to the campus, such as guest lecturers or conference attendees, can be assigned to a VLAN that provides limited access to the internet while keeping them isolated from sensitive university resources.

These VLANs allow network administrators to control access to resources, manage bandwidth usage, and enhance security by segmenting network traffic based on the specific needs and requirements of each department or user group.

### Interface VLAN 1 Command

The `interface vlan 1` command configures a virtual LAN (VLAN) interface with the number 1. This command allows you to enter the configuration mode for VLAN 1, where you can assign IP addresses, enable or disable the interface, configure VLAN-specific settings, and manage the interface properties related to that VLAN.


## What is NAT?

NAT (Network Address Translation) is a networking technique that allows multiple devices within a local network to share a single public IP address for accessing resources on the internet. It works by translating private IP addresses used within the local network into a single public IP address when communicating with external networks. This allows devices within the local network to access the internet while hiding their individual IP addresses from external networks for security and privacy reasons.

## Example:

In a home network scenario:

- Laptop: 192.168.1.100
- Smartphone: 192.168.1.101
- Smart TV: 192.168.1.102

When any of these devices want to access a website on the internet, they send a request to the router. The router, which is connected to the internet and has a public IP address assigned by your Internet Service Provider (ISP), acts as a mediator.

Using NAT, the router translates the private IP address of each device into its own public IP address before forwarding the request to the website. For example, when the laptop (192.168.1.100) wants to access a website, the router translates its IP address to its public IP address (e.g., 203.0.113.1) before sending the request to the website.

This way, the website sees all requests coming from your router's public IP address, hiding the individual IP addresses of devices within your home network. This provides a layer of security and privacy for your devices while allowing them to access the internet using a single public IP address.

