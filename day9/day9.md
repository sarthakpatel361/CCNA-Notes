 # 📘 Day 9 – Switch Interfaces   ( Notes + Interview Q&A)

---

# 🔹 What This Topic Covers

* Interface status
* Speed & duplex
* Autonegotiation
* Interface errors

👉 This is **real troubleshooting foundation**, not theory

---

# 🔹 Interface Status (VERY IMPORTANT)

## Command:

```bash
show ip interface brief
```

👉 Shows:

* Interface name
* IP address
* Status
* Protocol

---

## 🔹 Key States

| Status                | Meaning                  |
| --------------------- | ------------------------ |
| up/up                 | Working properly         |
| down/down             | No cable / no connection |
| administratively down | Manually shutdown        |

---

## 🔥 Important Difference

* Router interfaces → **shutdown by default**
* Switch interfaces → **NOT shutdown by default**

👉 So:

* Switch port + cable = usually **up/up**
* Router port = needs `no shutdown`
---

# 🔹 show interfaces status (Better for switches)

```bash
show interfaces status
```

👉 Gives:

* Port
* VLAN
* Status (connected / notconnect)
* Speed
* Duplex

👉 Cleaner than `show ip interface brief` for switches  

---

# 🔹 Speed & Duplex

## 🔹 Speed

* 10 Mbps
* 100 Mbps
* 1000 Mbps

## 🔹 Duplex

### Half Duplex

* Send OR receive (not both)
* Used in **hubs**
* Collisions happen

---

### Full Duplex

* Send AND receive simultaneously
* No collisions
* Used in switches

 Full duplex = better performance  (Page 13)

---

# 🔹 Collision Domain (Important Concept)

* Hub → **1 collision domain**
* Switch → **separate collision domain per port**

 Why switches are better

 (Pages 17–19 show this visually)

---

# 🔹 CSMA/CD (Only for Half Duplex)

* Devices “listen” before sending
* If collision → send jamming signal
* Retry after random delay

 Only exists because of collisions

 

---

# 🔹 Autonegotiation (CRITICAL)

* Devices automatically choose:

  * Best speed
  * Best duplex

👉 Default = **auto/auto**

---

## 🔥 What happens if mismatch?

Example:

* One side = auto
* Other = manual

👉 Result:

* Speed may match
* Duplex becomes **half**

👉 Leads to:
❌ Collisions
❌ Performance issues

 

---

# 🔹 Interface Configuration

```bash
conf t
interface f0/1
speed 100
duplex full
description ## to R1 ##
```

👉 You can manually override auto settings   

---

# 🔹 Interface Range (VERY USEFUL)

```bash
interface range f0/5 - 12
shutdown
```

👉 Configure multiple ports at once

---

# 🔹 Interface Errors (REAL TROUBLESHOOTING)

Command:

```bash
show interfaces f0/2
```

---

## 🔹 Important Errors

| Error  | Meaning            |
| ------ | ------------------ |
| Runts  | Frame < 64 bytes   |
| Giants | Frame > 1518 bytes |
| CRC    | Corrupted frame    |
| Frame  | Format issue       |

👉 These indicate real network problems  (Page 25)

---

# 🔁 Quick Revision

* Switch ports = up by default
* Full duplex = no collisions
* Half duplex = collisions + CSMA/CD
* Autonegotiation = default
* Mismatch = performance issues

---

# ❓ Interview Questions with Answers

## 🔸 Basic

Q1. What does `show ip interface brief` show?
A. Interface status, IP, and protocol state.

---

Q2. Difference between router and switch interfaces?
A. Router interfaces are shutdown by default, switch interfaces are not.

---

Q3. What is duplex?
A. Mode of communication: half (one direction) or full (both directions).

---

## 🔸 Intermediate

Q4. What is autonegotiation?
A. Process where devices automatically choose best speed and duplex.

---

Q5. What happens in duplex mismatch?
A. One side runs half duplex, causing collisions and poor performance.

---

Q6. What is collision domain?
A. Network segment where collisions can occur.

---

## 🔸 Scenario-Based (IMPORTANT)

Q7. Interface is “administratively down”. Fix?
A. Use `no shutdown`.

---

Q8. High CRC errors seen. Possible cause?
A. Cable issue, interference, or duplex mismatch.

---

Q9. Slow network but link is up. Why?
A. Duplex mismatch causing collisions.

 

 