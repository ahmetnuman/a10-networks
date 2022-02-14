---
layout: post
title: A10 Application Delivery Partitions
tags: A10 Application Delivery Partitions
categories: A10
---

We can isolate system compenent. It will provide the flexibilty to push application based configuration in different partitions.

#### Benefits :

- Simple, ease to manage
- Partition Level Granular Access
- Resource optimization - Less hardware unit i.e. SSLi, Skype for business
- IP re-useability i.e. interaface , VIP
- Resource Distribution / Partition

#### Types of Partitions :

- Service Partition (SP)
 - Partition in Partition
 - VLAN, interface - Parent Partition

 - Layer 3 Virtualization (L3V)
  - Shared - Ethernets, vlans
  - Partition Specific - L3(IP) -L7

![Image](/img/partitions.png)  

  

