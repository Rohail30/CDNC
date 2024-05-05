# Configuring Single-Area OSPF
Single-Area OSPF(Open Shortest Path First), also known as OSPFv2, is a type of OSPF configuration where all routers and interfaces within an autonomous system (AS) belong to a single OSPF area. In this setup, OSPF routers exchange link-state advertisements (LSAs) only within the same area. Single-Area OSPF is typically used in smaller networks or where scalability is not a concern. It offers simplicity in configuration and management compared to multi-area OSPF deployments. However, it may not be suitable for large networks due to potential limitations in scalability and convergence times.

## Topology
![image](https://github.com/Rohail30/CNDC/assets/96627590/4eb9b176-3521-4efc-9b8e-c314de287c86)

## Addressing table
![image](https://github.com/Rohail30/CNDC/assets/96627590/4706a6ea-041c-4a13-afc4-ca08bc46eabb)

## Step 1: Configure OSPF on R1, R2, and R3

a. Enable OSPF on R1:
```bash
R1(config)# router ospf 1
```
Note: The OSPF process ID is local and has no meaning to other routers.

b. Configure network statements for R1:
```bash
R1(config-router)# network 192.168.1.0 0.0.0.255 area 0
R1(config-router)# network 192.168.0.0 0.0.0.3 area 0
```

c. Configure network statements for R2:
```bash
R2(config)# router ospf 1
R2(config-router)# network 192.168.2.0 0.0.0.63 area 0
R2(config-router)# network 192.168.0.0 0.0.0.3 area 0
R2(config-router)# network 192.168.0.4 0.0.0.3 area 0
```

d. Configure network statements for R3:
```bash
R3(config)# router ospf 1
R3(config-router)# network 192.168.3.0 0.0.0.31 area 0
R3(config-router)# network 192.168.0.4 0.0.0.3 area 0
```

## Step 2: Verify OSPF neighbors and routing information

a. Verify OSPF neighbors:
```bash
R1# show ip ospf neighbor
```

b. Verify routing table:
```bash
R1# show ip route
```

## Step 3: Verify OSPF protocol settings

Use the `show ip protocols` command to check OSPF configuration:
```bash
R1# show ip protocols
```

## Step 4: Verify OSPF process information

Check OSPF process ID, router ID, and area information:
```bash
R1# show ip ospf
```

## Step 5: Verify OSPF interface settings

a. Summary of OSPF-enabled interfaces:
```bash
R1# show ip ospf interface brief
```

b. Detailed list of OSPF-enabled interfaces:
```bash
R1# show ip ospf interface
```

## Step 6: Verify end-to-end connectivity

Ensure each PC can ping the other PCs in the topology.


