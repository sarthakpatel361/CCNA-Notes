 # 📘 Day 8 – IPv4 Addressing (Part 2)

---

# 🔹 Core Concept (Don’t Skip This)

Every IPv4 question boils down to:

👉 Network bits vs Host bits

Everything you calculate comes from this.

---

# 🔹 Formula (VERY IMPORTANT)

```id="f1"
Number of hosts = 2^n - 2
```

* n = number of **host bits**
* -2 because:

  * Network address (all 0s)
  * Broadcast address (all 1s)

---

# 🔹 Example 1 (/24 Network)

```id="ex1"
192.168.1.0/24
```

* Total bits = 32
* Network bits = 24
* Host bits = 8

👉 Hosts:

```
2^8 - 2 = 256 - 2 = 254
```

---

## Addresses:

* Network: `192.168.1.0`
* Broadcast: `192.168.1.255`
* First usable: `192.168.1.1`
* Last usable: `192.168.1.254` 

---

# 🔹 Example 2 (/16 Network)

```id="ex2"
172.16.0.0/16
```

* Host bits = 16

👉 Hosts:

```
2^16 - 2 = 65,534
```

Addresses:

* Network: `172.16.0.0`
* Broadcast: `172.16.255.255`
* First: `172.16.0.1`
* Last: `172.16.255.254` 

---

# 🔹 Example 3 (/8 Network)

```id="ex3"
10.0.0.0/8
```

* Host bits = 24

👉 Hosts:

```
2^24 - 2 = 16,777,214
```

Addresses:

* Network: `10.0.0.0`
* Broadcast: `10.255.255.255`
* First: `10.0.0.1`
* Last: `10.255.255.254` 

---

# 🔹 Finding Addresses (Step-by-Step Method)

## Step 1: Identify Prefix

Example:

```
192.168.1.10/24
```

---

## Step 2: Find Network Address

👉 Set host bits = 0

Result:

```
192.168.1.0
```

---

## Step 3: Find Broadcast Address

👉 Set host bits = 1

Result:

```
192.168.1.255
```

---

## Step 4: Find Usable Range

* First usable = Network + 1
* Last usable = Broadcast - 1

---

# 🔹 Router Configuration (VERY PRACTICAL)

## Assign IP to Interface

```id="cfg1"
enable
configure terminal
interface gigabitEthernet 0/0
ip address 10.255.255.254 255.0.0.0
no shutdown
```

👉 Interface stays DOWN until `no shutdown` 

---

## Check Interface Status

```id="cfg2"
show ip interface brief
```

---

## Detailed Info

```id="cfg3"
show interfaces g0/0
```

---

## Add Description

```id="cfg4"
interface g0/0
description ## to SW1 ##
```

---

# 🔹 Interface States (Important)

* administratively down → manually shut
* down → cable/physical issue
* up → working

👉 Routers are **shutdown by default** 

---

# 🔹 Real Topology Insight

From diagram (page 11):

* Multiple networks:

  * 10.0.0.0/8
  * 172.16.0.0/16
  * 192.168.0.0/24

👉 Router connects different networks
👉 Each interface = different network 

---

# 🔁 Quick Revision

* Hosts = 2^n - 2
* Network = all 0s
* Broadcast = all 1s
* First = +1
* Last = -1
* Router needs `no shutdown`

---

# ❓ Interview Questions with Answers

## 🔸 Basic

Q1. How do you calculate number of hosts?
A. Using formula 2^n - 2, where n is number of host bits.

---

Q2. Why subtract 2?
A. Because network and broadcast addresses cannot be assigned to hosts.

---

Q3. What is first usable IP?
A. Network address + 1.

---

Q4. What is last usable IP?
A. Broadcast address - 1.

---

## 🔸 Intermediate

Q5. Find details for 192.168.10.25/24
A.

* Network: 192.168.10.0
* Broadcast: 192.168.10.255
* First: 192.168.10.1
* Last: 192.168.10.254
* Hosts: 254

---

Q6. What happens if you assign network address to a host?
A. It will not work because it represents the network itself.

---

Q7. Why router interfaces are down by default?
A. For security and manual control of network activation.

---

## 🔸 Scenario-Based (IMPORTANT)

Q8. Interface shows “administratively down”. What to do?
A. Use `no shutdown` command.

---

Q9. You configured IP but cannot ping. Possible reasons?
A.

* Interface down
* Wrong subnet
* No routing
* Cable issue

Q10. Why does each router interface need different subnet?
A. Because each interface connects to a different network.


 
 



 
 

