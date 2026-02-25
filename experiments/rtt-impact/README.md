 # RTT Impact on TCP Performance (Experiment 2)

## 1. Objective
The objective of this experiment is to study the effect of **Round-Trip Time (RTT)** on TCP behavior in a client–server network. By introducing an additional routing hop between the client and the server, we analyze how increased RTT influences packet traversal time, acknowledgment delays, and overall TCP responsiveness.

This experiment builds on the baseline TCP setup (Experiment 1) and focuses specifically on **latency-induced performance changes**, without introducing packet loss or congestion.

---

## 2. Network Topology
The topology consists of:
- One TCP client (PC0)
- Two routers (Router0 and Router2)
- Two switches (Switch0 and Switch1)
- One TCP server (Server0)

An **additional router hop** is inserted between the client and server to increase RTT while keeping bandwidth and packet loss constant.

**Screenshot:**
- `exp2_topology.png`

---

## 3. Experimental Setup
- Simulation environment: Cisco Packet Tracer
- Transport protocol: TCP
- Simulation mode: Packet-level (Simulation Mode)
- Traffic type: TCP data with acknowledgments
- Filters enabled: TCP, HTTP
- No artificial packet drops or bandwidth throttling applied

The experiment observes packet movement and timing at each hop using the Simulation Panel and Event List.

---

## 4. Experiment Procedure

### Step 1: TCP Transmission Initiation
TCP communication is initiated from **PC0** toward **Server0**. The first packet is observed leaving the client and entering the network.

**Screenshot:**
- `exp2_tcp_start_pc.png`

---

### Step 2: Packet Traversal Through Intermediate Router
The TCP packet traverses the intermediate router (Router0 → Router2). This additional hop introduces extra propagation and processing delay, contributing directly to increased RTT.

**Screenshot:**
- `exp2_tcp_mid_router.png`

---

### Step 3: Packet Arrival at Server
The TCP packet successfully reaches **Server0**, confirming end-to-end connectivity with increased RTT but without packet loss.

**Screenshot:**
- `exp2_tcp_server_reached.png`

---

### Step 4: TCP Acknowledgment Return Path
The server generates a TCP acknowledgment (ACK), which travels back through the same multi-hop path toward the client. The return ACK experiences similar latency due to the increased RTT.

**Screenshot:**
- `exp2_tcp_return_ack.png`

---

### Step 5: RTT Observation Using Event List
The Simulation Event List is used to observe timestamps for packet transmission and acknowledgment reception. The increased RTT is evident from the time difference between forward data packets and return ACKs.

**Screenshot:**
- `06_event_list_rtt_timing.png`

---

## 5. Observations
- Introducing an additional router increases RTT even in the absence of congestion.
- TCP acknowledgments are delayed proportionally with the increased RTT.
- Packet delivery remains reliable, but **response time increases**.
- Higher RTT directly affects TCP’s effective throughput and responsiveness.
- No packet loss or retransmissions were observed, isolating RTT as the only influencing factor.

---

## 6. Conclusion
This experiment demonstrates that **RTT is a critical factor in TCP performance**. Even without packet loss or congestion, increasing RTT results in delayed acknowledgments and slower feedback to the sender. This highlights why long-distance or multi-hop networks experience reduced TCP efficiency and why latency optimization is crucial in real-world networks.

The results from this experiment form a foundation for further analysis involving packet loss, congestion control, and fairness in subsequent experiments.

---

## 7. Screenshots Reference
All screenshots related to this experiment are available in the `screenshots/` directory:

1. `exp2_topology.png`
2. `exp2_tcp_start_pc.png`
3. `exp2_tcp_mid_router.png`
4. `exp2_tcp_server_reached.png`
5. `exp2_tcp_return_ack.png`
6. `06_event_list_rtt_timing.png`
