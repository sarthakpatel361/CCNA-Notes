 # Day 2 — Interfaces & Cables

## 📌 Key Concept Summary

Networking interfaces are the ports on devices that connect them to a network. Cables are the physical medium that carry signals between those interfaces. Choosing the right cable type depends on the devices being connected, the distance, and the speed required.

---

## ⚙️ Interface Types

| Interface | Speed | Common Use |
| --- | --- | --- |
| FastEthernet (Fa) | 100 Mbps | Older LANs |
| GigabitEthernet (Gi) | 1 Gbps | Modern LANs |
| 10GigabitEthernet | 10 Gbps | Data centers, uplinks |
| Serial | Variable | WAN connections (older) |
| Loopback | Virtual | Testing, routing protocols |
- Interfaces on Cisco devices are named like **GigabitEthernet0/0** or **Fa0/1**
- A loopback interface is **virtual** — it never goes down unless manually shut

---

## 🔌 Cable Types

### Copper — UTP (Unshielded Twisted Pair)

Most common in LANs. Twisted pairs reduce electromagnetic interference (EMI).

| Category | Speed | Notes |
| --- | --- | --- |
| Cat5 | 100 Mbps | Obsolete |
| Cat5e | 1 Gbps | Still found in older installs |
| Cat6 | 1–10 Gbps | Modern standard |
| Cat6a | 10 Gbps | Data centers |

**Wiring Standards:**

- **Straight-through** — Both ends same standard (T568B–T568B). Connects *different* device types (PC → Switch, Router → Switch)
- **Crossover** — Ends use different standards (T568A one end, T568B other). Connects *same* device types (Switch → Switch, PC → PC)
- **Rollover / Console** — Flat light-blue cable. Used to configure Cisco devices via console port

> **Auto-MDI/MDIX** — Modern Cisco devices auto-detect and adjust. Straight-through vs crossover distinction is mostly **theoretical for CCNA** now, but still tested.
> 

---

### Fiber Optic

Transmits data as **light**. Used for long distances or high-speed backbone links.

| Type | Core | Light Source | Distance | Cost |
| --- | --- | --- | --- | --- |
| **Single-Mode (SMF)** | Thin | Laser | Up to 100km | Expensive |
| **Multi-Mode (MMF)** | Wide | LED | Up to 2km | Cheaper |
- SMF = long distance (WAN, ISP, between buildings)
- MMF = short distance (within a building, campus)

---

### Coaxial Cable

- Old technology — used in early Ethernet (10BASE2, 10BASE5) and cable TV
- Rarely seen in modern networks but may appear in CCNA theory questions

---

## 🌍 Why It Matters

Wrong cable = no connectivity. In real jobs you need to know which cable to run between which devices. In interviews, cable and interface questions come up frequently as quick "do you know the basics" checks.

---

## 💼 Common Interview Questions

- When do you use a straight-through vs crossover cable?
    - **Straight-through** → Different device types (PC to Switch, Router to Switch)
    - **Crossover** → Same device types (Switch to Switch, PC to PC, Router to Router)
- What is Auto-MDI/MDIX?
    
    A feature on modern Cisco devices that automatically detects the cable type and adjusts accordingly — so straight-through vs crossover no longer matters in practice.
    
- What is the difference between Single-Mode and Multi-Mode fiber?
    - **SMF** — Thin core, laser light, long distances (up to 100km), expensive
    - **MMF** — Wider core, LED light, short distances (up to 2km), cheaper
- What cable do you use to configure a Cisco router/switch for the first time?
    
    A **rollover (console) cable** — connected from your PC's USB/serial port to the device's console port. Used for out-of-band management.
    
- What is a loopback interface and why is it used?
    
    A virtual interface that is always up unless manually shut down. Used for testing, management access, and as a stable router ID in routing protocols like OSPF.
    

---

## ⚠️ Common Mistakes & Gotchas

- **Forgetting Auto-MDI/MDIX exists** — Don't say crossover is always required for same-device connections on modern gear
- **Confusing SMF and MMF** — SMF = long distance + laser; MMF = short distance + LED
- **Thinking fiber is only for speed** — Fiber is also chosen for **distance** and **EMI immunity**
- **Console cable ≠ Ethernet cable** — Rollover cable is for configuration, not data transfer
- **Loopback is virtual** — It has no physical port; it never physically goes down

---

## 🖥️ Useful CLI Commands
show interfaces                    → Detailed status of all interfaces
show ip interface brief            → Quick summary (IP, status, protocol)
show interfaces GigabitEthernet0/0 → Specific interface details
show controllers serial 0/0        → Check if DCE/DTE on serial links