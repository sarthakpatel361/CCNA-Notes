 # 📘 IPv4 Header Example (Real + Explained)

---

## 🧩 Example Packet

```text
Source IP      : 192.168.1.10
Destination IP : 8.8.8.8
Protocol       : TCP
Data           : "Hello"
```

---

# 🔹 IPv4 Header Fields (Filled Example)

| Field           | Example Value | Meaning             |
| --------------- | ------------- | ------------------- |
| Version         | 4             | IPv4                |
| IHL             | 5             | Header = 20 bytes   |
| DSCP            | 0             | No priority         |
| ECN             | 0             | No congestion       |
| Total Length    | 40 bytes      | Header + Data       |
| Identification  | 54321         | Packet ID           |
| Flags           | 0             | No fragmentation    |
| Fragment Offset | 0             | Not fragmented      |
| TTL             | 64            | Can pass 64 routers |
| Protocol        | 6             | TCP                 |
| Header Checksum | 0xABCD        | Error check         |
| Source IP       | 192.168.1.10  | Sender              |
| Destination IP  | 8.8.8.8       | Receiver            |
| Options         | None          | Not used            |

---

# 🔥 What Happens in Network

---

## 🧠 Step 1: Packet Created

Computer builds packet:

```text
[IPv4 Header] + [TCP Header] + [Data]
```

---

## 🧠 Step 2: Router Processing

Each router checks:

* Destination IP → where to send
* TTL → reduce by 1

Example:

```text
Initial TTL = 64
After 1 router = 63
After 2 routers = 62
```

👉 If TTL = 0 → packet dropped

---

## 🧠 Step 3: At Destination

* Destination IP matches
* Packet accepted
* TCP reads data

---

# 🔥 Real Understanding of Key Fields

---

## 🔸 TTL

👉 Limits packet life
👉 Prevents infinite loops

---

## 🔸 Protocol

👉 Router says:

```text
"Send this to TCP process"
```

---

## 🔸 Checksum

👉 Router verifies header integrity
👉 If wrong → packet dropped

---

## 🔸 Identification + Flags

👉 Used only if packet is split

---

# 🔁 Visual Representation

```text
| IPv4 Header (20 bytes) | TCP Header | Data |
```

---

# 🧠 Important Insight

👉 Router only cares about:

* Destination IP
* TTL
* Protocol

👉 Everything else = supporting info

 
