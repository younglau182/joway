---
layout: post
title: "What is VMMNG"
date: 2014-03-19 03:03
category: tools
---

I am happy to announce my new "tool" - vmmng. If you are like me you do not work on a Windows machine and you are "forced" to use ESXi. Turning VM's on and off at will can, and will, get a bit tedious. Using that pesky Windows VM to administrate the ESXi server by just turning off and on machines is a little bit stupid. View [the project](http://github.com/andreicek/vmmng) on GitHub.

There are commands for ESXi if you enabled SSH shell and they do work great but, again, I needed something that won't take forever to do. Log in into SSH, list the VM, power it on, log out. And in between - google the command for turning it off and on.

Here comes **vmmng**. A nifty tool written in ruby that I plan on building up to do even more stuff.

Be sure to enable SSH on the ESXi box and also to create a key pair for login so you don't have to provide the password.

[Here](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2004746) is how to enable shell access on ESXi, and [here](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1002866) is how to use key auth with ESXi.


##How to install vmmng

1. Clone the repo

    `git clone https://github.com/andreicek/vmmng.git`

2. Edit the script and replace `USERNAME` and `HOSTNAME`

    ```
    USERNAME = root
    HOSTNAME = the.server.com
    ```

3. Move the `vmmng` script to your bin folder

    `mv vmmng ~/.dotfiles/bin`

4. Allow it to run

    `chmod +x ~/.dotfiles/bin/vmmng`
