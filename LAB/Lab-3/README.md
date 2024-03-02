Certainly! Here are the commands separated into markdown format:

**Switch Configuration:**
```markdown
Configure Switch:

```bash
S1# configure terminal
S1(config)# interface vlan 1
S1(config-if)# ip address 192.168.1.2 255.255.255.0
S1(config-if)# no shutdown
S1(config-if)# exit
S1(config)# line vty 0 4
S1(config-line)# password cisco
S1(config-line)# login
S1(config-line)# end
S1# copy run start
```

**Router Configuration:**
```markdown
Configure Router:

```bash
R> enable
R# configure terminal
R(config)# interface gigabitEthernet 0/0
R(config-if)# ip address 192.168.1.2 255.255.255.0
R(config-if)# no shutdown
R(config-if)# exit
R(config)# interface gigabitEthernet 0/1
R(config-if)# ip address 172.16.5.1 255.255.0.0
R(config-if)# no shutdown
R(config-if)# end
R# copy run start
R# exit
```

**Default Gateway Configuration on Switches:**
```markdown
Configure Default Gateway on Switches:

```bash
S1> enable
S1# configure terminal
S1(config)# ip default-gateway 192.168.1.1
S1(config)# exit
S1# copy run start
```

```markdown
S2> enable
S2# configure terminal
S2(config)# ip default-gateway 172.16.5.1
S2(config)# exit
S2# copy run start
```
