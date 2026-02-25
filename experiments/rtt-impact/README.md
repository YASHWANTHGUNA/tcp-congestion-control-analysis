RTT Impact on TCP Performance (Experiment 2)
1. Objective

The objective of this experiment is to systematically analyze the impact of Round-Trip Time (RTT) on TCP performance in a controlled client–server network. By introducing an additional routing hop between the sender and receiver, this experiment isolates RTT as the primary variable, enabling a focused study of latency-induced effects on TCP data transmission and acknowledgment behavior.

2. Network Topology

The experimental topology consists of:

One TCP client (PC0)

Two routers (Router0, Router2)

Two switches (Switch0, Switch1)

One TCP server (Server0)

An intermediate router is inserted between the client and server paths to deliberately increase RTT while keeping bandwidth, packet loss, and congestion constant.

Reference Screenshot:

exp2_topology.png

3. Experimental Setup

Simulation tool: Cisco Packet Tracer

Transport protocol: TCP

Simulation mode: Packet-level (Simulation Mode)

Traffic characteristics: TCP data packets with acknowledgments

Filters enabled: TCP, HTTP

No artificial packet drops, congestion, or bandwidth throttling applied

This setup ensures that observed performance changes are attributable solely to increased RTT.

4. Experiment Procedure
Step 1: TCP Session Initiation

A TCP transmission is initiated from the client (PC0) toward the server (Server0). The initial packet departure marks the start of the RTT measurement interval.

Screenshot:

exp2_tcp_start_pc.png

Step 2: Packet Traversal Through Intermediate Router

The TCP data packet traverses the intermediate router, introducing additional propagation and processing delay. This extra hop directly contributes to an increase in RTT.

Screenshot:

exp2_tcp_mid_router.png

Step 3: Packet Reception at Server

The TCP packet successfully reaches the server, confirming reliable end-to-end delivery despite the increased RTT.

Screenshot:

exp2_tcp_server_reached.png

Step 4: Acknowledgment Return Path

The server generates a TCP acknowledgment (ACK), which follows the same multi-hop path back to the client. The delayed arrival of the ACK reflects the increased RTT.

Screenshot:

exp2_tcp_return_ack.png

Step 5: RTT Measurement Using Simulation Event List

Packet timestamps from the Simulation Event List are examined to measure the delay between data packet transmission and acknowledgment reception, providing a direct visualization of RTT impact.

Screenshot:

06_event_list_rtt_timing.png

5. Observations

Increasing RTT results in delayed acknowledgment reception at the sender.

TCP packet delivery remains reliable, with no packet loss or retransmissions observed.

The sender experiences slower feedback due to increased latency, which can limit effective throughput.

RTT directly influences TCP responsiveness even under ideal, congestion-free conditions.

6. Conclusion

This experiment demonstrates that RTT is a fundamental determinant of TCP performance. Even in the absence of congestion and packet loss, increased RTT leads to delayed acknowledgments and reduced protocol responsiveness. These results emphasize the importance of latency optimization in wide-area and multi-hop networks.

The findings from this experiment provide a foundation for subsequent studies involving packet loss, congestion control algorithms, and fairness analysis.

7. Screenshots Reference

All experiment-related screenshots are available in the screenshots/ directory:

exp2_topology.png

exp2_tcp_start_pc.png

exp2_tcp_mid_router.png

exp2_tcp_server_reached.png

exp2_tcp_return_ack.png

06_event_list_rtt_timing.png

