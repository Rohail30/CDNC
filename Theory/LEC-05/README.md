# Ethernet LAN Switching

In networking, the Preamble and Start Frame Delimiter (SFD) are components of the Ethernet frame header used in wired communication. Here's what they are:

1. **Preamble**: The preamble is a sequence of bits (usually 8 bytes long) at the beginning of an Ethernet frame. Its purpose is to provide synchronization between the sender and receiver by allowing the receiver's clock to synchronize with the incoming bit stream. The preamble consists of alternating 1s and 0s, followed by a unique byte pattern (10101011), which signals the start of the frame.

2. **Start Frame Delimiter (SFD)**: The SFD immediately follows the preamble in an Ethernet frame. It is a fixed bit sequence (usually 1 byte long) that marks the end of the preamble and indicates the start of the frame's frame

![image](https://github.com/Rohail30/CNDC/assets/96627590/514797ab-6146-4454-a1a3-928627f77e5a)

## Ethernet Header Components

The Ethernet header is a fundamental part of the Ethernet frame, containing essential information for data transmission in Ethernet networks. Below are its components:

1. **Preamble**: 
   - Length: 7 bytes (56 bits)
   - Purpose: Synchronizes clocks between sender and receiver, precedes the frame's data, and alerts receiving devices of an incoming frame.

2. **Start of Frame Delimiter (SFD)**:
   - Length: 1 byte (8 bits)
   - Purpose: Marks the end of the preamble and the beginning of the frame's header.

3. **Destination MAC Address**:
   - Length: 6 bytes (48 bits)
   - Purpose: Specifies the MAC address of the destination device to which the frame is being sent.

4. **Source MAC Address**:
   - Length: 6 bytes (48 bits)
   - Purpose: Contains the MAC address of the sending device.

5. **EtherType/Length**:
   - Length: 2 bytes (16 bits)
   - Purpose: Indicates either the type of data encapsulated within the frame or the length of the data payload.
   - Depending on its value, if the value is less than or equal to 1500, it represents the length of the data payload.
   - If it is greater than or equal to 1536, it signifies the type of protocol used in the payload (e.g., IPv4, IPv6).

6. **Data Payload**:
   - Variable length
   - Purpose: Carries the actual data being transmitted, such as an IP packet or another higher-layer protocol frame.

7. **Frame Check Sequence (FCS)**:
   - Length: 4 bytes (32 bits)
   - Purpose: Contains a checksum value computed over the entire frame (excluding the preamble and SFD) to verify the frame's integrity.

These components together form the Ethernet header except FCS which is part of the trailer, facilitating data transmission and reception in Ethernet networks.

---

![image](https://github.com/Rohail30/CNDC/assets/96627590/16f3ed36-090d-452e-a4ab-c00159e5b212)

Ethernet frames have a minimum size requirement to ensure proper functioning of the network. This minimum size is necessary for collision detection and other network operations. Here's the breakdown:

- **Minimum Ethernet Frame Size**: The minimum size for an Ethernet frame, including the header, payload (packet), and trailer, is 64 bytes.

- **Header and Trailer Size**: The Ethernet header and trailer together typically occupy 18 bytes.

- **Minimum Payload Size**: To calculate the minimum payload size (packet size), we subtract the header and trailer size from the minimum frame size:
  ```plaintext
  Minimum Payload Size = Minimum Frame Size - Header and Trailer Size
                         = 64 bytes - 18 bytes
                         = 46 bytes
  ```

- **Padding**: If the payload (packet) size is less than the minimum payload size of 46 bytes, padding bytes are added to meet the minimum frame size requirement. For example, if a packet is 34 bytes, then 12 bytes of padding are added to reach the minimum payload size:
  ```plaintext
  Packet Size + Padding Size = Minimum Payload Size
  34 bytes + 12 bytes = 46 bytes
  ```

Padding ensures that Ethernet frames meet the minimum size requirement and maintain the integrity of network operations, including collision detection.

---

## MAC (Media Access Control)
A MAC (Media Access Control) address is a unique identifier assigned to a network interface controller (NIC) for communication within a network. It is a hardware address, typically expressed as a series of hexadecimal digits separated by colons or hyphens (e.g., 00:1A:2B:3C:4D:5E).

A MAC (Media Access Control) address is like a unique name given to each device that connects to a network, such as your computer, phone, or printer. It's made up of a series of numbers and letters, kind of like a digital fingerprint. This address helps devices on the network identify and talk to each other, sort of like how your name helps people know who you are. Each device has its own MAC address, so even if there are many devices on the same network, they can all be recognized separately.

The MAC address is typically represented as six groups of two hexadecimal digits separated by colons, dashes, or periods. For example: 

- XX:XX:XX:XX:XX:XX
- XX-XX-XX-XX-XX-XX
- XX.XX.XX.XX.XX.XX

Here, "XX" represents a hexadecimal digit, which means it can be any number from 0 to 9 or any letter from A to F.

The first half of a MAC address typically identifies the manufacturer of the network interface card (NIC) or device. This portion is called the OUI (Organizationally Unique Identifier). The OUI is assigned by the Institute of Electrical and Electronics Engineers (IEEE) to companies that produce network hardware.

## The Address Resolution Protocol (ARP) 
The Address Resolution Protocol (ARP) is a communication protocol used to map an IP address to a physical (MAC) address on a local network. Here's how ARP works:

1. **ARP Request**: When a device wants to communicate with another device on the same network, but it only knows the IP address of the destination, it sends out an ARP request broadcast packet. This packet contains the IP address of the target device that it wants to communicate with.

2. **ARP Reply**: Upon receiving the ARP request, the device that has the IP address specified in the request responds with an ARP reply packet. This packet contains its own MAC address, allowing the requesting device to update its ARP cache with the correct MAC address corresponding to the IP address it wants to communicate with.

In summary, ARP is used to dynamically discover the MAC address associated with a given IP address on a local network, enabling devices to communicate with each other at the data link layer.

### MAC address table in a switch 
The MAC address table in a switch is a database that associates MAC addresses with the port on which they were last seen. Here's how it works along with known and unknown unicast frames:

1. **Switch MAC Address Table**: When a switch receives a frame, it examines the source MAC address of the frame and adds an entry to its MAC address table that maps the MAC address to the incoming port. If the MAC address is already in the table but on a different port, the table entry is updated with the new port. This process allows the switch to learn which MAC addresses are reachable via which ports.

2. **Known Unicast Frame**: If a switch receives a unicast frame with a destination MAC address that is already in its MAC address table, it forwards the frame only to the port associated with that MAC address. This is called a known unicast frame because the switch knows the exact port to which the frame should be forwarded.

3. **Unknown Unicast Frame**: If a switch receives a unicast frame with a destination MAC address that is not in its MAC address table, it broadcasts the frame out of all ports except the port from which it was received. This is done in an attempt to reach the destination device since the switch doesn't have a specific port associated with the destination MAC address. This is called an unknown unicast frame because the switch doesn't know which port to forward the frame to based on the MAC address table.

### ARP Commands and terms

1. **View ARP Table**:
   - Windows, macOS, Linux: `arp -a`
  
2. **ARP Table Entries**:
   - `Internet Address` = IP address (Layer 3 address)
   - `Physical Address` = MAC address (Layer 2 address)

3. **ARP Table Entry Types**:
   - `Type static` = Default entry
   - `Type dynamic` = Learned via ARP
   
![image](https://github.com/Rohail30/CNDC/assets/96627590/65c37d58-9dd7-4d32-9141-4a7fb7924f30)

4. **Show MAC Address Table**
   - `SW1#show mac address-table`

![image](https://github.com/Rohail30/CNDC/assets/96627590/8016a232-3858-41ce-8705-b79c2a0010b9)


5. **Clear Dynamic MAC Address Table Entries**:
   - `clear mac address-table dynamic`
   - `clear mac address-table dynamic address [mac-address]`
   - `clear mac address-table dynamic interface [interface-id]`

These commands can be used to view and manage ARP table entries and clear dynamic MAC address table entries on network devices.
