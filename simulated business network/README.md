
# Simulated Business Network

## Objective
Build a small business network using Cisco Packet Tracer and verify connectivity between departments.

## Topology

## Network Diagram

The network consists of:

- Sales Department (2 PCs)
- HR Department (1 PC)
- File Server Network
- Cisco 2911 Router
- Three Cisco 2960 Switches

A topology screenshot is included below.


## IP Addressing

### Sales Network
- Network: 192.168.10.0/24
- Gateway: 192.168.10.1

### HR Network
- Network: 192.168.20.0/24
- Gateway: 192.168.20.1

### File Server Network
- Network: 192.168.30.0/24
- Gateway: 192.168.30.1

## Router Interfaces

| Interface | IP Address |
|------------|------------|
| G0/0 | 192.168.10.1 |
| G0/1 | 192.168.20.1 |
| G0/2 | 192.168.30.1 |

## Testing

Successful ping tests:

- Sales PC → HR PC
- Sales PC → File Server
- HR PC → File Server

All devices communicated successfully across different subnets.

## Skills Demonstrated

- Router configuration
- IP addressing
- Network segmentation
- Default gateway configuration
- Connectivity testing
- Cisco IOS CLI
