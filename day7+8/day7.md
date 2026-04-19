 # 📘 Day 7 – IPv4 Addressing (Part 1)

---

# 🔹 Network Layer (Layer 3)

* Provides **communication between different networks**
* Uses **IP addresses (logical addressing)**
* Responsible for:

  * Path selection (routing)
  * Packet forwarding

👉 Devices: **Routers** 

---

# 🔹 IPv4 Address Basics

* IPv4 = **32 bits (4 bytes)**
* Divided into **4 octets (8 bits each)**

Example:

```
192.168.1.254
```

Binary:

```
11000000.10101000.00000001.11111110
```

👉 Each octet = 8 bits 

---

 

 

---

# 🔹 Prefix Length (/Notation)

Example:

```
192.168.1.254/24
```

* /24 = first **24 bits = network**
* Remaining = **host bits**

👉 Total bits = 32
👉 Network bits = 24
👉 Host bits = 8

---

# 🔹 Netmask

| Prefix | Netmask       |
| ------ | ------------- |
| /8     | 255.0.0.0     |
| /16    | 255.255.0.0   |
| /24    | 255.255.255.0 |

👉 Binary:

```
/24 → 11111111.11111111.11111111.00000000
```



---

# 🔹 Network vs Host Portion

Example:

```
192.168.1.254/24
```

* Network portion → first 3 octets → 192.168.1
* Host portion → last octet → 254

---

# 🔹 Network Address

* Host bits = **all 0s**

Example:

```
192.168.1.0/24
```

👉 Cannot assign to any device 

---

# 🔹 Broadcast Address

* Host bits = **all 1s**

Example:

```
192.168.1.255/24
```

👉 Used to send data to all devices in network
👉 Cannot assign to host 

---

# 🔹 IP Address Classes (Old but Important for Exams)

| Class | Range   | Default Prefix |
| ----- | ------- | -------------- |
| A     | 0–127   | /8             |
| B     | 128–191 | /16            |
| C     | 192–223 | /24            |
| D     | 224–239 | Multicast      |
| E     | 240–255 | Reserved       |

👉 Based on **first octet** 

---

# 🔹 Loopback Address

* Range: **127.0.0.0 – 127.255.255.255**
* Common: `127.0.0.1`

👉 Used to test local machine (network stack) 

---

# 🔹 Key Understanding (VERY IMPORTANT)

* MAC address → inside LAN
* IP address → across networks

👉 Router uses IP
👉 Switch uses MAC

---

# 🔁 Quick Revision

* IPv4 = 32 bits
* Divided into network + host
* Network = all 0s
* Broadcast = all 1s
* /24 = 255.255.255.0

---

# ❓ Interview Questions with Answers

## 🔸 Basic

Q1. What is IPv4 address?
A. A 32-bit logical address used to identify devices in a network.

---

Q2. Why do we need IP address?
A. To identify devices across different networks and enable routing.

---

Q3. What is subnet mask?
A. It defines which part of IP is network and which part is host.

---

## 🔸 Intermediate

Q4. What is /24?
A. It means first 24 bits are network bits and last 8 bits are host bits.

---

Q5. What is network address?
A. An address where all host bits are 0; represents the network itself.

---

Q6. What is broadcast address?
A. An address where all host bits are 1; used to send to all devices.

---

Q7. Difference between MAC and IP?
A. MAC is physical (Layer 2), IP is logical (Layer 3).

---

## 🔸 Scenario-Based (IMPORTANT)

Q8. Can you assign 192.168.1.0 to a host?
A. No, it is the network address.

---

Q9. Can you assign 192.168.1.255?
A. No, it is the broadcast address.

---

Q10. Why do we divide network and host?
A. To organize networks and allow efficient routing.

---
 