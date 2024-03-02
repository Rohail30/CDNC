**Switch Configuration:**

Configure Switch:

```bash
configure terminal
```

```bash
interface vlan 1
```

```bash
ip address 192.168.1.2 255.255.255.0
```

```bash
no shutdown
```

```bash
exit
```

```bash
line vty 0 4
```

```bash
password cisco
```

```bash
login
```

```bash
end
```

```bash
copy run start
```

**Router Configuration:**

```markdown
Configure Router:

```bash
enable
```

```bash
configure terminal
```

```bash
interface gigabitEthernet 0/0
```

```bash
ip address 192.168.1.2 255.255.255.0
```

```bash
no shutdown
```

```bash
exit
```

```bash
interface gigabitEthernet 0/1
```

```bash
ip address 172.16.5.1 255.255.0.0
```

```bash
no shutdown
```

```bash
end
```

```bash
copy run start
```

```bash
exit
```

**Default Gateway Configuration on Switches:**

```markdown
Configure Default Gateway on Switches:

```bash
enable
```

```bash
configure terminal
```

```bash
ip default-gateway 192.168.1.1
```

```bash
exit
```

```bash
copy run start
```

```markdown
enable
```

```bash
configure terminal
```

```bash
ip default-gateway 172.16.5.1
```

```bash
exit
```

```bash
copy run start
```
