## Navigating the two different networks.
### Assign a name to a switch.
1. `Switch# configure terminal` - Enter Global Configuration Mode.
2. `Switch(config)# hostname S1` - Set the hostname to S1.
3. `S1(config)# exit` - Exit Global Configuration Mode.
4. `S1#` - Return to Privileged EXEC Mode.

### Secure access to the console line.
1. `S1# configure terminal` - Enter Global Configuration Mode.
2. `S1(config)# line console 0` - Access the console line configuration mode.
3. `S1(config-line)# password letmein` - Set the console password to "letmein".
4. `S1(config-line)# login` - Enable login on the console line.
5. `S1(config-line)# exit` - Exit the console line configuration mode.
6. `S1(config)# exit` - Exit Global Configuration Mode.

### Secure privileged mode access.
1. `S1> enable` - Enter Privileged EXEC Mode.
2. `S1# configure terminal` - Enter Global Configuration Mode.
3. `S1(config)# enable password c1$c0` - Set the enable password to "c1$c0".
4. `S1(config)# exit` - Exit Global Configuration Mode.

### Configure an encrypted password to secure access to privileged mode.
1. `S1# config t` - Enter Global Configuration Mode.
2. `S1(config)# enable secret itsasecret` - Set the enable secret password to "itsasecret".
3. `S1(config)# exit` - Exit Global Configuration Mode.

**Note:** You can abbreviate `show running-config` as `S1# show run` to save Configuration Files to NVRAM

### Configure a message of the day (MOTD) banner.
1. `S1# config t` - Enter Global Configuration Mode.
2. `S1(config)# banner motd "This is a secure system. Authorized Access Only!"` - Set a message of the day (MOTD) banner.
3. `S1(config)# exit` - Exit Global Configuration Mode.

### Save Configuration Files to NVRAM
NVRAM stands for Non-Volatile Random Access Memory. It's a type of memory used in computers and networking devices that retains its stored data even when the power is turned off. In networking devices like routers and switches, NVRAM is often used to store the device's configuration files. This allows the device to retain its configuration settings even after a reboot or power loss, ensuring that the device operates consistently according to its configured settings.

1. `S1# copy running-config startup-config`
<p>Destination filename [startup-config]?[Enter]</p>
<p>Building configuration...</p>
<p>[OK]</p>

### Configure Switch with an IP address.
1. `S1(config)# interface vlan 1` - Enter Interface Configuration Mode for VLAN 1
2. `S1(config-if)# ip address 192.168.1.2 255.255.255.0` - Set IP address and subnet mask
3. `S1(config-if)# no shutdown` - Enable the VLAN interface
4. `S1(config-if)# exit` - Exit Interface Configuration Mode

#### Configure Virtual Terminal Line (VTY):
1. `S1(config)# line vty 0 4` - Access Line Configuration Mode for VTY lines
2. `S1(config-line)# password cisco` - Set VTY password
3. `S1(config-line)# login` - Enable login on the VTY lines
4. `S1(config-line)# end` - Exit Configuration Mode

### Configure Router’s (R) Interfaces with IP addresses.
1. `R> enable` - Enter Privileged EXEC Mode
2. `R # configure terminal` - Enter Global Configuration Mode
3. `R (config) # interface gigabitEthernet 0/0` - Access Interface Configuration Mode for GigabitEthernet 0/0
4. `R(config-if)# ip address 192.168.1.2 255.255.255.0` - Set IP address and subnet mask
5. `R(config-if)# no shutdown` - Enable the interface
6. `R(config-if)# exit` - Exit Interface Configuration Mode
7. `R (config) # interface gigabitEthernet 0/1` - Access Interface Configuration Mode for GigabitEthernet 0/1
8. `R(config-if)# ip address 172.16.5.1 255.255.0.0` - Set IP address and subnet mask
9. `R(config-if)# no shutdown` - Enable the interface
10. `R(config-if)# end` - Exit Global Configuration Mode
11. `R# copy run start` - Save the configuration to NVRAM
12. `R# exit` - Exit Privileged EXEC Mode

### Verify the IP address configuration on Router and Switch.
1. `show ip interface brief command` or `show running-config`

### Configure default gateway on Switch.
1. `S1 > enable` - Enter Privileged EXEC Mode
2. `S1 # configure terminal` - Enter Global Configuration Mode
3. `S1 (config)# ip default-gateway 192.168.1.1` - Configure the default gateway IP address
4. `S1 (config)# exit` - Exit Global Configuration Mode
5. `S1 # copy run start` - Save the configuration to NVRAM

#### Telnet
Telnet is a network protocol for remote access to devices over a network. It allows users to control and manage devices from a remote location.
- `telnet 192.168.1.253` -initiates a Telnet session to the device with the IP address 192.168.1.253

<br>

#
#### Table
<img src='./table.png'>

#
<img src='./lab3.png'>\

<br>

#
### Switch Configuration
1. `Switch> enable`- Enter Privileged EXEC Mode
2. `Switch# show running-config`- Show the current configuration
3. `Switch# configure terminal`- Enter Global Configuration Mode
4. `Switch(config)# hostname S1`- Set the hostname to S1
5. `S1(config)# line console 0`- Enter Console Line Configuration Mode
6. `S1(config-line)# password letmein`- Set the console password
7. `S1(config-line)# login`- Enable login on the console
8. `S1(config-line)# exit`- Exit Console Line Configuration Mode
9. `S1(config)# enable password c1$c0`- Set the privileged exec password (plaintext)
10. `S1(config)# enable secret itsasecret`- Set the privileged exec password (encrypted), overrides the enable password
11. `S1(config)# service password-encryption`- Encrypt all passwords (plaintext to encrypted)
12. `S1(config)# banner motd "Authorized Access Only!"`- Set the message of the day banner
13. `S1(config)# exit`- Exit Global Configuration Mode
14. `S1# copy running-config startup-config`- Save the configuration to NVRAM (Non-Volatile RAM)

<br>

#
### Router Configuration
1. `Router> enable`- Enter Privileged EXEC Mode
2. `Router# configure terminal`- Enter Global Configuration Mode
3. `Router(config)# interface gigabitEthernet 0/0` or `interface gigabitEthernet 0/1` - Access Interface Configuration Mode for GigabitEthernet 0/0 or GigabitEthernet 0/1- Enter Interface Configuration Mode
4. `Router(config-if)# ip address 192.168.1.1 255.255.255.0`- Set IP address and subnet mask
5. `Router(config-if)# no shutdown`- Enable the interface
6. `Router(config-if)# end`- Exit to Privileged EXEC Mode
7. `Router# copy running-config startup-config`
8. `Router# show ip interface brief`- Verify the configuration
9. `Router# exit`- Exit Interface Configuration Mode
10. `copy run start` - Save the configuration to NVRAM


<br>

#
### Default Gateway Configuration on Switches

1. `S1>enable` - Enter Privileged EXEC Mode
2. `S1#configure terminal` - Enter Global Configuration Mode
3. `S1(config)#ip default-gateway 192.168.1.1` - Set the default gateway
4. `S1(config)#exit` - Exit Global Configuration Mode
5. `S1#copy run start` - Save the configuration to NVRAM

<br>

#
### Setting up Virtual Terminal Lines (VTY)

We set up VTY (Virtual Terminal) lines to allow remote access to a device, such as a router or switch, over a network using protocols like Telnet or SSH. These lines define the number of concurrent connections allowed and specify authentication settings for users accessing the device remotely.

To set up VTY lines for remote access:

1. `S1> enable`
2. `S1# configure terminal`
3. `S1(config)# line vty 0 4` - Enter VTY Line Configuration Mode
4. `S1(config-line)# password c1$c0` - Set the VTY password
5. `S1(config-line)# login` - Enable login on the VTY lines

VTY lines are used to remotely connect to a switch using Telnet.





