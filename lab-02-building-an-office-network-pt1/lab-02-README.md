
# Lab 02 — Construction Inc. Office Network
 
**Tool:** Cisco Packet Tracer  
**Difficulty:** Beginner  
**Builds on:** Lab 01 — Connecting Two PCs in GNS3
 
---
 
## Scenario

I wanted to start learning with hands-on practice, so i've decided to start working for Construction Inc. A newly founded company.
 
Construction Inc. needs a basic office network. As the network technician, my job is to design and build their internal network from scratch inside Cisco Packet Tracer — naming all devices properly, connecting the hardware, and verifying that all PCs can communicate through a central switch and router.
 
---
 
## Objectives
 
- Show that I'm comfortable with the Cisco Packet Tracer interface
- Add and name network devices to represent a real company environment
- Connect PCs to a switch, and the switch to a router
- Assign IP addresses and verify basic connectivity with `ping`
---
 
## Topology
 
```
PC-Office-1 ──┐
PC-Office-2 ──┤
PC-Office-3 ──┼──── SW-HQ ──── RT-HQ
PC-Office-4 ──┤
PC-Office-5 ──┘
```
 
| Device | Hostname | Role |
|---|---|---|
| Router | RT-HQ | Default gateway for the office |
| Switch | SW-HQ | Connects all office PCs |
| PC 1–5 | PC-Office-1 … PC-Office-5 | End-user workstations |
 
---
 
## IP Addressing
 
| Device | IP Address | Subnet Mask | Default Gateway |
|---|---|---|---|
| RT-HQ (Fa0/0) | 192.168.1.1 | 255.255.255.0 | — |
| PC-Office-1 | 192.168.1.10 | 255.255.255.0 | 192.168.1.1 |
| PC-Office-2 | 192.168.1.11 | 255.255.255.0 | 192.168.1.1 |
| PC-Office-3 | 192.168.1.12 | 255.255.255.0 | 192.168.1.1 |
| PC-Office-4 | 192.168.1.13 | 255.255.255.0 | 192.168.1.1 |
| PC-Office-5 | 192.168.1.14 | 255.255.255.0 | 192.168.1.1 |
 
---
 
## Step-by-Step Build
 
### Step 1 — Opening Packet Tracer and starting a New Project
 
I opened Cisco Packet Tracer and created a new blank project. This office space will be named Construciton Inc.
 
![Step 1 — New blank Packet Tracer project]()
 
---
 
### Step 2 — Add the Router
 
From the device panel at the bottom, I have selected **Routers** and dragged a `2911` router onto the workspace.
 
![Step 2 — Router added to workspace]()
 
---
 
### Step 3 — Naming the Router
 
I clicked the router to open its config panel. I've navigated to **Config → Settings** and set the **Display Name** and **Hostname** to `RT-HQ`. This represents Construction Inc.'s main office router.
 
![Step 3 — Router named RT-HQ]()
 
---
 
### Step 4 — Add the Switch
 
From the device panel, I selected **Switches** and dragged a `2960` switch onto the workspace below the router. I chose the 2960 as they are known for long term reliabilty and a truly viable option for small to medium sized networks.
 
![Step 4 — Switch added to workspace]()
 
---
 
### Step 5 — Naming the Switch
 
I clicked the switch → **Config → Settings** and set the **Display Name** and **Hostname** to `SW-HQ`.
 
![Step 5 — Switch named SW-HQ]()
 
---
 
### Step 6 — Add the PCs
 
From the device panel, I selected **End Devices** and dragged 5 PCs onto the workspace. Arrange them in a row below the switch.
 
![Step 6 — Five PCs added to workspace]()
 
---
 
### Step 7 — Naming Each PC
 
Click each PC → **Config → Settings** and set the **Display Name** to `PC-Office-1` through `PC-Office-5`.
 
![Step 7 — PCs named PC-Office-1 to PC-Office-5]()
 
---
 
### Step 8 — Connect the PCs to the Switch
 
Selected the **Connections** tool (lightning bolt icon) and chose the **Copper Straight-Through** cable. I then clicked each PC's `FastEthernet0` port and connect it to any available port on `SW-HQ`.
 
![Step 8 — PCs port selection to SW-HQ]()
![Step 8 — PCs connected to SW-HQ]()
 
---
 
### Step 9 — Connect the Switch to the Router
 
Used another **Copper Straight-Through** cable to connect `SW-HQ` (any free port that i've had) to `RT-HQ` on `GigabitEthernet0/0`.
 
![Step 9 — SW-HQ connected to RT-HQ port]()
![Step 9 — SW-HQ port to RT-HQ]()
![Step 9 — SW-HQ connected to RT-HQ]()
 
---
 
### Step 10 — Configured the Router Interface
 
Clicked `RT-HQ` → **CLI** tab and entered the following:
 
```
enable
configure terminal
interface GigabitEthernet0/0
 ip address 192.168.1.1 255.255.255.0
 no shutdown
end
```

![Step 10 — Router interface configured via CLI]()
(i've accidentally called for FastEthernet but RT-HQ only has GigabitEthernet)

---
 
### Step 11 — Assign IP Addresses to PCs
 
Clicked each PC → **Desktop → IP Configuration** and assigned the IP, subnet mask, and default gateway from the addressing table above.
 
![Step 11 — IP configuration on PC-Office-1]()
 
---
 
### Step 12 — Verifying the connectivity with Ping
 
On PC 2, I've gone to **Desktop → Command Prompt** and ping another PC and the router:
 
```
ping 192.168.1.1
ping 192.168.1.11
```
 
A successful reply confirms the network is working.
 
![Step 12 — Successful ping between PCs]()
 
---
 
## What I Learned
 
- How to navigate the Cisco Packet Tracer interface and place devices
- The importance of naming devices clearly to reflect real-world environments
- How a star topology works: all PCs connect to a switch, switch connects to a router
- How to assign IP addresses manually on end devices
- Verified end-to-end connectivity using `ping`
---
 
## Compared to Lab 01
 
| | Lab 01 | Lab 02 |
|---|---|---|
| Tool | GNS3 | Cisco Packet Tracer |
| Devices | 2 PCs | 5 PCs, 1 switch, 1 router |
| Connection | Direct crossover | Star topology via switch |
| Addressing | Manual | Manual with gateway |
| Verification | Basic ping | Ping to gateway + other PCs |
 
---
