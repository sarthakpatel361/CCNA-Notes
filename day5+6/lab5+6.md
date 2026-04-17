  Topology Setup 
  
  PC1 -------- SW1 -------- SW2 -------- PC3
             |              |
            PC2            PC4

            | Device | IP Address  | MAC Address    |
| ------ | ----------- | -------------- |
| PC1    | 192.168.1.1 | AAAA.AAAA.AAAA |
| PC2    | 192.168.1.2 | BBBB.BBBB.BBBB |
| PC3    | 192.168.1.3 | CCCC.CCCC.CCCC |
| PC4    | 192.168.1.4 | DDDD.DDDD.DDDD |
🔥 ARP Process (What Actually Happens)
🎯 Scenario:

PC1 wants to ping PC3

🧠 Step 1: Problem

PC1 knows:

Destination IP = 192.168.1.3
❌ Does NOT know MAC

👉 This is where ARP starts

📡 Step 2: ARP Request (Broadcast)

PC1 sends:

Src MAC: AAAA
Dst MAC: FFFF.FFFF.FFFF (broadcast)
Message:
👉 “Who has 192.168.1.3?”
🔁 Step 3: Switch Behavior

SW1:

Learns: AAAA → Port1
Floods to all ports

SW2:

Also floods to its ports

👉 EVERY device receives it

🎯 Step 4: ARP Reply (Unicast)

Only PC3 responds:

Src MAC: CCCC
Dst MAC: AAAA
Message:
👉 “I am 192.168.1.3”
⚡ Step 5: Learning Happens
PC1 stores:
192.168.1.3 → CCCC
Switches learn:
CCCC → correct port
🚀 Step 6: Actual Communication

Now PC1 sends:

Src MAC: AAAA
Dst MAC: CCCC

👉 Switch forwards directly (NO flooding)
⚠️ Important Observations
ARP request = broadcast → flood
ARP reply = unicast → forward
Switch learns from source MAC
First ping may fail/slow due to ARP