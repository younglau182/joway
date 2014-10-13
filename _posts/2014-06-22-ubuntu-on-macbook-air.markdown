---
layout: post
title: "Ubuntu on MacBook Air - The easy way"
date: 2014-06-22 09:00
location: "Zagreb, Croatia"
category: "linux"
---

This process is if you want **single boot** only. There are a lot of tutorials on dualboot out there.

##1. Remove FileVault

You will not be able to remove partitions on the disk if you skip this step. If you however don't have FileVault turned on move along :)

##2. Download Ubuntu and prepare the USB disk

In OSX go ahead and download the [ubuntu-13.10-desktop-amd64.iso](http://releases.ubuntu.com/13.10/ubuntu-13.10-desktop-amd64.iso). Next you will need to convert the ISO file to IMG (OSX will append .dmg to it, it won't matter).

```
cd ~/Downloads
hdiutil convert -format UDRW -o ubuntu-13.10-desktop-amd64.img ubuntu-13.10-desktop-amd64.iso
diskutil list
```

From the `diskutil list` command find your USB and remeber/write down the disk ID (e.g. disk2). **Be sure that this is correct.**

```
diskutil unmountDisk /dev/disk<REPLACE ME>
sudo dd if=ubuntu-13.10-desktop-amd64.img.dmg of=/dev/rdisk<REPLACE ME> bs=1m
```

Now you have the installation drive ready. Be sure that you have backed up all data that you want to save. *Note: Ubuntu will read NFS+ partitions if you happen to have such disks.*

##3. Removing OSX

Boot into recovery. Restart the computer and hold down `CMD + R`. The recovery menu will show up, select the Disk Utillity. Unmount the system disk, go to **Partition** tab and select from the dropdown menu 1 partition. As type select Free. Hit apply and power off the computer.

##4. Boot into the instalation USB

Be sure that the disk is in the computer (use the left USB port, I had no luck with the right one...). Start up the computer while holding `Alt` button. The computer will boot up, and select Install Ubuntu from the menu.

##5. Install Ubuntu

Next, next, next... ;)

##6. Fix the boot issue

Now if you try booting you will get the missing "folder" icon. This is fixable quite easly. Plug the USB installation disk back in and this time boot into live CD. Open up the terminal and do the following:

```
sudo apt-get install efibootmgr
sudo efibootmgr
```

Ubuntu shuld be listed as `Boot0000*`. Run this simple command to fix the boot `sudo efibootmgr -o 0,80`. Now reboot and enjoy Ubuntu.

##7. After the installation

I reccomend following [this](https://help.ubuntu.com/community/MacBookAir6-2/Trusty) guide to setup Airport and improve battery life.


