## Security Features on Switch

Sure, here's the explanation of each command along with the formatted Markdown file:

### **Securing Ports**

1. `Switch> enable` - Enter Privileged EXEC Mode: This command is used to enter the privileged EXEC mode, which provides access to all switch commands.
2. `Switch# configure terminal` - Enter Global Configuration Mode: This command is used to enter the global configuration mode, where you can configure global parameters for the switch.
3. `Switch(config)# interface f0/1` - Select Interface: This command is used to select the interface FastEthernet 0/1 for configuration.
4. `Switch(config-if)# switchport mode access` - Set Interface Mode: This command configures the interface to operate in access mode, which means it will only carry traffic for a single VLAN.
5. `Switch(config-if)# switchport port-security` - Enable Port Security: This command enables port security on the interface, allowing you to restrict access based on MAC addresses.
6. `Switch(config-if)# switchport port-security maximum 1` - Set the Maximum Number of MAC Addresses: This command sets the maximum number of MAC addresses allowed on the interface to 1.
7. `Switch(config-if)# switchport port-security mac-address sticky` - Learn MAC Addresses Dynamically: This command configures the interface to dynamically learn MAC addresses and add them to the port security table.
8. `Switch(config-if)# switchport port-security violation shutdown` - Action to Take When Violation Occurs: This command configures the interface to shut down if a port security violation occurs.
9. `Switch# show port-security interface f0/1` - Verify Port Security: This command is used to verify the port security configuration on interface FastEthernet 0/1.

### **Creating subinterfaces on Router**

1. `Router> enable` - Enter Privileged EXEC Mode: This command is used to enter the privileged EXEC mode on the router.
2. `Router# configure terminal` - Enter Global Configuration Mode: This command is used to enter the global configuration mode on the router.
3. `Router(config)# interface f0/0.1` - Create Subinterface: This command creates a subinterface named f0/0.1 on the router's FastEthernet 0/0 interface.
4. `Router(config-subif)# encapsulation dot1Q 10` - Assign VLAN ID: This command assigns VLAN ID 10 to the subinterface.
5. `Router(config-subif)# ip address 192.168.1.1 255.255.255.0` - Configure IP Address: This command configures the IP address and subnet mask for the subinterface.
6. `Router(config-subif)# exit` - Exit Subinterface Configuration Mode: This command exits the subinterface configuration mode and returns to the global configuration mode.

### **Creating VLANs and Trunking**

1. `Switch> enable` - Enter Privileged EXEC Mode: This command is used to enter the privileged EXEC mode on the switch.
2. `Switch# configure terminal` - Enter Global Configuration Mode: This command is used to enter the global configuration mode on the switch.
3. `Switch(config)# vlan 10` - Create VLAN: This command creates a VLAN with ID 10 on the switch.
4. `Switch(config-vlan)# name Students` - Set VLAN Name: This command assigns the name "Students" to VLAN 10 for easy identification.
5. `Switch(config)# interface f0/1` - Select Interface: This command selects interface FastEthernet 0/1 for configuration.
6. `Switch(config-if)# switchport mode trunk` - Set Interface Mode: This command configures the interface to operate in trunk mode, allowing it to carry traffic for multiple VLANs.
7. `Switch(config-if)# switchport trunk allowed vlan 10` - Allow VLANs on Trunk: This command specifies that VLAN 10 is allowed on the trunk link.

### **Configuring Access Mode**

1. `Switch> enable` - Enter Privileged EXEC Mode: This command is used to enter the privileged EXEC mode on the switch.
2. `Switch# configure terminal` - Enter Global Configuration Mode: This command is used to enter the global configuration mode on the switch.
3. `Switch(config)# interface f0/1` - Select Interface: This command selects interface FastEthernet 0/1 for configuration.
4. `Switch(config-if)# switchport mode access` - Set Interface Mode: This command configures the interface to operate in access mode, allowing it to carry traffic for a single VLAN.
5. `Switch(config-if)# switchport access vlan 10` - Assign VLAN: This command assigns VLAN 10 to the access port, specifying that traffic on this port belongs to VLAN 10.

[Click here to view the .md file](sandbox:/)
---

<summary><strong>Addressing Table</strong></summary>

![image](https://github.com/Rohail30/CNDC/assets/96627590/77bd422d-632c-4e60-9637-5438dc25414c)

<summary><strong>Topology</strong></summary>

![image](https://github.com/Rohail30/CNDC/assets/96627590/c588b692-61a3-4fc5-87da-c08ad1c81229)




