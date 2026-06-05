# Small Business Network Design and Implementation using Cisco Packet Tracer

## Project Overview

This project demonstrates the design, configuration, and testing of a small business network using Cisco Packet Tracer.

The network was designed for three departments:

* Administration
* Sales and Marketing
* Information Technology (IT)

Each department was assigned its own subnet to ensure organized network management and scalability.

## Network Components

* 1 Cisco Router (2911)
* 3 Cisco Switches
* 15 PCs (5 per department)

## IP Addressing Scheme

| Department     | Network Address | Subnet Mask   |
| -------------- | --------------- | ------------- |
| Administration | 192.168.10.0    | 255.255.255.0 |
| Sales          | 192.168.20.0    | 255.255.255.0 |
| IT             | 192.168.30.0    | 255.255.255.0 |

## Configuration Tasks Completed

* Network topology design
* Device interconnection
* Router interface configuration
* IP address assignment
* Default gateway configuration
* Connectivity testing using ICMP ping

## Challenges Encountered

### Router-to-Switch Links Remained Down

One of the first challenges encountered was that all router-to-switch connections remained red despite correct cabling.

After troubleshooting, I learned that Cisco router interfaces are administratively down by default. The issue was resolved by enabling the interfaces using:

enable

configure terminal

interface gigabitethernet0/0,0/1,0/2

no shutdown

This immediately brought the interfaces up and established connectivity.

### Inter-Department Communication Failure

Although devices within the same department could communicate successfully, communication between departments initially failed.

Further investigation revealed that IP addresses had been assigned to all end devices, but the router interfaces had not yet been configured with gateway addresses.

After assigning the following addresses:

* G0/0 → 192.168.10.1
* G0/1 → 192.168.20.1
* G0/2 → 192.168.30.1

Inter-network routing functioned successfully.

## Verification

Successful ICMP ping tests were performed between:

* Administration ↔ Sales
* Administration ↔ IT
* Sales ↔ IT

## Key Concepts Learned

* IPv4 Addressing
* Subnetting
* CIDR Notation
* ARP (Address Resolution Protocol)
* ICMP (Internet Control Message Protocol)
* Router Configuration
* Inter-Network Routing
* Network Troubleshooting

## Outcome

This project provided hands-on experience in designing, configuring, and troubleshooting a routed network. 
It strengthened my understanding of how devices communicate across multiple subnets and the critical role routers play in enabling inter-network communication.
