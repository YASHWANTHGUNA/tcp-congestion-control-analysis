# Final Observations and Discussion

## Cross-Experiment Insights

Across all experiments, TCP behavior consistently emerges from interaction effects rather than isolated parameters.

- RTT determines how quickly TCP can probe available bandwidth.
- Packet loss forces aggressive backoff, even when capacity exists.
- Fairness mechanisms prevent starvation but limit peak throughput per flow.

TCP congestion control is therefore best understood as a **dynamic equilibrium system**, not a static algorithm.

---

## Trade-Offs Observed

1. **Throughput vs Stability**
   - Aggressive growth improves utilization but risks congestion collapse.
   - Conservative backoff preserves stability but sacrifices throughput.

2. **Fairness vs Performance**
   - Equal sharing ensures fairness but reduces individual flow performance.
   - In shared bottlenecks, no flow can fully utilize the link alone.

3. **Latency Sensitivity**
   - High RTT penalizes flows even without congestion.
   - TCP favors low-latency paths in competitive environments.

---

## Limitations of Cisco Packet Tracer

While Packet Tracer is effective for conceptual analysis, it has limitations:

- Simplified TCP implementations
- No precise congestion window or RTT measurement
- Abstracted queueing and buffer behavior
- No support for modern TCP variants (e.g., Cubic, BBR)

Despite this, Packet Tracer is well-suited for:
- Visualizing packet flow
- Understanding congestion events
- Studying qualitative TCP behavior

---

## Why RTT and Fairness Dominate High-Speed TCP

In high-speed networks:
- Bandwidth-delay product grows large
- RTT dominates achievable throughput
- Fairness determines long-term flow performance

As link speeds increase, latency—not bandwidth—becomes the primary bottleneck.

---

## Expected Behavior in Real Networks

In real-world deployments:
- TCP Cubic or BBR would alter fairness dynamics
- Active Queue Management (AQM) would reduce loss
- RTT bias would be more pronounced
- Flow synchronization effects would appear

These experiments form a conceptual foundation for studying real TCP stacks in emulation or testbed environments.

---

## Research Takeaway

TCP congestion control is not merely a protocol feature—it is a distributed control system governing global Internet stability.

Understanding its behavior requires observing:
- Delay
- Loss
- Competition
- Feedback loops

This project provides a structured experimental lens into those dynamics.
