# 📘 Subnetting Example – 192.168.40.150/25

---

## 🔹 Given

IP: **192.168.40.150/25**

---

## 🔹 Step 1: Convert Prefix to Mask

```text
/25 = 255.255.255.128
```

---

## 🔹 Step 2: Block Size

```text
Block size = 256 - 128 = 128
```

---

## 🔹 Step 3: Number of Subnets

(Assume base = /24)

```text
Borrowed bits = 25 - 24 = 1
Subnets = 2^1 = 2
```

---

## 🔹 Step 4: Subnet Ranges

```text
0 – 127
128 – 255
```

👉 IP = 150 → lies in **128–255**

---

## 🔹 Step 5: Network Address

```text
Network = 192.168.40.128
```

---

## 🔹 Step 6: Broadcast Address

```text
Broadcast = 192.168.40.255
```

---

## 🔹 Step 7: First Usable

```text
192.168.40.129
```

---

## 🔹 Step 8: Last Usable

```text
192.168.40.254
```

---

## 🔹 Step 9: Usable Hosts

```text
Host bits = 32 - 25 = 7
Total = 2^7 = 128
Usable = 128 - 2 = 126
```

---

#  Final Answer

* Block size → **128**
* Subnets → **2**
* Network → **192.168.40.128**
* Broadcast → **192.168.40.255**
* First usable → **192.168.40.129**
* Last usable → **192.168.40.254**
* Usable hosts → **126**

---

#  Key Takeaway

```text
Range → decides everything
Start = Network
End = Broadcast
```

---
# 📘 Subnetting Example – 10.20.30.200/27

---

## 🔹 Given

IP: **10.20.30.200/27**

---

## 🔹 Step 1: Subnet Mask

```text
/27 = 255.255.255.224
```

---

## 🔹 Step 2: Block Size

```text
Block size = 256 - 224 = 32
```

---

## 🔹 Step 3: Number of Subnets

(Assume base = /24)

```text
Borrowed bits = 27 - 24 = 3
Subnets = 2^3 = 8
```

---

## 🔹 Step 4: Subnet Ranges

```text
0, 32, 64, 96, 128, 160, 192, 224
```

👉 IP = 200 → lies in **192–223**

---

## 🔹 Step 5: Network Address(All host bits are 0)

```text
10.20.30.192
```

---

## 🔹 Step 6: Broadcast Address(All host bits are 1)

```text
10.20.30.223
```

---

## 🔹 Step 7: First Usable

```text
10.20.30.193
```

---

## 🔹 Step 8: Last Usable

```text
10.20.30.222
```

---

## 🔹 Step 9: Usable Hosts

```text
Block size = 32
Usable = 32 - 2 = 30
```

---

# ✅ Final Answer

* Block size → **32**
* Subnets → **8**
* Network → **10.20.30.192**
* Broadcast → **10.20.30.223**
* First usable → **10.20.30.193**
* Last usable → **10.20.30.222**
* Usable hosts → **30**

---

# 🧠 Key Insight

```text
Find block → find range → everything comes from that
```

---
# 📘 Subnetting Example – 10.20.30.200/27

---

## 🔹 Given

IP: **10.20.30.200/27**

---

## 🔹 Step 1: Subnet Mask

```text
/27 = 255.255.255.224
```

---

## 🔹 Step 2: Block Size

```text
Block size = 256 - 224 = 32
```

---

## 🔹 Step 3: Number of Subnets

(Assume base = /24)

```text
Borrowed bits = 27 - 24 = 3
Subnets = 2^3 = 8
```

---

## 🔹 Step 4: Subnet Ranges

```text
0, 32, 64, 96, 128, 160, 192, 224
```

👉 IP = 200 → lies in **192–223**

---

## 🔹 Step 5: Network Address

```text
10.20.30.192
```

---

## 🔹 Step 6: Broadcast Address

```text
10.20.30.223
```

---

## 🔹 Step 7: First Usable

```text
10.20.30.193
```

---

## 🔹 Step 8: Last Usable

```text
10.20.30.222
```

---

## 🔹 Step 9: Usable Hosts

```text
Block size = 32
Usable = 32 - 2 = 30
```

---

# ✅ Final Answer

* Block size → **32**
* Subnets → **8**
* Network → **10.20.30.192**
* Broadcast → **10.20.30.223**
* First usable → **10.20.30.193**
* Last usable → **10.20.30.222**
* Usable hosts → **30**

---

 # 📘 Subnetting Example – 172.16.70.45/20

---

## 🔹 Given

IP: **172.16.70.45/20**

---

## 🔹 Step 1: Subnet Mask

```text id="h9c2tk"
/20 = 255.255.240.0
```

👉 First non-255 octet = **3rd octet (240)**

---

## 🔹 Step 2: Block Size

```text id="v0w3p1"
Block size = 256 - 240 = 16
```

👉 Subnetting happens in **3rd octet**

---

## 🔹 Step 3: Number of Subnets

(Assume base = /16)

```text id="7h3vaz"
Borrowed bits = 20 - 16 = 4
Subnets = 2^4 = 16
```

---

## 🔹 Step 4: Subnet Ranges (3rd octet)

```text id="yxg0n7"
0–15
16–31
32–47
48–63
64–79
80–95
...
```

👉 IP = **70** → lies in **64–79**

---

## 🔹 Step 5: Network Address

```text id="n1q7f0"
172.16.64.0
```

---

## 🔹 Step 6: Broadcast Address

```text id="q6u9dc"
172.16.79.255
```

---

## 🔹 Step 7: First Usable

```text id="v5x1y3"
172.16.64.1
```

---

## 🔹 Step 8: Last Usable

```text id="k2m8r4"
172.16.79.254
```

---

## 🔹 Step 9: Usable Hosts

```text id="x8p3lz"
Host bits = 32 - 20 = 12
Total = 2^12 = 4096
Usable = 4096 - 2 = 4094
```

---

# ✅ Final Answer

* Block size → **16 (3rd octet)**
* Subnets → **16**
* Network → **172.16.64.0**
* Broadcast → **172.16.79.255**
* First usable → **172.16.64.1**
* Last usable → **172.16.79.254**
* Usable hosts → **4094**

---

# 🧠 Key Insight (THIS IS CRITICAL)

```text id="0bqk7e"
Don’t look at last octet blindly
Find the “interesting octet” first
```

---



 