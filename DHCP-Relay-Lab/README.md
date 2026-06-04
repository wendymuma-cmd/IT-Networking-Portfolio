# DHCP Relay Lab

## Overview
This lab demonstrates DHCP Relay (ip helper-address) configuration using Cisco Packet Tracer.

A centralized DHCP server located in the Server subnet provides IP addresses to hosts in different networks through a router configured with DHCP Relay.

## Network Topology

- Sales Network: 192.168.10.0/24
- HR Network: 192.168.20.0/24
- Server Network: 192.168.30.0/24

### Devices Used

- 1 Router
- 2 Switches
- 2 Sales PCs
- 1 HR PC
- 1 DHCP Server

## Router Configuration

```cisco
interface g0/0
 ip address 192.168.10.1 255.255.255.0
 ip helper-address 192.168.30.10

interface g0/1
 ip address 192.168.20.1 255.255.255.0
 ip helper-address 192.168.30.10

interface g0/2
 ip address 192.168.30.1 255.255.255.0
```

## DHCP Relay Explanation

DHCP requests are broadcast messages and cannot cross router boundaries.

The command:

```cisco
ip helper-address 192.168.30.10
```

was configured on the Sales and HR router interfaces to forward DHCP requests to the DHCP server located on the Server subnet.

This allowed clients in different networks to obtain IP addresses from a centralized DHCP server.

## DHCP Server Configuration

- IP Address: 192.168.30.10
- Network: 192.168.30.0/24
### Sales Pool

- Network: 192.168.10.0/24
- Default Gateway: 192.168.10.1
- DNS Server: 8.8.8.8
- Start Address: 192.168.10.100

### HR Pool

- Network: 192.168.20.0/24
- Default Gateway: 192.168.20.1
- DNS Server: 8.8.8.8
- Start Address: 192.168.20.100

## Verification

### Sales PC

Successfully received:

- IP Address: 192.168.10.100+
- Subnet Mask: 255.255.255.0
- Default Gateway: 192.168.10.1

### HR PC

Successfully received:

- IP Address: 192.168.20.100+
- Subnet Mask: 255.255.255.0
- Default Gateway: 192.168.20.1

### Connectivity Tests

Successful ping tests were performed between:

- Sales PC and HR PC
- Sales PC and DHCP Server

Results showed successful communication across all subnets with 0% packet loss.

## Files Included

1. Network Topology
2. DHCP Server Configuration
3. Router DHCP Relay Configuration
4. HR PC DHCP Assignment
5. Successful Ping Test
6. DHCP Relay Demonstration Video
7. Cisco Packet Tracer Lab File

## Skills Demonstrated

- DHCP Configuration
- DHCP Relay (IP Helper Address)
- Router Configuration
- IP Addressing and Subnetting
- Network Troubleshooting
- Cisco Packet Tracer

## Key Learning Outcome
This lab demonstrates how the `ip helper-address` command allows a router to forward DHCP broadcast requests to a DHCP server located on a different subnet. By implementing DHCP Relay, multiple networks can share a centralized DHCP service while maintaining successful communication between subnets.

