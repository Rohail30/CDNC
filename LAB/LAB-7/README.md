## IPv4 Static and Default Routes

### Topology

![image](https://github.com/Rohail30/CNDC/assets/96627590/b3951298-2f28-4672-a112-c9868a83110d)

### Addressing table

![image](https://github.com/Rohail30/CNDC/assets/96627590/e03a35de-7eb4-456a-a82a-184dde27235d)

### Basic Device Settings

### Configure IP settings on the routers.

##### a. R1 G0/0 Configuration
1. `R1(config)# interface G 0/0` - Configure interface G0/0
2. `R1(config-if)# ip address 192.168.2.1 255.255.255.252` - Set IP address and subnet mask
3. `R1(config-if)# no shutdown` - Enable the interface
4. `R1(config-if)# exit` - Exit interface configuration mode

##### b. R1 G0/1 Configuration
1. `R1(config)# interface G 0/1` - Configure interface G0/1
2. `R1(config-if)# ip address 192.168.1.1 255.255.255.0` - Set IP address and subnet mask
3. `R1(config-if)# no shutdown` - Enable the interface
4. `R1(config-if)# exit` - Exit interface configuration mode

##### c. R2 G0/0 Configuration
1. `R2(config)# interface G 0/0` - Configure interface G0/0
2. `R2(config-if)# ip address 192.168.2.2 255.255.255.252` - Set IP address and subnet mask
3. `R2(config-if)# no shutdown` - Enable the interface
4. `R2(config-if)# exit` - Exit interface configuration mode

##### d. R2 G0/1 Configuration
1. `R2(config)# interface G 0/1` - Configure interface G0/1
2. `R2(config-if)# ip address 192.168.0.1 255.255.255.0` - Set IP address and subnet mask
3. `R2(config-if)# no shutdown` - Enable the interface
4. `R2(config-if)# exit` - Exit interface configuration mode

##### e. R2 G0/2 Configuration
1. `R2(config)# interface G 0/2` - Configure interface G0/2
2. `R2(config-if)# ip address 192.168.3.1 255.255.255.252` - Set IP address and subnet mask
3. `R2(config-if)# no shutdown` - Enable the interface
4. `R2(config-if)# exit` - Exit interface configuration mode

##### f. R3 G0/0 Configuration
1. `R3(config)# interface G 0/0` - Configure interface G0/0
2. `R3(config-if)# ip address 192.168.3.2 255.255.255.252` - Set IP address and subnet mask
3. `R3(config-if)# no shutdown` - Enable the interface
4. `R3(config-if)# exit` - Exit interface configuration mode

##### g. R3 G0/1 Configuration
1. `R3(config)# interface G 0/1` - Configure interface G0/1
2. `R3(config-if)# ip address 192.168.4.1 255.255.255.0` - Set IP address and subnet mask
3. `R3(config-if)# no shutdown` - Enable the interface
4. `R3(config-if)# exit` - Exit interface configuration mode

### Static Route Configurations

##### a. On Router 1
1. `R1(config) # ip route 192.168.0.0 255.255.255.0 192.168.2.2` - Configure static route on Router 1
2. `R1(config) # ip route 192.168.3.0 255.255.255.252 192.168.2.2` - Configure static route on Router 1
3. `R1(config) # ip route 192.168.4.0 255.255.255.0 192.168.2.2` - Configure static route on Router 1

##### b. On Router 2
1. `R2(config) # ip route 192.168.1.0 255.255.255.0 192.168.2.1` - Configure static route on Router 2
2. `R2(config) # ip route 192.168.4.0 255.255.255.0 192.168.3.2` - Configure static route on Router 2

##### c. On Router 3
1. `R3(config) # ip route 192.168.0.0 255.255.255.0 192.168.3.1` - Configure static route on Router 3
2. `R3(config) # ip route 192.168.2.0 255.255.255.252 192.168.3.1` - Configure static route on Router 3
3. `R3(config) # ip route 192.168.1.0 255.255.255.0 192.168.3.1` - Configure static route on Router 3

