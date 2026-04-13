 
# OSI Model & TCP/IP Model — Interview Notes

---

## 1. OSI Model (Open Systems Interconnection)

A conceptual framework with 7 layers that standardizes how different network systems communicate.

> Mnemonic (top to bottom): **All People Seem To Need Data Processing**
> Mnemonic (bottom to top): **Please Do Not Throw Sausage Pizza Away**

| Layer | Name | Key Function | Protocol/Device Examples |
|-------|------|--------------|--------------------------|
| 7 | Application | Interface for end-user apps | HTTP, HTTPS, FTP, DNS, SMTP |
| 6 | Presentation | Data formatting, encryption, compression | SSL/TLS, JPEG, ASCII |
| 5 | Session | Manages sessions between apps | NetBIOS, PPTP |
| 4 | Transport | End-to-end delivery, error recovery | TCP, UDP |
| 3 | Network | Logical addressing, routing | IP, ICMP, Router |
| 2 | Data Link | MAC addressing, framing | Ethernet, Switch, ARP |
| 1 | Physical | Raw bit transmission | Cables, Hubs, NIC |

---

## 2. What Each Layer Does (in plain English)

**Layer 7 — Application**
- Where the user interacts. Your browser, email client, etc.
- Does NOT mean the app itself — it means the protocols the app uses.
- Example: when you open gmail.com, HTTP/HTTPS is Layer 7.

**Layer 6 — Presentation**
- Translates data into a format the application can understand.
- Handles encryption (SSL/TLS) and compression.
- Example: converting EBCDIC to ASCII, encrypting data before sending.

**Layer 5 — Session**
- Opens, manages, and closes sessions between two devices.
- Handles authentication and reconnection.
- Example: when you log into a website, a session is created.

**Layer 4 — Transport**
- Responsible for reliable (TCP) or fast (UDP) delivery.
- Segments data and reassembles it at the destination.
- Adds port numbers to identify which application gets the data.

**Layer 3 — Network**
- Handles logical IP addressing and routing between networks.
- Routers operate here.
- Example: finding the best path from your PC to google.com.

**Layer 2 — Data Link**
- Handles MAC addresses and frames within the same network.
- Switches operate here.
- Divided into two sublayers: LLC and MAC.

**Layer 1 — Physical**
- Raw bits (0s and 1s) transmitted over cables, fiber, or radio.
- Hubs, cables, and NICs operate here.

---

## 3. TCP/IP Model

A practical 4-layer model that the internet actually runs on.

| TCP/IP Layer | OSI Equivalent | Protocols |
|--------------|----------------|-----------|
| Application | Layers 5, 6, 7 | HTTP, FTP, DNS, SMTP, DHCP |
| Transport | Layer 4 | TCP, UDP |
| Internet | Layer 3 | IP, ICMP, ARP |
| Network Access | Layers 1, 2 | Ethernet, Wi-Fi |

> Note: Some books show a 5-layer TCP/IP model that splits Network Access into Physical and Data Link — both versions are acceptable in interviews.

---

## 4. TCP vs UDP — Must Know for Interviews

| Feature | TCP | UDP |
|---------|-----|-----|
| Connection | Connection-oriented (3-way handshake) | Connectionless |
| Reliability | Guaranteed delivery | No guarantee |
| Speed | Slower | Faster |
| Error checking | Yes | Minimal |
| Use case | Web, email, file transfer | Video streaming, VoIP, DNS, gaming |

**TCP 3-way handshake:**
1. SYN — client sends connection request
2. SYN-ACK — server acknowledges
3. ACK — client confirms, connection established

---

## 5. OSI vs TCP/IP — Key Differences

| Point | OSI | TCP/IP |
|-------|-----|--------|
| Layers | 7 | 4 |
| Developed by | ISO | DARPA |
| Usage | Conceptual/reference model | Practical, used by the internet |
| Protocol independence | Yes | Built around TCP/IP protocols |

---

## 6. Data Encapsulation (must know)

As data travels down the OSI layers, each layer adds its own header (and sometimes trailer). This is called **encapsulation**.

| Layer | Data Unit Name |
|-------|---------------|
| 7–5 | Data |
| 4 (Transport) | Segment (TCP) / Datagram (UDP) |
| 3 (Network) | Packet |
| 2 (Data Link) | Frame |
| 1 (Physical) | Bits |

At the receiving end, each layer strips its header — this is called **de-encapsulation**.

---

## 7. Common Interview Questions & Answers

**Q: What is the difference between OSI and TCP/IP model?**
A: OSI is a 7-layer conceptual model used as a reference standard. TCP/IP is a 4-layer practical model that the internet actually uses. OSI separates Session and Presentation as distinct layers; TCP/IP combines them into the Application layer.

**Q: Which layer does a router operate at?**
A: Layer 3 (Network). It uses IP addresses to route packets between networks.

**Q: Which layer does a switch operate at?**
A: Layer 2 (Data Link). It uses MAC addresses to forward frames within a network. A Layer 3 switch can also route between VLANs.

**Q: Which layer does a hub operate at?**
A: Layer 1 (Physical). It blindly broadcasts data to all ports with no intelligence.

**Q: What is the difference between TCP and UDP?**
A: TCP is connection-oriented, reliable, and slower — used for HTTP, email, FTP. UDP is connectionless, faster but unreliable — used for DNS, VoIP, video streaming.

**Q: What happens during TCP's 3-way handshake?**
A: SYN → SYN-ACK → ACK. The client initiates, the server acknowledges, and the client confirms. Only then is the connection established.

**Q: What is encapsulation?**
A: The process of adding headers (and trailers) at each layer as data travels down the OSI stack from Application to Physical. At the receiver, headers are stripped layer by layer — called de-encapsulation.

**Q: What is the PDU at Layer 3?**
A: A Packet. At Layer 2 it's a Frame. At Layer 4 it's a Segment (TCP) or Datagram (UDP).

**Q: Why does the OSI model matter if TCP/IP is what we use?**
A: OSI gives a universal language for troubleshooting and understanding network communication. When diagnosing issues, engineers refer to OSI layers — e.g. "this is a Layer 1 problem" (cable issue) vs "Layer 3 problem" (routing issue).

---

## 8. Quick Memory Tips

- **Layer 2 = MAC address** (hardware, burned into NIC)
- **Layer 3 = IP address** (logical, assigned by admin/DHCP)
- **TCP = phone call** (establish connection first, then talk)
- **UDP = sending a letter** (just send it, no confirmation)
- **Router = Layer 3**, **Switch = Layer 2**, **Hub = Layer 1**
