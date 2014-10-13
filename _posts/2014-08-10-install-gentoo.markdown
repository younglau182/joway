---
layout: post
title: "Install Gentoo general guide"
date: 2014-08-10 07:55
category: "linux"
---

I found this guide on 4Chan and am planning on making it so you can install it on a Mac.

```
boot a linux livecd

partition and format drive

go into drive

download and extract tar.gz file

sudo cp /etc/resolv.conf etc
sudo mount -t proc none proc
sudo mount --rbind /dev dev
sudo mount --rbind /sys sys

sudo chroot .

emerge --sync

echo -e "MAKEOPTS=\"-j4\"\nEMERGE_DEFAULT_OPTS=\"--keep-going=y --autounmask-write=y --jobs=4\"" >> /etc/portage/make.conf

emerge genkernel gentoo-sources grub dhcpcd

echo "MAKEOPTS=\"-j4\"" >> /etc/genkernel.conf

genkernel all

grub2-install /dev/sda
grub2-mkconfig > /boot/grub/grub.cfg

rc-update add dhcpcd default

passwd

exit

sudo reboot
```
