---
layout: post
title: A10 Lab Setup
tags: A10 Lab Setup
categories: A10
---

> Ahmet Numan Aytemiz 14.02.2022

![Image](/img/a10-lab-topology.png)


**Tasks**

- Configure ethernet 2 ip address : 192.168.200.135/24
- Configure ethernet 1 ip address : 192.168.100.133/24
- Create partition 
   - name Sharepoint, id 1 , type : L3V , App Type : ADC
   - name SSLi, id 3 , type : L3V , App Type : none
   - name Exchange, id 4 , type : L3V , App Type : ADC
   - name CGN, id 5 , type : L3V , App Type : CGNV6
   - name HTTP, id 6 , type : Service Partition , App Type : ADC

 - Assignt ethernet 3 interafece to the Sharepoint partition and configure ip address : 192.168.100.133/24

 - Under the HTTP partition :
   - create slb server as following :
     - name srv1
     - ip address 192.168.200.140
     - port 80 tcp

    - create slb service-group as following :
      - name sg1
      - member srv1
      - port 80

    - create slb virtual-server as following :
      - name : vip
      - ip address : 192.168.100.200 
      - source-nat : auto
      - service-group : sg1

- Verify wheater conneting http://192.168.100.200 from client pc


   

