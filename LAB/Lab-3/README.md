### Switch Configuration

1. `configure terminal` - Enter Global Configuration Mode
2. `interface vlan 1` - Access Interface Configuration Mode for VLAN 1
3. `ip address 192.168.1.2 255.255.255.0` - Set IP address and subnet mask
4. `no shutdown` - Enable the interface
5. `exit` - Exit Interface Configuration Mode
6. `line vty 0 4` - Access Line Configuration Mode for VTY lines
7. `password cisco` - Set VTY password
8. `login` - Enable login on the VTY lines
9. `end` - Exit Global Configuration Mode
10. `copy run start` - Save the configuration to NVRAM

<br>

#
### Router Configuration

1. `enable` - Enter Privileged EXEC Mode
2. `configure terminal` - Enter Global Configuration Mode
3. `interface gigabitEthernet 0/0` - Access Interface Configuration Mode for GigabitEthernet 0/0
4. `ip address 192.168.1.2 255.255.255.0` - Set IP address and subnet mask
5. `no shutdown` - Enable the interface
6. `exit` - Exit Interface Configuration Mode
7. `interface gigabitEthernet 0/1` - Access Interface Configuration Mode for GigabitEthernet 0/1
8. `ip address 172.16.5.1 255.255.0.0` - Set IP address and subnet mask
9. `no shutdown` - Enable the interface
10. `end` - Exit Global Configuration Mode
11. `copy run start` - Save the configuration to NVRAM

<br>

#
### Default Gateway Configuration on Switches

1. `enable` - Enter Privileged EXEC Mode
2. `configure terminal` - Enter Global Configuration Mode
3. `ip default-gateway 192.168.1.1` - Set the default gateway
4. `exit` - Exit Global Configuration Mode
5. `copy run start` - Save the configuration to NVRAM

<br>

#
#### Telnet
Telnet is a network protocol for remote access to devices over a network. It allows users to control and manage devices from a remote location.
- `telnet 192.168.1.253` -initiates a Telnet session to the device with the IP address 192.168.1.253

<br>

#
#### table
<img src='./table.png'>

#
<img src='./lab3.png'>
