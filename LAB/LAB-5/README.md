# Configuring VLANs and Trunking

## Trunking 
Trunking is a network configuration technique used in computer networking to allow multiple VLANs to share the same physical network link between switches. It enables the transmission of traffic from multiple VLANs over a single link, thus optimizing network bandwidth utilization. Trunking protocols, such as IEEE 802.1Q or ISL (Inter-Switch Link), add VLAN information to Ethernet frames, allowing switches to distinguish between different VLANs and forward traffic accordingly. Trunking is commonly used in environments where VLAN segmentation is required to segregate traffic for security, performance, or organizational purposes.
#
![image](https://github.com/Rohail30/CNDC/assets/96627590/636e3918-de6b-4bce-b6af-22149acbc50d)
#
![image](https://github.com/Rohail30/CNDC/assets/96627590/839570b7-ee88-485e-8a44-ce8063208e2b)
#

### Create VLANs on the switches.
1. `S1(config)# vlan 10` - Create VLAN 10
2. `S1(config-vlan)# name Student` - Assign name "Student" to VLAN 10
3. `S1(config-vlan)# vlan 20` - Create VLAN 20
4. `S1(config-vlan)# name Faculty` - Assign name "Faculty" to VLAN 20
5. `S1(config-vlan)# vlan 99` - Create VLAN 99
6. `S1(config-vlan)# name Management` - Assign name "Management" to VLAN 99
7. `S1(config-vlan)# end` - Exit VLAN configuration mode

### To see the VLANs
`S1# show vlan`

![image](https://github.com/Rohail30/CNDC/assets/96627590/f7bf3cd8-0427-4468-98be-6abfae6c3e9e)

### Assign VLANs to the correct switch interfaces.
#### 1. Assign PC-A to the Student VLAN:
1. `S1(config)# interface f0/6` - Enter interface configuration mode for FastEthernet interface 0/6.
2. `S1(config-if)# switchport mode access` - Set the interface to access mode.
3. `S1(config-if)# switchport access vlan 10` - Assign VLAN 10 (Student) to the interface.
4. `S1(config-if)# exit` - Exit interface configuration mode.


#### 2. Move the switch IP address to VLAN 99:
1. `S1(config)# interface vlan 1` - Enter interface configuration mode for VLAN 1.
2. `S1(config-if)# no ip address` - Remove the IP address assigned to VLAN 1.
3. `S1(config-if)# interface vlan 99` - Enter interface configuration mode for VLAN 99.
4. `S1(config-if)# ip address 192.168.1.11 255.255.255.0` - Assign IP address 192.168.1.11 with subnet mask 255.255.255.0 to VLAN 99.
5. `S1(config-if)# end` - Exit configuration mode.

### Assign a VLAN to multiple interfaces.
#### On S1, assign interfaces F0/11 – 24 to VLAN 10.
1. `S1(config)# interface range f0/11-24` - Enter interface range configuration mode for FastEthernet interfaces 0/11 through 0/24.
2. `S1(config-if-range)# switchport mode access` - Set the interfaces to access mode.
3. `S1(config-if-range)# switchport access vlan 10` - Assign VLAN 10 to the interfaces.
4. `S1(config-if-range)# end` - Exit configuration mode.

### Remove a VLAN assignment from an interface.
#### Use the no switchport access vlan command to remove the VLAN 10 assignment to F0/24.
1. `S1(config)# interface f0/24` - Enter interface configuration mode for FastEthernet interface 0/24.
2. `S1(config-if)# no switchport access vlan` - Remove the VLAN assignment from the interface.
3. `S1(config-if)# end` - Exit configuration mode.

### Remove a VLAN ID from the VLAN database.
#### Add VLAN 30 to interface F0/24 without issuing the VLAN command.
1. `S1(config)# interface f0/24` - Enter interface configuration mode for FastEthernet interface 0/24.
2. `S1(config-if)# switchport access vlan 30` - Assign VLAN 30 to the interface.

#### Use the no vlan 30 command to remove VLAN 30 from the VLAN database.
1. `S1(config)# no vlan 30` - Remove VLAN 30 from the switch configuration.
2. `S1(config)# end` - Exit configuration mode.


### Use DTP to initiate trunking on F0/1.
#### Set F0/1 on S1 to negotiate trunk mode.
1. `S1(config)# interface f0/1` - Enter interface configuration mode for FastEthernet interface 0/1.
2. `S1(config-if)# switchport mode dynamic desirable` - Set the interface to dynamic desirable mode.

`S1# show interfaces trunk`

![image](https://github.com/Rohail30/CNDC/assets/96627590/dade1894-1581-4436-a378-397b962d16ec)

### Manually configure trunk interface F0/1.
The **switchport mode trunk** command is used to manually configure a port as a trunk. This command should be
issued on both ends of the link.
#### Change the switchport mode on interface F0/1 to force trunking. 
1. `S1(config)# interface f0/1` - Enter interface configuration mode for FastEthernet interface 0/1.
2. `S1(config-if)# switchport mode trunk` - Set the interface to trunk mode.

#### Issue the show interfaces trunk command to view the trunk mode. Notice that the mode changed from desirable to on.
`S2# show interfaces trunk`

![image](https://github.com/Rohail30/CNDC/assets/96627590/87ddf472-05a9-473e-9f5e-4e6b9115cc19)

### Determine if the VLAN database exists.
`S1# show flash` - Display information about the flash memory on switch S1.

![Screenshot 2024-03-18 024355](https://github.com/Rohail30/CNDC/assets/96627590/5abb03f5-181b-4759-90ba-a9e2674550c5)

**Note:** If there is a vlan.dat file located in flash, then the VLAN database does not contain its default settings.

### Delete the VLAN database.
1. `S1# delete vlan.dat` - Delete the VLAN database file.
   
![image](https://github.com/Rohail30/CNDC/assets/96627590/08b6aeea-e3f7-42e6-afb7-c3fcec324bf9)
