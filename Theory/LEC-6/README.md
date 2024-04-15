# Switch Interfaces

The **`show IP int brief`** command is a Cisco IOS command used to display a brief summary of the IPv4 configuration of all interfaces on a Cisco router or switch. It provides information such as the interface name, IP address, status (up/down), protocol (up/down), and method of assignment (manual or DHCP).

Here's what each column represents:

- **Interface**: Name of the interface.
- **IP Address**: IPv4 address assigned to the interface.
- **Status**: Indicates whether the interface is administratively up (connected) or down (disconnected).
- **Protocol**: Indicates whether the layer 3 protocol is operational (up) or not (down).
- **Method**: Indicates the method used to assign the IP address to the interface, such as manual configuration (configured) or dynamic assignment through DHCP (DHCP).

Overall, `show IP int brief` is a useful command for quickly checking the IPv4 configuration and status of all interfaces on a Cisco device.


![image](https://github.com/Rohail30/CNDC/assets/96627590/92150645-1bd7-4c80-9e2f-547439d6c130)

- Router interfaces have the shutdown command applied by default ==> will be in the administratively down/down state by default
- Switch interfaces do NOT have the 'shutdown' command applied by default ==> will be in the up/up state if connected to another device OR in the down/down state if not connected to another device

The **`show interface status`** command is a Cisco IOS command used to display a brief summary of the status of all interfaces on a Cisco router or switch. It provides information such as the interface name, status (up/down), VLAN, duplex mode (half or full), speed (10/100/1000 Mbps), and type (RJ45, SFP, etc.).

Here's what each column represents:

- **Port**: Name of the interface.
- **Status**: Indicates whether the interface is administratively up (connected) or down (disconnected).
- **VLAN**: VLAN assigned to the interface.
- **Duplex**: Indicates the duplex mode of the interface (half or full).
- **Speed**: Indicates the speed of the interface (10/100/1000 Mbps).
- **Type**: Indicates the type of interface connector (RJ45, SFP, etc.).

![image](https://github.com/Rohail30/CNDC/assets/96627590/5f14da7a-7355-4903-a6a9-37134167269f)

The **`interface range`** command in Cisco IOS allows you to configure multiple interfaces simultaneously by specifying a range of interfaces. In this case, `f0/5 - 12` refers to interfaces FastEthernet 0/5 through FastEthernet 0/12.

Here's what the command does:

- **interface range f0/5 - 12**: Enters interface configuration mode for a range of FastEthernet interfaces, from FastEthernet 0/5 to FastEthernet 0/12.

Once in interface configuration mode for this range of interfaces, you can then configure specific settings or parameters for all interfaces within the specified range.

![image](https://github.com/Rohail30/CNDC/assets/96627590/03d891bb-5eb9-4500-ac34-93cefe374b64)

## Collision
A collision in networking occurs when two devices on a shared network attempt to transmit data simultaneously. This simultaneous transmission results in a collision, causing the data sent by both devices to become corrupted and unintelligible. In Ethernet networks, collisions typically occur in half-duplex mode, where devices share the same communication medium and can either transmit or receive data at any given time, but not both simultaneously. Collisions are detected by the devices involved, which then implement collision avoidance mechanisms, such as the CSMA/CD (Carrier Sense Multiple Access with Collision Detection) protocol, to retransmit the data after a random backoff period.

### Collision and Broadcast Domains

- **Hub**: A hub operates at the physical layer (Layer 1) of the OSI model. It functions as a multi-port repeater, where all data received on one port is rebroadcast to all other ports. In a hub environment, all devices connected to the hub share the same collision domain, meaning that if one device transmits data, all other devices on the hub must wait, leading to potential collisions. However, a hub has only one broadcast domain, as it forwards broadcast traffic to all connected devices.

- **Switch/Bridge**: A switch operates at the data link layer (Layer 2) of the OSI model. Unlike a hub, a switch can create separate collision domains for each of its ports. This means that each device connected to a switch has its own dedicated bandwidth and does not need to contend with other devices for transmission. However, all devices connected to the same switch share a single broadcast domain, meaning that broadcast traffic is forwarded to all devices within the switch.

- **Router**: A router operates at the network layer (Layer 3) of the OSI model. It separates collision domains by default, as each of its interfaces represents a separate network segment, and data is typically not forwarded between interfaces unless explicitly configured to do so. Therefore, each interface on a router represents a separate collision domain. Additionally, routers also separate broadcast domains by default, as they do not forward broadcast traffic between interfaces by default, unless specifically configured to do so.

## So
**HUB:** 
- Single collision domain
- Single broadcast domain

**Switch/Bridge:** 
- Multiple collision domain
- Single broadcast domain
  
**Router:** 
- Multiple collision domain
- Multiple broadcast domain.

## CSMA/CD
**C**arrier **S**ense **M**ultiple **A**ccess with **C**ollision **D**etection Before sending frames, devices 'listen' to the collision domain until they detect that other devices are not sending. If a collision does occur, the device sends a jamming signal to inform the other devices that a collision happened. Each device will wait a random period of time before sending frames again. The process repeats.

## Auto-negotiation 
Auto-negotiation is a feature in Ethernet networking that allows devices to automatically negotiate and configure their connection settings, such as speed, duplex mode (full or half), and flow control. When two devices with auto-negotiation capabilities are connected, they exchange signaling messages to determine the optimal configuration for their connection.

- Interfaces that can run at different speeds (10/100 or 10/100/1000) have default settings of speed auto and duplex auto.
- Interfaces 'advertise' their capabilities to the neighboring device, and they negotiate the best speed and duplex settings they are both capable of.

![image](https://github.com/Rohail30/CNDC/assets/96627590/ec39f2ec-cbd3-4f3a-bbc8-cc865725cba1)

What if autonegotiation is disabled on the device connected to the switch

**SPEED:** The switch will try to sense the speed that the other device is operating at. If fails to sense the speed, it will use the slowest supported speed (ie. 10 Mbps on a 10/100/1000 interface)

**DUPLEX:** If the speed is 10 or 100 Mbps, the switch will use half duplex. If the speed is 1000 Mbps or greater, use full duplex.

![image](https://github.com/Rohail30/CNDC/assets/96627590/359f78d8-e48c-40af-a92a-f56395e264f6)

## Interface Errors

![image](https://github.com/Rohail30/CNDC/assets/96627590/c9635064-65d5-411e-beb6-036d4585306b)

- **Runts:** Frames that are smaller than the minimum frame size (64 bytes)
- **Giants:** Frames that are larger than the maximum frame size (1518 bytes)
- **CRC:** Frames that failed the CRC check (in the Ethernet FCS trailer)
- **Frame:** Frames that have an incorrect format (due to an error)
- **Input errors:** Total of various counters, such as the above four
- **Output errors:** Frames the switch tried to send, but failed due to an error


