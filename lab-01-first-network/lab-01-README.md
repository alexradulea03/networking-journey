# Lab 01 — First Network & Ping
### Date: 06/03/2026
### Tool: GNS3 with VPCS
### Status: ✅ Complete

## What I built
A simple network with two virtual PCs connected through a switch:
```
PC1 (192.168.1.1) ──┐
                   Switch1
PC2 (192.168.1.2) ──┘
```

## What I did

Opened GNS3 and dragged two VPCS nodes, cloud and one Ethernet switch onto the canvas
Connected PC1 and PC2 to Switch1 using cables
Started all devices using the green play button
![Alt text](/networking-journey/lab-01-first-network/screenshots/Screenshot 2026-03-06 155829.png?raw=true "Network Layout")
Opened each PC's console and assigned IP addresses manually:
```
PC1: ip 192.168.1.1/24
PC2: ip 192.168.1.2/24
```

Verified IPs with show ip
Pinged PC1 from PC2: ping 192.168.1.1


## What went wrong
Problem: Ping returned "not reachable" even though cables looked connected, IPs were correct and everything was running.
Root cause: PC1 and PC2 were running on different servers — PC2 was on my local machine while PC1 was on the GNS3 VM. Even though they appeared connected on the canvas, they were on completely isolated network stacks and couldn't communicate.
Fix: Moved all devices to the local server so they share the same network stack.

## What I learned

Two devices can look connected but still not communicate if they're running on isolated systems, this is the same concept behind VLANs later
In VPCS, the command to assign an IP is ip [address]/[prefix], different from Linux syntax
The /24 after the IP is the subnet mask in CIDR notation, means the first 3 octets identify the network, the last identifies the device
A switch alone is enough for devices on the same network to talk, no router needed yet


## Next objectives
Add a second network and a router & find out why devices on different networks can't talk through a switch alone.
