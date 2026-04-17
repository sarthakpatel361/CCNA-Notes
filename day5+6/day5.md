 # 📘 Day 5 – Ethernet LAN Switching ( Understanding Notes)

---

# 🔹 OSI Model (What Actually Matters Here)

## Layer 1 – Physical Layer (HOW data moves)

* Handles **actual transmission of bits**
* Converts:

  * 1s and 0s → electrical signals (copper)
  * 1s and 0s → light signals (fiber)
* Defines:

  * Cable type (UTP, fiber)
  * Speed (100Mbps, 1Gbps)
  * Connectors (RJ45)
* Has **NO intelligence** → just sends signals

👉 Think: “dumb pipe” that carries data 

---

## Layer 2 – Data Link Layer (HOW devices talk locally)

* Responsible for **device-to-device communication**
* Uses **MAC addresses** (physical identity)
* Converts data → **Frames**
* Detects errors using FCS (does NOT fix them)

👉 Important:

* Works only within same network (LAN)
* Switch operates here 

---

# 🔹 Encapsulation (Hidden but Critical)

When data is sent:

Application Data
↓
Transport → adds header → Segment
↓
Network → adds IP → Packet
↓
Data Link → adds MAC → Frame
↓
Physical → converts to bits

👉 Each layer adds its own identity
👉 This is why troubleshooting requires layer-by-layer thinking 

---

# 🔹 Ethernet Frame (Don’t Just Memorize — Understand)

## Structure + WHY it exists

### 1. Preamble (7 bytes)

* Pattern: 10101010 repeated
* Purpose: **Synchronize receiver clock**

👉 Without this → receiver can’t understand incoming bits

---

### 2. SFD (1 byte)

* Pattern: 10101011
* Purpose: Marks **start of actual frame**

👉 Think: “Real data starts NOW”

---

### 3. Destination MAC (6 bytes)

* Who should receive this frame

---

### 4. Source MAC (6 bytes)

* Who sent the frame

👉 THIS is what switch uses to learn (very important)

---

### 5. Type / Length (2 bytes)

* If value ≤1500 → payload size
* If ≥1536 → protocol type

  * IPv4 = 0x0800
  * IPv6 = 0x86DD

---

### 6. FCS (4 bytes)

* Uses CRC (Cyclic Redundancy Check)
* Detects errors in transmission

👉 If error found → frame is **discarded**

---

👉 Total Ethernet overhead = 26 bytes 

---

# 🔹 MAC Address (Deep Understanding)

* 48-bit unique identifier
* Example: AAAA.AA00.0001

## Structure:

* First 24 bits → OUI (Vendor)
* Last 24 bits → Unique device ID

## Key Reality:

* MAC address = **identity inside LAN**
* IP address = **identity across networks**

👉 Don’t mix these up or you’ll struggle later 

---

# 🔹 How a Switch Actually Works (CORE LOGIC)

Most people memorize this. You need to **visualize it step-by-step**.

---

## Step 1: Frame Arrives

Switch checks:

* Source MAC
* Destination MAC

---

## Step 2: Learning (MOST IMPORTANT)

Switch takes:
👉 Source MAC
👉 Stores it in MAC table with incoming port

Example:
PC1 (MAC1) sends frame → comes on Fa0/1
Switch stores:
MAC1 → Fa0/1

👉 This is how switch “learns network”

---

## Step 3: Forwarding Decision

### Case 1: Destination UNKNOWN

* MAC not in table
* Switch has no idea where device is

👉 Action:

* FLOOD frame to all ports except incoming

👉 Reason:

* Only way to find destination

---

### Case 2: Destination KNOWN

* MAC already in table

👉 Action:

* FORWARD only to specific port

👉 Result:

* Efficient communication
* No unnecessary traffic

---

## Step 4: MAC Aging

* Entries removed after ~5 minutes
* Why?

  * Devices may leave network
  * Ports may change

👉 Keeps table accurate 

---

# 🔹 Real Behavior (What Actually Happens in Network)

First communication:

* Switch doesn’t know anything
* Flooding happens

After learning:

* Switch becomes efficient
* Direct forwarding happens

👉 This transition = **learning phase → optimized phase**

---

# 🔹 Important Observations (High Value)

* Switch learns ONLY from **Source MAC**
* Unknown unicast = flooding
* Known unicast = forwarding
* Switch NEVER sends back on incoming port
* Each switch builds its own MAC table

---

# 🔁 Quick Revision (Mental Model)

Switch = Learns → Stores → Forwards

---

# ❓ Interview Questions with Answers

## 🔸 Basic

Q1. What is the role of Data Link layer?
A. It handles node-to-node communication, frames data, uses MAC addressing, and performs error detection.

---

Q2. What is a MAC address?
A. A 48-bit unique hardware identifier used for communication within a LAN.

---

Q3. What is an Ethernet frame?
A. A Layer 2 structure that includes MAC addresses, payload, and FCS for error detection.

---

## 🔸 Intermediate

Q4. Why is preamble required?
A. It synchronizes the receiver’s clock so it can correctly interpret incoming bits.

---

Q5. What happens if FCS fails?
A. The frame is discarded because it is considered corrupted.

---

Q6. How does a switch learn MAC addresses?
A. By reading the source MAC of incoming frames and associating it with the receiving port.

---

Q7. Why doesn’t switch learn from destination MAC?
A. Because destination MAC only tells where frame is going, not where device is physically connected.

---

## 🔸 Scenario-Based (CRITICAL)

Q8. Why does a switch flood traffic?
A. Because it does not know the destination MAC location, so it sends the frame to all ports to find the device.

---

Q9. What improves network efficiency over time?
A. MAC learning—switch builds a table and starts forwarding instead of flooding.

---

Q10. What happens if MAC entry expires?
A. Switch forgets the device and will flood again until relearned.

---

Q11. Two switches connected, unknown MAC. What happens?
A. Both switches flood the frame, increasing broadcast domain traffic until MAC is learned.

---

 

