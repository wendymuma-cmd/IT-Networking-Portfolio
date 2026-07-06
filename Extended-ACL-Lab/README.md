# Extended ACL Lab

## Overview

After learning Inter-VLAN Routing, I wanted to understand how network administrators control communication between different departments without breaking the entire network.

In this lab, I configured an Extended Access Control List (ACL) to block one specific Sales PC from accessing the HR PC while allowing all other traffic to continue normally.

This helped me understand that ACLs are not simply about blocking traffic—they are about enforcing security policies with precision.

## Packet Tracer Lab

📥 **Download the Packet Tracer Lab:** [Extended-ACL-Lab.pkt](Extended-ACL-Lab.pkt)


## Objectives

- Configure an Extended ACL
- Apply the ACL inbound on the Sales interface
- Verify that only the intended traffic is blocked
- Test connectivity before and after applying the ACL

## Technologies Used

- Cisco Packet Tracer
- Cisco Catalyst 2960 Switch
- Cisco 2911 Router
- VLANs
- Router-on-a-Stick
- Extended ACLs

## Network Topology
< ![Topology](Topology.png)

## VLAN Verification

![VLAN](Show-VLAN-Brief.png)

## Trunking

![Trunking](Show-interfaces-trunk.png)

## Router Interface Verification

![Interfaces](Show-IP-Interface-Brief.png)

## ACL Configuration

![ACL](Show-Access-Lists.png)

## Connectivity Test
![Failed ping](Failed-ping-sales-PC1-HR-PC.png) 


## Successful ping
![Successful ping](Sales-PC2-HR-PC.png)

![Successful ping](Sales-PC1-Gateway.png)


## IP Addressing

| Device | IP Address |
|---------|------------|
| Sales PC1 | 192.168.10.2 |
| Sales PC2 | 192.168.10.3 |
| HR PC | 192.168.20.2 |
| Sales Gateway | 192.168.10.1 |
| HR Gateway | 192.168.20.1 |

## ACL Configuration

```text
ip access-list extended BLOCK_PC1_TO_HR
 deny ip host 192.168.10.2 host 192.168.20.2
 permit ip any any
