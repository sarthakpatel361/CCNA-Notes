 # 📘 Subnetting Answers with Reasoning

---

# 🧩 Question 1

IP: 192.168.10.45/24

## 🔹 Key Idea

/24 → block size = 256 → entire last octet

## ✅ Answers

* Network → **192.168.10.0**
* Broadcast → **192.168.10.255**
* First usable → **192.168.10.1**
* Last usable → **192.168.10.254**
* Hosts → **254**

## 🧠 Reason

* /24 → host bits = 8 → 2⁸ = 256 → usable = 254
* Range always: **.0 – .255**

---

# 🧩 Question 2

IP: 192.168.20.70/26

## 🔹 Step 1: Block size

/26 → 255.255.255.192
Block = 256 - 192 = **64**

## 🔹 Step 2: Ranges

0–63, 64–127, 128–191, 192–255

👉 70 lies in **64–127**

## ✅ Answers

* Network → **192.168.20.64**
* Broadcast → **192.168.20.127**
* First → **192.168.20.65**
* Last → **192.168.20.126**
* Subnet range → **64–127**

---

# 🧩 Question 3

IP: 192.168.1.200/27

## 🔹 Step 1: Block size

/27 → 255.255.255.224
Block = 256 - 224 = **32**

## 🔹 Step 2: Ranges

0,32,64,96,128,160,192,224

👉 200 lies in **192–223**

## ✅ Answers

* Network → **192.168.1.192**
* Broadcast → **192.168.1.223**
* First → **192.168.1.193**
* Last → **192.168.1.222**

## 🔹 Subnet Number

Counting:
0–31 (1), 32–63 (2), …, 192–223 (**7th subnet**)

---

# 🧩 Question 4

IP: 10.0.0.150/28

## 🔹 Step 1: Block size

/28 → 255.255.255.240
Block = 256 - 240 = **16**

## 🔹 Step 2: Ranges

0,16,32,48,64,80,96,112,128,144,160

👉 150 lies in **144–159**

## ✅ Answers

* Network → **10.0.0.144**
* Broadcast → **10.0.0.159**
* First → **10.0.0.145**
* Last → **10.0.0.158**
* Hosts → **14**

## 🧠 Reason

2⁴ = 16 → usable = 14

---

# 🧩 Question 5

IP: 172.16.5.10/30

## 🔹 Step 1: Block size

/30 → 255.255.255.252
Block = 256 - 252 = **4**

## 🔹 Step 2: Ranges

0–3, 4–7, 8–11, 12–15

👉 10 lies in **8–11**

## ✅ Answers

* Network → **172.16.5.8**
* Broadcast → **172.16.5.11**
* First → **172.16.5.9**
* Last → **172.16.5.10**

## 🔹 Hosts

2² = 4 → usable = **2**

---

## 🔹 Why /30 is used?

👉 Only **2 usable IPs**
👉 Perfect for:

* Router-to-router links
* Point-to-point connections

👉 No IP wastage

---

# 🔥 Final Pattern You Must Remember

| Prefix | Block Size | Usable Hosts |
| ------ | ---------- | ------------ |
| /24    | 256        | 254          |
| /26    | 64         | 62           |
| /27    | 32         | 30           |
| /28    | 16         | 14           |
| /30    | 4          | 2            |

---

 Solution – 192.168.77.200/20 
🔹 Step 1: Understand the Prefix
/20 → Subnet mask = 255.255.240.0

👉 “Interesting octet” = 3rd octet (240)

🔹 Step 2: Find Block Size
Block size = 256 - 240 = 16

👉 Subnet increases by 16 in 3rd octet

🔹 Step 3: Subnet Ranges (3rd Octet)
0–15
16–31
32–47
48–63
64–79
80–95
...
🔹 Step 4: Find Where 77 Falls

👉 77 lies in:

64 – 79
🔹 Step 5: Final Answers
✅ Network Address
192.168.64.0
✅ Broadcast Address
192.168.79.255
✅ First Usable
192.168.64.1
✅ Last Usable
192.168.79.254
🔹 Step 6: Number of Hosts
Host bits = 32 - 20 = 12
Total = 2^12 = 4096
Usable = 4094
🔥 Final Answer Summary
Network → 192.168.64.0
Broadcast → 192.168.79.255
First usable → 192.168.64.1
Last usable → 192.168.79.254
Usable hosts → 4094
🧠 Key Insight (This is what matters)

👉 For /20:

Ignore last octet ❌
Focus on 3rd octet jumps of 16
---
