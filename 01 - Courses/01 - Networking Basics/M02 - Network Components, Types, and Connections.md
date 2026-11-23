---
course: Networking Basics
module: "02"
module-name: Network Components, Types, and Connections
type: Topic
status: completed
difficulty: 1
tags:
  - cisco
  - netacad
  - topic
  - networking-basics
created: 2026-11-19
last-reviewed: 2026-11-23
---
# Topic

> [!summary] TL;DR
> This module aims to explain network types, components and connections.

## Learning Objectives

- Understand the roles of clients and servers in a network.
- Understand the roles of network infrastructure devices.
- Understand ISP connectivity options.

## Key Concepts

- hosts
- client
- server
- peer-to-peer
- end device
- intermediate device
- network media
- Internet Service Provider (ISP)

## Notes

### Clients and Servers

All devices connected to a network that participate directly in the network communication are classified as ***hosts***. They can send and receive messages on the network. The software installed on the host determines its role.
***Servers*** are hosts that have software installed which enables them to provide information to other hosts on the network
***Clients*** are hosts that have software installed which enables the host to request and display the information obtained from the server

***Peer-to-peer (P2P)*** networks are networks where each host can act as both client and server. They are easier to set up, less complex and lower in cost. However, they possess no centralized administration, have less security, are not scalable and can perform more slowly.

### Network Components

The network infrastructure contains three categories of network infrastructure
- ***End devices*** | Serve as the origin or destination (hosts) of data on a network. (PC, laptop, smartphone)
- ***Intermediate devices*** | Connect end devices and networks, manage data flow, regenerate signals, and enforce security policies behind the scenes. (Switch, router, wireless access point)
- ***Network media*** | Provide the physical or wireless channels through which data signals travel from one device to another. (Wi-Fi, fiber optic cable, ethernet cable)

### ISP connectivity Options

***An Internet Service Provider (ISP)*** provides the link between the home network and the Internet. Each ISP connects to other ISPs to form a network of links that interconnect users all over the world. They are connected in a hierarchical manner to ensure internet traffic takes the shortest path.


## Real-World Connection

- In a home network : your phone (end device) → Wi-Fi router (intermediate device) → ISP (cable/fiber) → Internet.
- In a small office: PCs and printers (end devices) → switch (intermediate) → router/firewall (intermediate) → ISP.

## Gotchas / Exam Traps

- A host is any device that sends/receives. "hosts" ≠ "server". All clients and servers are hosts but not all hosts are servers

## Related Modules

- Previous: [[M01 - Communication in a Connected World]]
- Next: [[M03 - Wireless and Mobile Networks]]
- Related: [[M04 - Build a Home Network]]

## Self-Test Questions

1. What determines whether a host acts as a client or a server ?
2. Name three intermediate devices and explain what each does.
3. What are two advantages and two disadvantages of a P2P network compared to a client-server model ?
4. What is the role of an ISP, and how are ISPs connected to each other ?
5. Give one example each of end devices, intermediate devices, and network media.

## Resources

- [x] NetAcad module content
- [x] Checkpoint exam