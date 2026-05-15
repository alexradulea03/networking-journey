# networking-journey

A hands-on lab portfolio documenting my journey toward the Cisco CCNA certification. Every lab is built from scratch, tested, and documented with step-by-step instructions, CLI output, and screenshots, no copy-paste, no shortcuts.

## About

Every lab here represents something I built, broke, debugged, and learned from.

I started with the basics: connecting two computers. Now I'm configuring WAN links, dynamic routing protocols, and multi-site networks. The goal is the CCNA, but the real goal is to be able to walk into any network environment and know what I'm doing.

---

## Tools

| Tool | Purpose |
|---|---|
| Cisco Packet Tracer | Primary lab environment for CCNA topics |
| GNS3 | Used in early labs, returning for advanced topics |
| GitHub | Lab documentation and portfolio |

---

## Lab Progress

| Lab | Title | Scenario | Key Concepts | Status |
|---|---|---|---|---|
| 01 | [Connecting Two PCs](lab-01-connecting-two-pcs/) | — | Basic connectivity, crossover cable, GNS3 interface | ✅ Done |
| 02 | [Construction Inc. — Basic Office Network](lab-02-construction-inc/) | Construction Inc. | Star topology, static IPs, switch, router, Packet Tracer interface | ✅ Done |
| 03 | [Construction Inc. — Server & Services](lab-03-construction-inc-pt2/) | Construction Inc. | DHCP, DNS, HTTP, FTP, network printer, static vs dynamic addressing | ✅ Done |
| 04 | [Construction Inc. — VLANs](lab-04-construction-inc-vlans/) | Construction Inc. | VLANs, access ports, trunk ports, Router-on-a-Stick, inter-VLAN routing | ✅ Done |
| 05 | [Riverstone Legal — WAN & Routing](lab-05-riverstone-legal-wan/) | Riverstone Legal | Serial WAN link, /30 subnetting, static routing, RIPv2, multi-site design | ✅ Done |
| 06 | [Riverstone Legal — WAN & Routing](lab-06-riverstone-legal-acls/) | Riverstone Legal | ACLs, standard vs extended, traffic filtering, SSH access control | ✅ Done |
| 07 | Coming soon | TBD | OSPF, dynamic routing, link-state vs distance-vector | 🔄 In progress |
| 08 | Coming soon | TBD | NAT/PAT, internet simulation, overload | 📋 Planned |

---

## Concepts Covered So Far

- Physical and logical network topologies
- IP addressing and subnetting (including /30 for WAN links)
- Static IP assignment vs DHCP
- DNS, HTTP, FTP server configuration
- Network printing over a LAN
- VLAN design and segmentation
- 802.1Q trunking and Router-on-a-Stick
- Inter-VLAN routing
- Serial WAN links and clock rate
- Static routing (`ip route`)
- RIPv2 dynamic routing (`no auto-summary`)
- Multi-site network design

---

## Certification Roadmap

```
[In Progress] CCNA (200-301)
              ↓
          [Planned] CompTIA Security+
```

**CCNA Topics Checklist**

- [x] Network fundamentals and topologies
- [x] IP addressing and subnetting
- [x] Switching — VLANs, trunking
- [x] Routing — static, RIP
- [ ] Routing — OSPF
- [ ] ACLs — standard and extended
- [ ] NAT / PAT
- [ ] Network security fundamentals
- [ ] Wireless basics
- [ ] Automation and programmability

---

## What's Next

**Lab 06 — ACLs (Access Control Lists)**
Building on the Riverstone Legal two-site network from Lab 05. Adding traffic filtering rules to control what branch PCs can and cannot access at HQ — the primary tool for network security policy on Cisco devices.

**Lab 07 — OSPF**
Replacing RIPv2 with OSPF in the Riverstone Legal network. Understanding why link-state routing protocols replaced distance-vector in real-world networks.

**Lab 08 — NAT/PAT**
Simulating internet access — translating private addresses to a public IP so internal hosts can reach the outside world.

---

## Lab Structure

Each lab folder contains:

```
lab-XX-name/
├── README.md          ← full step-by-step documentation
├── *.pkt              ← Packet Tracer save file (or GNS3 project or n/a)
└── screenshots/       ← screenshots referenced in the README
```

---

## Note on Mistakes

Every troubleshooting section in these labs documents real mistakes made during the build — wrong port assumptions, misconfigured interfaces, syntax errors. They are left in intentionally to show my troubleshooting abilities.

---

*Built by Alex — Timisoara, Romania*