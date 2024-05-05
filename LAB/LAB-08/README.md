# Configuring Basic RIP
Router RIP (Routing Information Protocol) is a dynamic routing protocol used to exchange routing information between routers in computer networks. It broadcasts updates containing network topology and metrics, enabling routers to build and maintain routing tables for packet forwarding. RIP is known for its simplicity and ease of configuration but is limited in scalability due to its support for classful routing.

## topology
![image](https://github.com/Rohail30/CNDC/assets/96627590/bb7713f2-68d0-477b-8ba6-3270856b47fa)

## Addressing table
![image](https://github.com/Rohail30/CNDC/assets/96627590/9c5fdc10-bf60-4ffc-9f8e-d7f28b378db9)

## Basic Device Settings

### Configure IP settings on the routers.

#### R1 G0/0 configuration:
```bash
R1(config)# interface G0/0
R1(config-if)# ip address 192.168.2.1 255.255.255.252
R1(config-if)# no shutdown
R1(config-if)# exit
```

#### R1 G0/1 configuration:
```bash
R1(config)# interface G0/1
R1(config-if)# ip address 192.168.1.1 255.255.255.0
R1(config-if)# no shutdown
R1(config-if)# exit
```

#### R2 G0/0 configuration:
```bash
R2(config)# interface G0/0
R2(config-if)# ip address 192.168.2.2 255.255.255.252
R2(config-if)# no shutdown
R2(config-if)# exit
```

#### R2 G0/1 configuration:
```bash
R2(config)# interface G0/1
R2(config-if)# ip address 192.168.0.1 255.255.255.0
R2(config-if)# no shutdown
R2(config-if)# exit
```

#### R2 G0/2 configuration:
```bash
R2(config)# interface G0/2
R2(config-if)# ip address 192.168.3.1 255.255.255.252
R2(config-if)# no shutdown
R2(config-if)# exit
```

#### R3 G0/0 configuration:
```bash
R3(config)# interface G0/0
R3(config-if)# ip address 192.168.3.2 255.255.255.252
R3(config-if)# no shutdown
R3(config-if)# exit
```

#### R3 G0/1 configuration:
```bash
R3(config)# interface G0/1
R3(config-if)# ip address 192.168.4.1 255.255.255.0
R3(config-if)# no shutdown
R3(config-if)# exit
```

## Static Route Configurations

### On Router 1
```bash
R1(config)# router rip
R1(config)# ip route 192.168.2.0
R1(config)# ip route 192.168.1.0
```

### On Router 2
```bash
R2(config)# router rip
R2(config)# ip route 192.168.0.0
R2(config)# ip route 192.168.2.0
R2(config)# ip route 192.168.3.0
```

### On Router 3
```bash
R3(config)# router rip
R3(config)# ip route 192.168.3.0
R3(config)# ip route 192.168.4.0
```



No Router Rip (not in manual)
