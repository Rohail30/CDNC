## Dynamic Host Configuration Protocol (DHCP)
DHCP (Dynamic Host Configuration Protocol) automates the assignment of IP addresses and network settings to devices on a network, simplifying network administration and ensuring efficient use of IP addresses.

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
