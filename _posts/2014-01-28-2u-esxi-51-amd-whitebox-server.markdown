---
layout: post
title: "2u ESXi 5.1 AMD whitebox server"
date: 2014-01-28 03:03
category: "homelab"
---

As a software engineer I don't have any real connections to the "hardware" world in my studies. But I saw an opportunity to get some hand on knowledge in server/client visualization. I choose VMware because I have some experience in their end user software. This is the hardware that I will buy:


| Hardware | Price (USD) |
|----------|------------:|
|INTER-TECH IPC 2U-2312L /w power supply|262|
|INTEL EXPI9301CTBLK|48|
|AMD FX-Series X8 8320|205|
|Asrock 970 Extreme3|97|
|DDR3 8GB (1x8GB) Kingston, HyperX Blue x2|215|
|Thermaltake Contac 30|46|
|**TOTAL**|**873**|

-----------------

**Edit:**

Once everything arrived I set up the box, installed ESXi 5.1 (support for INTEL EXPI9301CTBLK was dropped on ESXi 5.5 and I had to slipstream 5.5, and I had no time). I had to add a graphic card, and by friend recommendation I went with ASUS 5450. Also, being lucky guy I am, I got borrowed two Cisco routers (more about this in next posts).

The diagram of my network is as follows:

[![Network diagram](http://andreicek.eu/images/network-diagram.png)](http://i.imgur.com/qwFxaso.png)

More soon.
