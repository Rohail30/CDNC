# Router as DHCP server.

## Dynamic Host Configuration Protocol (DHCP)
DHCP (Dynamic Host Configuration Protocol) automates the assignment of IP addresses and network settings to devices on a network, simplifying network administration and ensuring efficient use of IP addresses.

![image](https://github.com/Rohail30/CNDC/assets/96627590/418ef3eb-fd47-49eb-adb9-1820597c5954)
![image](https://github.com/Rohail30/CNDC/assets/96627590/0983927d-d7b6-4795-90ec-a17b9d627e94)

### Configure S1 with an IP address and configure Virtual Terminal Line (VTY):
#### Switch

1. `S # configure terminal` - Enter Global Configuration Mode
2. `S (config)# interface vlan 1` - Access Interface Configuration Mode for VLAN 1
3. `S (config-if)# ip address 192.168.1.2 255.255.255.0` - Set IP address and subnet mask
4. `S (config-if)# no shutdown` - Enable the interface
5. `S (config-if)# exit` - Exit Interface Configuration Mode
6. `S (config)# ip default-gateway 192.168.1.1` - Configure the default gateway
7. `S (config)# exit` - Exit Global Configuration Mode
8. `S # copy run start` - Save the configuration to NVRAM
9. `S# exit` - Exit Configuration Mode

#### VTY
10. `S1(config)# line vty 0 15` - Access Line Configuration Mode for VTY lines
11. `S1(config-line)# password cisco` - Set VTY password
12. `S1(config-line)# login` - Enable login on the VTY lines
13. `S1(config-line)# end` - Exit Line Configuration Mode

### Configure Router’s (R) Interfaces with IP addresses.
#### Router
1. `R> enable` - Enter Privileged EXEC Mode
2. `R# configure terminal` - Enter Global Configuration Mode
3. `R(config)# interface gigabitEthernet 0/0` - Access Interface Configuration Mode for GigabitEthernet 0/0
4. `R(config-if)# ip address 192.168.1.1 255.255.255.0` - Set IP address and subnet mask
5. `R(config-if)# description connected to ACCOUNTS` - Assign a description to the interface
6. `R(config-if)# no shutdown` - Enable the interface
7. `R(config-if)# end` - Exit Interface Configuration Mode
8. `R# copy running-config startup-config` - Save the configuration to NVRAM
9. `R# exit` - Exit Privileged EXEC Mode

#### VTY
10. `R(config)# line vty 0 15` - Access Line Configuration Mode for VTY lines
11. `R(config-line)# password cisco` - Set VTY password
12. `R(config-line)# login` - Enable login on the VTY lines
13. `R(config-line)# end` - Exit Line Configuration Mode
14. `R# copy running-config startup-config` - Save the configuration to NVRAM
15. `R# exit` - Exit Privileged EXEC Mode

### Verify the IP address configuration on Router (R) and Switch (S)
Use the `show ip interface brief` command to display the IP address and status of the all the switch ports and
interfaces. Alternatively, you can also use the `show running-config` command.

### Configure a DHCPv4 on Router:
1. `R(config)# service dhcp` - Enable DHCP service on the router
2. `R(config)# ip dhcp pool ACCOUNTS` - Create a DHCP pool named "ACCOUNTS"
3. `R(dhcp-config)# network 192.168.1.0 255.255.255.0` - Define the network and subnet mask for the DHCP pool
4. `R(dhcp-config)# default-router 192.168.1.1` - Specify the default gateway for DHCP clients
5. `R(dhcp-config)# dns-server 8.8.8.8` - Specify the DNS server for DHCP clients
6. `R(dhcp-config)# exit` - Exit DHCP pool configuration mode
7. `R(config)# ip dhcp excluded-address 192.168.1.1 192.168.1.2` - Exclude IP addresses from DHCP assignment
8. `R(config)# exit` - Exit Global Configuration Mode
9. `R# write memory` - Save the configuration changes to NVRAM
10. `R# exit` - Exit Privileged EXEC Mode

#
## Setting up DHCP in Router

1. `Router> enable` - Enter Privileged EXEC Mode
2. `Router# configure terminal` - Enter Global Configuration Mode
3. `Router(config)# hostname R` - Set the hostname to R
4. `R(config)# interface g0/0` - Access Interface Configuration Mode for GigabitEthernet 0/0
5. `R(config-if)# ip address 192.168.1.1 255.255.255.0` - Set IP address and subnet mask for the interface
6. `R(config-if)# description connected to ACCOUNTS` - Add a description for the interface
7. `R(config-if)# no shutdown` - Enable the interface
8. `R(config-if)# end` - Exit Interface Configuration Mode
9. `Router# configure terminal` - Re-enter Global Configuration Mode
10. `R(config)# service dhcp` - Enable DHCP service on the router
11. `R(config)# ip dhcp pool ACCOUNTS` - Create a DHCP pool named ACCOUNTS
12. `Router(dhcp-config)# network 192.168.1.0 255.255.255.0` - Specify the network range for DHCP
13. `Router(dhcp-config)# default-router 192.168.1.1` - Set the default gateway for DHCP clients
14. `Router(dhcp-config)# dns-server 8.8.8.8` - Set the DNS server for DHCP clients
15. `Router(dhcp-config)# exit` - Exit DHCP pool configuration
16. `R(config)# ip dhcp excluded-address 192.168.1.1 192.168.1.2` - Exclude DHCP address range to avoid conflicts
17. `R(config)# exit` - Exit Global Configuration Mode
18. `Router# copy running-config startup-config` - Save the configuration changes
19. `Router# configure terminal` - Re-enter Global Configuration Mode
20. `R(config)# line vty 0 15` - Access Line Configuration Mode for VTY lines
21. `R(config-line)# password cisco` - Set a password for VTY lines
22. `R(config-line)# login` - Enable login on VTY lines
23. `R(config-line)# end` - Exit Line Configuration Mode
24. `Router# copy running-config startup-config` - Save the configuration changes
25. `Router# exit` - Exit Privileged EXEC Mode

## Setting up switch for DHCP
1. `Switch> enable` - Enter Privileged EXEC Mode
2. `Switch# configure terminal` - Enter Global Configuration Mode
3. `Switch(config)# hostname S1` - Set the hostname to S1
4. `S1(config)# interface vlan 1` - Access Interface Configuration Mode for VLAN 1
5. `S1(config-if)# ip address 192.168.1.2 255.255.255.0` - Set IP address and subnet mask for VLAN 1 interface
6. `S1(config-if)# no shutdown` - Enable the interface
7. `S1(config-if)# exit` - Exit Interface Configuration Mode
8. `S1(config)# ip default-gateway 192.168.1.1` - Set the default gateway
9. `S1(config)# line vty 0 15` - Access Line Configuration Mode for VTY lines
10. `S1(config-line)# password cisco` - Set a password for VTY lines
11. `S1(config-line)# login` - Enable login on VTY lines
12. `S1(config-line)# end` - Exit Line Configuration Mode
13. `S1# copy running-config` - Save the configuration changes
