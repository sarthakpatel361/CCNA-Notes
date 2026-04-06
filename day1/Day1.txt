## 📌 Key Concept Summary

Networking devices are hardware components that connect and direct traffic across a network. Each device operates at a specific OSI layer and serves a distinct role — knowing *which device does what and why* is essential for both exams and interviews.

---

## ⚙️ Devices at a Glance

| Device | OSI Layer | Key Role |
| --- | --- | --- |
| Hub | Layer 1 | Broadcasts to all ports |
| Switch | Layer 2 | Forwards using MAC address table |
| Router | Layer 3 | Routes between networks using IP |
| Layer 3 Switch | Layer 2/3 | Switches + routes between VLANs |
| Access Point | Layer 2 | Extends LAN wirelessly |
| Firewall | Layer 3–7 | Filters traffic based on rules |
| Modem | Layer 1 | Converts digital ↔ analog signals |
| NIC | Layer 1/2 | Connects device to network, has MAC |

---

## 🔑 Key Concepts

**Collision Domain** — Area where packet collisions can occur.

- Hub = 1 collision domain for ALL ports (bad)
- Switch = 1 collision domain PER port (good)

**Broadcast Domain** — Area that receives broadcast frames.

- Switch = all ports in 1 broadcast domain (unless VLANs)
- Router = separates broadcast domains (each interface = 1 domain)

**Auto-MDI/MDIX** — Modern Cisco devices auto-detect cable type, so straight-through vs crossover doesn't matter in practice — but CCNA still tests the theory.

---

## 💼 Common Interview Questions

- What is the difference between a Hub, Switch, and Router?
    - **Hub** → Layer 1, dumb, broadcasts to all ports, single collision domain
    - **Switch** → Layer 2, uses MAC table, sends frames only to destination port
    - **Router** → Layer 3, routes between different networks using IP addresses
- What is a collision domain vs a broadcast domain?
    - **Collision domain** — where collisions happen. Each switch port = its own. Hub = one shared.
    - **Broadcast domain** — where broadcasts are received. Routers separate them. Switches don't (unless VLANs).
- What is the difference between a Layer 2 and Layer 3 switch?
    - **L2 Switch** → forwards frames using MAC addresses only
    - **L3 Switch** → can also route packets between VLANs using IP (switch + router combined)
- Why are hubs obsolete?
    
    Hubs share one collision domain across all ports — every device competes for bandwidth. Switches give each port its own collision domain, eliminating collisions entirely.
    
- Is a Modem the same as a Router?
    
    No. A **modem** converts signals to connect to an ISP. A **router** directs traffic between networks. Home devices often combine both, which causes confusion.
    

---

## ⚠️ Common Mistakes & Gotchas

- Switches do **NOT** separate broadcast domains — routers (or VLANs) do
- L3 switches **can** route — don't say "only routers route" in interviews
- Access Points are **not** routers — they extend wireless access, they don't route
- A NIC has a **MAC address** burned in (called BIA — Burned-In Address)

---

## 🖥️ Useful CLI Commands

```
show mac address-table        → View switch MAC address table
show ip interface brief       → View interface status
show ip route                 → View routing table (on router/L3 switch)
show arp                      → View IP-to-MAC mappings
```
