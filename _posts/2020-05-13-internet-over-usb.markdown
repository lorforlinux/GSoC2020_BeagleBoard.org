---
layout: post
title:  Internet over USB for BeagleBone (Fedora Linux)
---

This topic is explained all over the internet but my favourite is this detailed [Gist](https://gist.github.com/pdp7/d2711b5ff1fbb000240bd8337b859412) from [pdp7](https://github.com/pdp7) for configuring the network for Internet over USB. This post will be a concise version of that Gist.

<span style="color:red"> Node: I am using Fedora Linux here, if you are using something different then wireless and ethernet device names might be different for you.</span>

For using internet over USB we have to setup a conection like this:

`BBB <-- USB --> Laptop <-- WiFi --> Internet`

## Setting up the connection

Identify the wireless acess point and the ethernet device (BeagleBone) names. Type `ifconfig` and look for a devices with name starting with wlp and enp, they are your wifi and ethernet devices respectively. Output from `ifconfig` will look something like this:

  ``` output
  ...

enp0s20u2: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 192.168.7.1  netmask 255.255.255.252  broadcast 192.168.7.3
        inet6 fe80::d04a:c143:36e4:edfa  prefixlen 64  scopeid 0x20<link>
        ether 50:72:24:b7:38:64  txqueuelen 1000  (Ethernet)
        RX packets 48  bytes 7716 (7.5 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 53  bytes 10475 (10.2 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

...

wlp3s0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 192.168.0.105  netmask 255.255.255.0  broadcast 192.168.0.255
        inet6 fe80::e2bf:8e13:6de3:8894  prefixlen 64  scopeid 0x20<link>
        ether 4c:34:88:08:64:a2  txqueuelen 1000  (Ethernet)
        RX packets 2523304  bytes 2394947379 (2.2 GiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 1063434  bytes 562873531 (536.7 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```

Here `enp0s20u2` with `inet 192.168.7.1` and `wlp3s0` with `inet 192.168.0.105` are the devices we want for the connection. If you want to learn about how these deices are named you can see [this](https://unix.stackexchange.com/questions/134483/why-is-my-ethernet-interface-called-enp0s10-instead-of-eth0) stackexchange answer, For quick info see this:

``` information
enp4s10f0                        pci 0000:04:0a.0
| | |  |                                |  |  | |
| | |  |                   domain <- 0000  |  | |
| | |  |                                   |  | |
en| |  |  --> ethernet                     |  | |
  | |  |                                   |  | |
  p4|  |  --> prefix/bus number (4)  <--  04  | |
    |  |                                      | |
    s10|  --> slot/device number (10)<--     10 |
       |                                        |
       f0 --> function number (0)    <--        0
```

After finding the correct device names everything else is very simple. Here are the commands for your BeagleBone and Linux Computer. If you are confused what does `$` and `#` means, they are part of your linux [prompt](https://linuxconfig.org/bash-prompt-basics). The `$` before a command means you are a normal user and `#` means you are a super user OR root (use `su` OR `sudo su command` to become root).

### Linux Computer

``` commands
Become SuperUser
$ sudo su

Turn on ip forwarding
# echo 1 > /proc/sys/net/ipv4/ip_forward

Flush old rules from iptables (e.g. firewall)
# iptables -t nat -F
# iptables -t mangle -F
# iptables -F
# iptables -X

Setup the connection
# iptables --table nat --append POSTROUTING --out-interface wlp3s0 -j MASQUERADE
# iptables --append FORWARD --in-interface enp0s20u2 -j ACCEPT
```

### BeagleBone

``` commands
Become Super User
$ sudo su

Congigure the connection
# /sbin/route add default gw 192.168.7.1
# echo "nameserver 8.8.8.8" >> /etc/resolv.conf
```

You can create bash scripts for both and run them instead of writing all the commands one by one. Now you know what you have to do to use Internet over USB on a BeagleBone :) go try it yourslef. If you find any problem in the post, you can create a new issue for this repository.
