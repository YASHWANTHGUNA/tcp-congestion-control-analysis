# TCP Congestion Control Analysis

## Problem Statement
Modern networks must support multiple concurrent data flows over shared infrastructure while maintaining efficiency, stability, and fairness.  
TCP congestion control is the core mechanism that enables this, yet its behavior emerges from dynamic interactions between latency, loss, and competing flows.

This project experimentally studies **how TCP congestion control behaves under realistic network conditions** such as delay, packet loss, and multi-flow contention.

---

## Why TCP Congestion Control Matters
TCP carries the majority of Internet traffic. Its congestion control mechanisms determine:
- Network stability under load
- Fairness among competing users
- Throughput over long-distance, high-latency links
- Performance degradation under packet loss

Understanding TCP behavior is critical for:
- High-speed backbone networks
- Data center traffic engineering
- Long-haul and satellite communications
- Transport protocol design and optimization

---

## Experiments Conducted

This repository contains four structured experiments:

### 1. Baseline TCP Performance
Established a reference TCP flow under ideal conditions to observe normal behavior without congestion or loss.

### 2. RTT Impact on TCP Throughput
Analyzed how increasing round-trip time affects TCP’s effective throughput, highlighting latency-bound performance limitations.

### 3. Impact of Packet Loss on TCP
Studied TCP’s reaction to packet loss, including retransmissions and congestion window reduction.

### 4. TCP Fairness Analysis
Evaluated how multiple TCP flows share bandwidth when competing over a common bottleneck link.

---

## Key Insights (Conceptual, Not Numeric)

- TCP performance is fundamentally constrained by **RTT**, even in the absence of loss.
- Packet loss triggers conservative behavior that significantly reduces throughput.
- TCP naturally converges toward **fair bandwidth sharing** among competing flows.
- Congestion control behavior emerges from interaction between delay, loss, and contention—not from any single parameter.

---

## Tools and Methodology
- **Cisco Packet Tracer** for controlled network simulation
- Discrete-event simulation mode for packet-level observation
- HTTP-based TCP flows to emulate realistic application traffic
- Systematic variation of network conditions (RTT, loss, contention)

---

## Relevance to High-Speed and Long-Distance TCP
High-speed and long-distance networks amplify TCP limitations:
- Large RTTs slow congestion window growth
- Loss recovery becomes more expensive
- Fairness becomes critical under shared bottlenecks

The insights from these experiments directly map to challenges faced in:
- Transcontinental fiber networks
- Satellite and undersea links
- High-bandwidth academic and research networks

---

## Repository Structure
# TCP Congestion Control Analysis

## Problem Statement
Modern networks must support multiple concurrent data flows over shared infrastructure while maintaining efficiency, stability, and fairness.  
TCP congestion control is the core mechanism that enables this, yet its behavior emerges from dynamic interactions between latency, loss, and competing flows.

This project experimentally studies **how TCP congestion control behaves under realistic network conditions** such as delay, packet loss, and multi-flow contention.

---

## Why TCP Congestion Control Matters
TCP carries the majority of Internet traffic. Its congestion control mechanisms determine:
- Network stability under load
- Fairness among competing users
- Throughput over long-distance, high-latency links
- Performance degradation under packet loss

Understanding TCP behavior is critical for:
- High-speed backbone networks
- Data center traffic engineering
- Long-haul and satellite communications
- Transport protocol design and optimization

---

## Experiments Conducted

This repository contains four structured experiments:

### 1. Baseline TCP Performance
Established a reference TCP flow under ideal conditions to observe normal behavior without congestion or loss.

### 2. RTT Impact on TCP Throughput
Analyzed how increasing round-trip time affects TCP’s effective throughput, highlighting latency-bound performance limitations.

### 3. Impact of Packet Loss on TCP
Studied TCP’s reaction to packet loss, including retransmissions and congestion window reduction.

### 4. TCP Fairness Analysis
Evaluated how multiple TCP flows share bandwidth when competing over a common bottleneck link.

---

## Key Insights (Conceptual, Not Numeric)

- TCP performance is fundamentally constrained by **RTT**, even in the absence of loss.
- Packet loss triggers conservative behavior that significantly reduces throughput.
- TCP naturally converges toward **fair bandwidth sharing** among competing flows.
- Congestion control behavior emerges from interaction between delay, loss, and contention—not from any single parameter.

---

## Tools and Methodology
- **Cisco Packet Tracer** for controlled network simulation
- Discrete-event simulation mode for packet-level observation
- HTTP-based TCP flows to emulate realistic application traffic
- Systematic variation of network conditions (RTT, loss, contention)

---

## Relevance to High-Speed and Long-Distance TCP
High-speed and long-distance networks amplify TCP limitations:
- Large RTTs slow congestion window growth
- Loss recovery becomes more expensive
- Fairness becomes critical under shared bottlenecks

The insights from these experiments directly map to challenges faced in:
- Transcontinental fiber networks
- Satellite and undersea links
- High-bandwidth academic and research networks

---

## Repository Structure
experiments/ # Individual TCP experiments
topology/ # Packet Tracer simulation files
notes/ # Research observations and discussion
results/ # Screenshots and captured outputs


---

## Author
Undergraduate researcher exploring transport-layer behavior with emphasis on TCP congestion control dynamics.
