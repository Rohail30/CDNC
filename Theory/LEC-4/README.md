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

### 192.168.200.0
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

