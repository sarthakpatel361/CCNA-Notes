
## 🔧 Topology Setup

```
PC1 -------- SW1 -------- SW2 -------- PC3
             |              |
            PC2            PC4
```

---

## 🌐 IP & MAC Addressing

| Device | IP Address  | MAC Address    |
| ------ | ----------- | -------------- |
| PC1    | 192.168.1.1 | AAAA.AAAA.AAAA |
| PC2    | 192.168.1.2 | BBBB.BBBB.BBBB |
| PC3    | 192.168.1.3 | CCCC.CCCC.CCCC |
| PC4    | 192.168.1.4 | DDDD.DDDD.DDDD |

---

# 🔥 ARP Process (Step-by-Step)

## 🎯 Scenario

PC1 wants to ping PC3

---

## 🧠 Step 1: Problem

PC1 knows:

* Destination IP = `192.168.1.3`
* ❌ Does NOT know MAC address

👉 This is where ARP starts

---

## 📡 Step 2: ARP Request (Broadcast)

PC1 sends:

* Source MAC: `AAAA.AAAA.AAAA`
* Destination MAC: `FFFF.FFFF.FFFF` (Broadcast)

Message:

> Who has 192.168.1.3?

---

## 🔁 Step 3: Switch Behavior

### SW1:

* Learns: `AAAA → Port connected to PC1`
* Floods frame to all other ports

### SW2:

* Receives frame and floods to all its ports

👉 Result: **All devices receive ARP request**

---

## 🎯 Step 4: ARP Reply (Unicast)

Only PC3 responds:

* Source MAC: `CCCC.CCCC.CCCC`
* Destination MAC: `AAAA.AAAA.AAAA`

Message:

> I am 192.168.1.3

---

## ⚡ Step 5: Learning Happens

### PC1:

* Stores in ARP table:

  ```
  192.168.1.3 → CCCC.CCCC.CCCC
  ```

### Switches:

* Learn:

  ```
  CCCC → correct port
  ```

---

## 🚀 Step 6: Actual Communication

Now PC1 sends data:

* Source MAC: `AAAA.AAAA.AAAA`
* Destination MAC: `CCCC.CCCC.CCCC`

👉 Switch forwards directly (NO flooding)

---

# 🔁 What Changes After First Packet?

| Phase      | Behavior          |
| ---------- | ----------------- |
| Before ARP | Flooding          |
| After ARP  | Direct Forwarding |

👉 Network becomes efficient after learning

---

# ⚠️ Important Observations

* ARP request = **Broadcast → Flood**
* ARP reply = **Unicast → Forward**
* Switch learns from **Source MAC**
* First ping may be **slow or fail** due to ARP

---

# 🧠 Key Insight

```
IP known → ARP finds MAC → Switch forwards → Communication works
```

---
