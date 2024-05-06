# Switching (VLANS, Trunk ports, Inter VLAN routing [ROAS])

- LAN stands for Local Area Network. It refers to a network that connects computers and other devices within a relatively small geographic area, such as a home, office, or campus. LANs typically use high-speed communication technologies like Ethernet or Wi-Fi to enable devices to communicate with each other and share resources such as files, printers, and internet connections. LANs are often used to facilitate collaboration, share resources, and enable communication between devices in close proximity.

- A more specific definition: A LAN is a single broadcast domain, including all devices in that broadcast domain.

### Broadcast Domain 
- A broadcast domain is the group of devices which will receive a broadcast frame (destination MAC FFFF.FFFF.FFFF) sent by any one of the members.

## VLAN
- **Performance:** Lots of unnecessary broadcast traffic can reduce network performance.

![image](https://github.com/Rohail30/CNDC/assets/96627590/2c803b95-c67d-4c72-9a85-3ec511591d03)

- **Security:** Even within the same office, you want to limit who has access to what. You can apply security policies on a router/firewall. Because this is one LAN, PCs can reach each other directly, without traffic passing through the router. So, even if you configure security policies, they won't have any effect.

### How VLAN works
1. **Switches Divide**: Switches split the network into different groups called VLANs. Each VLAN is like its own club where only certain devices can hang out.

2. **Ports for Each Club**: Switches assign ports to each VLAN. So, if your computer is plugged into Port 1 and it's in the Sales club, it can only talk to other devices in the Sales club.

3. **Tagging for Directions**: When a message comes into the switch from a device, the switch puts a little tag on it saying which VLAN it belongs to. This tag helps the switch know where to send the message.

4. **Sharing with Club Members**: Switches still let messages go to all devices in the same club. So, even though they're in different offices (VLANs), everyone in the same club can still talk to each other.

![image](https://github.com/Rohail30/CNDC/assets/96627590/d62eb612-daec-411a-ad34-74501419a728)

![image](https://github.com/Rohail30/CNDC/assets/96627590/7df38d18-a356-4b8d-8506-ff17fff980cd)

### Inter-VLAN Routing
Inter-VLAN routing is the process of allowing communication between different VLANs. Imagine each VLAN as a separate island, and inter-VLAN routing builds bridges between these islands so they can communicate with each other.

1. **Router as a Bridge**: Unlike switches, routers can understand and route traffic between different VLANs. They act as bridges connecting these VLANs.

2. **Routing Traffic**: When a device from one VLAN wants to communicate with a device in another VLAN, the traffic goes through the router. The router reads the destination VLAN of the packet and forwards it to the correct VLAN.

3. **Keeping Traffic Separate**: Even though the router connects the VLANs, it ensures that traffic from one VLAN doesn't leak into another unless specifically allowed. This helps maintain network security and privacy.

## Trunk
A trunk, in networking, is a type of connection between network devices, typically switches or routers, that can carry traffic for multiple VLANs simultaneously.

- In a small network with few VLANs, it is possible to use a separate interface for each VLAN when connecting switches to switches, and switches to routers.

- However, when the number of VLANs increases, this is not viable. It will result in wasted interfaces, and often routers won't have enough interfaces for each VLAN.

- You can use trunk ports to carry traffic from multiple VLANs over a single interface.

![image](https://github.com/Rohail30/CNDC/assets/96627590/1a136378-3cba-4f47-8a15-8b10c97f353e)














