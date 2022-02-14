---
layout: post
title: A10 Basic Configuration
tags: A10 Basic Configuration
categories: A10
---

> Ahmet Numan Aytemiz 14.02.2022

---

## A10 Thunder Configuration Methods

- Web Gui
- Command Line (CLI)
- App Templates
- Harmony Controller
  - We can manage more than one device via harmany controller
- Ansible
- Scripts
- 3rd party Apps

## Configure Hostname

```
vThunder>enable
Password:
vThunder#conf t
vThunder(config)#hostname ANKARA-UMITKOYVM-CUSTOMER1
ANKARA-UMITKOYVM-CUSTOMER1(config)#write mem
```

![Image](/img/a10-hostname.png)


## Configure Multi Config

We need to enable multi config feature to configure A10 device more then one session simultaneously.

```
ANKARA-UMITKOYVM-CUSTOMER1#conf t
ANKARA-UMITKOYVM-CUSTOMER1(config)#multi-config enable
ANKARA-UMITKOYVM-CUSTOMER1(config)#write mem

```

![Image](/img/a10-multi-config.png)

## Configure Banner

```
ANKARA-UMITKOYVM-CUSTOMER1>
ANKARA-UMITKOYVM-CUSTOMER1>enable
Password:
ANKARA-UMITKOYVM-CUSTOMER1#conf t
ANKARA-UMITKOYVM-CUSTOMER1(config)#banner login "This Thunder Belongs to X Organization"
ANKARA-UMITKOYVM-CUSTOMER1(config)#banner exec "Dont change config before informing IT team"
ANKARA-UMITKOYVM-CUSTOMER1(config)#write mem

```

![Image](/img/a10-banner.png)

![Image](/img/a10-banner2.png)


## Configure DNS

```
ANKARA-UMITKOYVM-CUSTOMER1>enable
Password:
ANKARA-UMITKOYVM-CUSTOMER1#conf t
ANKARA-UMITKOYVM-CUSTOMER1(config)#ip dns primary 8.8.8.8
ANKARA-UMITKOYVM-CUSTOMER1(config)#ip dns secondary 8.8.4.4
ANKARA-UMITKOYVM-CUSTOMER1(config)#write mem

```

![Image](/img/a10-dns.png)

## Configure Timezone and NTP

```

ANKARA-UMITKOYVM-CUSTOMER1>enable
Password:
ANKARA-UMITKOYVM-CUSTOMER1#conf t
ANKARA-UMITKOYVM-CUSTOMER1(config)#timezone Europe/Athens
ANKARA-UMITKOYVM-CUSTOMER1(config)#sh clock
*10:46:04 EET Mon Feb 14 2022
ANKARA-UMITKOYVM-CUSTOMER1(config)#ntp server 10.250.0.11
ANKARA-UMITKOYVM-CUSTOMER1(config-ntpsvr:10.250.0.11)#enable
ANKARA-UMITKOYVM-CUSTOMER1(config-ntpsvr:10.250.0.11)#prefer
ANKARA-UMITKOYVM-CUSTOMER1(config-ntpsvr:10.250.0.11)#write mem

```

`show ntp status`

`show ntp servers`








